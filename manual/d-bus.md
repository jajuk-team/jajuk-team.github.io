---
title: D-bus - Jajuk
layout: default
---

# D-bus

## How to get D-Bus working
- Jajuk contains the necessary code changes to enable control via D-Bus, currently the following actions are available (see class DBusSupport for the latest list of methods published to D-Bus): 
    - previous
    - next
    - rewind
    - playPause
    - stop
    - forward
    - exit
    - shuffleGlobal
    - previousAlbum
    - nextAlbum
    - increaseVolume
    - decreaseVolume
    - mute
    - currentHTML - returns the current playing track as HTML snippet
    - current - returns the current playing track as simple string
    - banCurrent (see [banning system](ratings.html))
    - showCurrentlyPlaying
    - bookmarkCurrentlyPlaying

D-Bus for Jajuk is provided by the open source library for D-Bus binding for Java and a few additional .jar files that are used by this library. Most of the setup is done "behind the scenes", if you are using a Unix-like operating system that uses a X-Window Manager with support for D-Bus, it should work out of the box. During startup, Jajuk tries to establish a connection to the D-Bus session daemon to provide it's interfaces to all applications running in the same session. []()

## Remote control
The following applications allow to test controlling Jajuk remotely, "dbus-send" and "qdbus" can also be used to create scripts that control Jajuk, i.e. integration in LIRC or other systems: 
- dbus-send, e.g. use the following command:
<pre> 
dbus-send --session --print-reply --dest=org.jajuk.dbus.DBusSupport  /JajukDBus org.jajuk.services.dbus.DBusSupport.next
</pre>
- qdbus (part of package qt-dev, similar to dbus-send, look at documentation for commandline parameters)
- qdbusviewer (part of package qt-dev, a graphical browser that allows easy calling of all the methods, look at the bottom of the list for ``org.jajuk.dbus.DBusSupport``.

KDE has also support for linking dbus-actions to keyboard shortcuts in the system settings dialogs for keyboard shortcuts, see bellow for details.

## Native library
- D-Bus on Unix uses an operating system functionality called "Unix domain sockets" which Java does not support natively. This means that some JNI code is required by the D-Bus Java bindings to provide interconnection with the D-Bus daemon. Jajuk delivers the necessary library, but currently only does so for the amd64 architecture (i.e. Intel 64-bit processors and AMD 64-bit processors) and the x86 architecture (i.e. Intel and AMD 32-bit processors).  
- Jajuk command line looks like this:
<pre>
$JAVA_BIN $JAVA_OPTIONS -Djava.library.path=$JAJUK_HOME/../lib -jar jajuk.jar $JAJUK_OPTIONS
</pre>

## Troubleshooting
- The logfile will print out an error entry with some stacktrace about any problem that is encountered while setting up the D-Bus connection. Make sure to look at this output to see what is missing. Typically the wrong libunix.so native library is found, look at the previous section for more information. Detailed instructions for the most common problems will be added here later...

### Cannot Resolve Session Bus Address
During startup the Error "Cannot Resolve Session Bus Address" is reported and DBus-support does not work. The logfile will show the following:
<pre>
2009/05/22 08:58:41 [INFO] Trying to start support for D-Bus on Linux with Bus:   
[Startup Async After Collection Load Thread] (Log.java:148) 
2009/05/22 08:58:41 [ERROR] Cannot Resolve Session Bus Address / null 
[Startup Async After Collection Load Thread] (Log.java:276) 
org.freedesktop.dbus.exceptions.DBusException: Cannot Resolve Session Bus Address
	at org.freedesktop.dbus.DBusConnection.getConnection(Unknown Source)
	at org.jajuk.services.dbus.DBusSupportImpl.connect(DBusSupportImpl.java:75)
	at org.jajuk.services.dbus.DBusManager.&lt;init&gt;(DBusManager.java:48)
	at org.jajuk.services.dbus.DBusManager.getInstance(DBusManager.java:38)
	at org.jajuk.services.core.StartupService$2.run(StartupService.java:258)
</pre>

### Solution
In order to access the D-Bus session-wide bus, the D-Bus libraries use an environment variable ``DBUS_SESSION_BUS_ADDRESS`` which is set by the dbus-startup scripts. Ensure that this environment variable is available. E.g. check the output of the following command:
<pre>
set | grep DBUS
</pre>
It should print out something like: 

<pre>
DBUS_SESSION_BUS_ADDRESS=unix:abstract=/tmp/dbus-nFsYERQLN6,guid=42fbbb828bf5a6bc6adcf2514a028b67
</pre>
If this environment variable is not set, ensure that the d-bus support is started correctly in your operating system configuration/installation.

##### Appendix: Using xbindkeys to enable multimedia keys to control Jajuk
- To map the multimedia keys on a laptop, we use xbindkeys with the following lines in ``~/.xbindkeysrc`` 

<pre>
"amixer -q set PCM 5%+ unmute"
  XF86AudioRaiseVolume

"amixer -q set PCM 5%- unmute"
  XF86AudioLowerVolume

"amixer -q set Master toggle"
  XF86AudioMute

"dbus-send --session --print-reply --dest=org.jajuk.dbus.DBusSupport /JajukDBus org.jajuk.services.dbus.DBusSupport.next"
  XF86AudioNext

"dbus-send --session --print-reply --dest=org.jajuk.dbus.DBusSupport /JajukDBus org.jajuk.services.dbus.DBusSupport.previous"
  XF86AudioPrev

"dbus-send --session --print-reply --dest=org.jajuk.dbus.DBusSupport /JajukDBus org.jajuk.services.dbus.DBusSupport.stop"
  XF86AudioStop

"dbus-send --session --print-reply --dest=org.jajuk.dbus.DBusSupport /JajukDBus org.jajuk.services.dbus.DBusSupport.playPause"
  XF86AudioPlay
</pre>

Just starting xbindkeys at the startup maps the keys and allows to use the multimedia keys for controlling Jajuk. The following will add key-combinations for non-audio keyboards, in this case CTRL-ALT-B for _ban_and CTRL-ALT-N for "show currently playing": 

<pre>
#ban
"dbus-send --session --print-reply --dest=org.jajuk.dbus.DBusSupport /JajukDBus org.jajuk.services.dbus.DBusSupport.banCurrent"
   m:0xc + c:56
   Control+Alt + b 

#showCurrent
"dbus-send --session --print-reply --dest=org.jajuk.dbus.DBusSupport /JajukDBus org.jajuk.services.dbus.DBusSupport.showCurrentlyPlaying"
   m:0xc + c:57
   Control+Alt + n
</pre>

## Appendix: How to configure key combinations for D-Bus in KDE
- KDE has built in support for assigning global keyboard shortcuts to any D-Bus method. You can easily use this to assign key-combinations to control Jajuk without having to switch to the application window. You can configure this by following the following steps: 
    1. Open KDE System Control Center
    2. Choose the item "Keyboard Shortcuts"
    3. Right click in the list of defined actions and choose "New Group" to create a separate group for Jajuk
    4. Right click on the new entry for "Jajuk" and choose "New -&gt; Global Shortcut -&gt; D-Bus-Call"
    5. On the right side, you should see a window with three tabs, "Comment", "Trigger" and "Action",
    6. Choose "Trigger" and select a keyboard combination that you want to use. The system warns you if you try to override an existing shortcut
    7. Next choose "Action" and enter the fields as follows:
        1. Application: org.jajuk.dbus.DBusSupport
        2. Object: /JajukDBus
        3. Method: org.jajuk.services.dbus.DBusSupport.&lt;dbus-action-to-call&gt;

    8. Save the changes and test that it works!
You can repeat this step for any keyboard combination that you would like to define.