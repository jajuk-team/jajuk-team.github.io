---
title: FAQ - Jajuk
layout: default
---
# Frequency Asked Questions

## General

### What is Jajuk ?

Jajuk is an advanced Jukebox used to manage large or scattered music collections for advanced users

### Under which license Jajuk is provided ?

Jajuk is free software published under the <a href="http://www.gnu.org/licenses/gpl.html" class="external text" title="http://www.gnu.org/licenses/gpl.html" rel="nofollow">GPL V2 license</a>

### Which formats are supported?

Please find <a href="/features.html#Supported_formats" title="Features"> the full list</a>

### Do you plan to read DVD and pictures etc... with Jajuk and make it a media center&nbsp;?

It is very unlikely. We want to make a jukebox with as many features as we can for advanced users. We want to manage Music and make it right.

### Can Jajuk play only the audio of a video? (Jajuk &gt; 1.6) 

In the <i>Configuration, Preferences view</i>, use "-novideo" in <i>Mplayers argument</i>.

### Can Jajuk play / encode Audio CDs&nbsp;?

No, Jajuk doesn't currently support Audio CDs read nor encode. Jajuk goal is primary to play existing audio files like MP3, not to create them. To encode/rip your CDs, we suggest using dedicated programs like the excellent <a href="http://cdexos.sourceforge.net/" class="external text" title="http://cdexos.sourceforge.net/" rel="nofollow">CDex</a>.
(Note however that Jajuk supports Data CDs with audio files like mp3s)

## Technical

###How to select sound device in case of multiple sound cards&nbsp;?

<ul>
<li> [Linux users] Configure your default sound card in ``$HOME/.mplayer/config`` (e.g.: ``ao=alsa:device=hw=0.3``). You can use ``aplay -l`` to list your sound devices.
</li><li> [Windows]&nbsp;: In Parameter view / Advanced tab, change "Sound engine" option and add ``-ao dsound:device=&lt;1, 2 or any other device id&gt;``
</li><li> Note: If your are not using your second card, why not deactivate it from your BIOS&nbsp;?
</li></ul>

### How much resources does Jajuk use?

<ul><li> Please read the <a href="/jajuk_manual_performance_tips.html" title="Performance tips">Performance tips</a> in the embedded help system
</li><li> On a recently manufactured PC, Jajuk uses less than 1 or 2&nbsp;% CPU and typically from 40 to 70 MB of memory for a 50 GB collection
</li></ul>

### (Windows) How to map statically a letter to a drive&nbsp;?

<ul><li> This can be useful to create jajuk devices mapped to a drive letter one time for ever (example: first external hard drive = M:, second external hard drive = N:)
</li><li> Check this <a href="http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/dm_drive_letter.mspx?mfr=true" class="external text" title="http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/dm_drive_letter.mspx?mfr=true" rel="nofollow">Microsoft page</a>
</li></ul>

### I would like to remote control Jajuk 

If you are running Linux, look at the functionality described at <a href="/jajuk_manual_d_bus.html" title="D-Bus">D-Bus</a>.


## Troubleshooting


### Every Operating System 


#### Some webradios doesn't play with mplayer but do with VLC

See <a href="https://github.com/jajuk-team/jajuk/issues/1819" class="external text" title="issue #1819" rel="nofollow">issue #1819</a>, a workaround is provided.


#### Jajuk stops after selection has been played

and you'd like to make it continue to play next tracks in collection...
If jajuk stops after the queue is void (check your Queue view), it's probably because your continue mode is disabled (this is the default). Enable it from <b>Modes</b> top menu -&gt; check "continue mode".


#### Jajuk continues to play even after the selection has been played

See previous question, tune this with the continue mode.


#### Duplicated albums in Catalog or Albums view

In Catalog view, you see the same cover several times. In Albums view, you see several lines with (apparently) the same album. 
You need to know that in Jajuk, albums are disambiguated by&nbsp;:

<ul><li> Of course the <b>album name</b> (case sensitive)
</li><li> but also the <a href="http://en.wikipedia.org/wiki/CDDB" class="external text" title="http://en.wikipedia.org/wiki/CDDB" rel="nofollow">CDDB</a> <b>disc id</b> (jajuk computes it)
</li></ul>
<p>To display the disc id value, select the album (in catalog view for instance) -&gt; Right click -&gt; select 'Properties'.
</p><p><u>Notes</u>&nbsp;:
</p>
<ul><li> If you change one of these properties on a duplicated album, both albums will be merged.
</li><li> If you feel something is wrong and that these rules are not applied, it may be a bug, please <a href="https://github.com/jajuk-team/jajuk/issues" title="Github issues">create an issue</a> and provide details on the albums and associated tracks.
</li></ul>

#### Cannot play some APE

If under MacOS or Linux, try to upgrade mplayer to recent releases (a 2009 build or later). 

#### I experience Out Of Memory issues

By default, Jajuk can use from 35MB to 512MB of physical memory. That should be large enough for most users. If you have a really huge collection and experience out-of-memory problems, increase the -Xmx value in the Jajuk launch script (open a support issue if you need help)


#### What can I do if my collection looks *really* corrupted&nbsp;?
Check out <a href="/jajuk_manual_using_devices.html#Collection_backup_and_restore" title="Using devices">Using_devices#Collection_backup_and_restore</a> the device page of the jajuk manual. Note that this case has never been reported so far as Jajuk provides an efficient built-in recovery system.


#### Jajuk cannot read files with non-ASCII characters

(Characters different from [a to z] like 'é' 'ç', Asian ideograms...). This is a filename encoding problem due to a wrong file system mounting option, a quick fix is to rename your filenames to utf-8.

### Windows Only


#### 32/64 bits JVM mess-up

In some special cases including switch from a 32 to a 64 bits JVM, you get this message when launching Jajuk from the shortcut&nbsp;:
</p>
<pre>The item 'javaw.exe' that this shortcut refers to has been changed or moved, so this shortcut will no longer work properly. Do you want to delete this shortcut?
</pre>
<p>Workaround&nbsp;: use the path instead&nbsp;:
</p>
<pre>C:\Windows\SysWOW64\javaw.exe
</pre>


#### Some parts of the screen are not refreshed

<p>
This may happen with some JRE 1.6 releases along with some video drivers. A workaround is change the 
windows shortcut that launches jajuk (the ``-Dsun.java2d.d3d=false`` option disables double buffering)&nbsp;:
</p><p>from&nbsp;:
</p>
<pre>C:\WINDOWS\system32\javaw.exe -client -Xms20M -Xmx512M -XX:MinHeapFreeRatio=5 
-XX:MaxHeapFreeRatio=10 -jar "C:\Program Files\Jajuk-1.9dev/bin/jajuk.jar" -test
</pre>
<p>to:
</p>
<pre>C:\WINDOWS\system32\javaw.exe -client -Dsun.java2d.d3d=false -Xms20M -Xmx512M 
-XX:MinHeapFreeRatio=5 -XX:MaxHeapFreeRatio=10 -jar "C:\Program Files\Jajuk-1.9dev/bin/jajuk.jar" -test
</pre>


#### Cannot play files on a Network drive (NAS)
<p>It is caused by the use of windows shortnames by mplayer (that are required to fix non-European filenames issues beside this). From 1.7, Jajuk automatically try both modes (short and long names) in case of failure.
</p>


#### A "pop" (think "standard windows 'pop' sound") is heard between tracks

<p>It's a sound emitted by the system when opening the systray balloons. We can't disable this sound as it is managed by Windows itself. You can:
</p>
<ul><li> Either change from balloon to none or Toast notification mode in Jajuk (<a href="/jajuk_manual_view_preferences.html" title="Preferences view"> Preferences view</a> / GUI tab/ Notification). 
</li><li> Or disable it manually from Windows Sounds Parameters wizards (Parameters / sound and multimedia / disable "notify new messages" sound)
</li></ul>


#### Firefox is set as default browser, I use JRE 1.6 Sun and I regularly get this message: "java.net.MalformedURLException: unknown protocol: socket"

<ul><li> See <a href="http://forum.java.sun.com/thread.jspa?threadID=5127788" class="external free" title="http://forum.java.sun.com/thread.jspa?threadID=5127788" rel="nofollow">http://forum.java.sun.com/thread.jspa?threadID=5127788</a>
</li><li> This is a Sun JRE 1.6 issue dealing with proxy settings. To fix it&nbsp;:
</li></ul>
<p>1) go to Control Panel -&gt; Java
2) click the Network Settings button
3) Select Direct Connection, and click ok a couple of times to exit
</p>


#### Cannot run Jajuk on Vista 64 bits (cannot execute 32 bits dll)

<p>(Thanks elefkof) You need to install both a 32-bit and 64-bits JRE. It will allow you to have a 64-bit and 32-bit versions alongside each other. It will use the 32-bit JRE for 32 bit apps and 64 bit JRE for 64 bit apps. See <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=4802695" class="external free" title="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=4802695" rel="nofollow">http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=4802695</a>
</p>


#### Access is denied under Vista

<ul><li> I get this error message:  java.io.FileNotFoundException: C:\Program Files (x86)\Jajuk\bin\JIntellitype.dll (Access is denied) when launching java installer under a Vista 64 bit
</li><li> Workaround: Run the installer as an administrator. That should work. (thanks kawayanuuc )
</li></ul>

<a name="Linux_Only" id="Linux_Only"></a> Linux Only
--------------


### Some webradios don't work

<p>If some webradios doesn't work, try to upgrade your mplayer version. For example, version SVN-r34777-snapshot-4.6.1 from feb 2012 is known to work. Note that if you can't get a newer mplayer version package for your distro, you can still build mplayer yourself in a directory and use this mplayer executable from Jajuk Preferences view / Advanced tab / Mplayer path (full path to the executable).
</p>

#### [KDE only] External browser features not available under KDE

<p>Under KDE, some jajuk features like "Help-&gt;Report an issue" or opening the Lastfm artist page from the suggestion view are disabled.
It's due to Sun bug 6486393 (see <a href="https://github.com/jajuk-team/jajuk/issues/1612" class="external free" title="issue #1612" rel="nofollow">issue #1612</a> for details).
</p>

#### Some Japanese fonts are not displayed correctly (squares) in some part of the screen

See <a href="https://help.ubuntu.com/community/Japanese_in_Java" class="external free" title="https://help.ubuntu.com/community/Japanese_in_Java" rel="nofollow">https://help.ubuntu.com/community/Japanese_in_Java</a>
Update: As of version 1.7.1, the above modification is NOT necessary for correct display of CJK (Chinese Japanese Korean) characters.  As long as you have appropriate CJK fonts installed, Java should be able to pick the right one to use.


#### After setting a cross-fade, the next track cannot start

<p>This can be caused by a wrong mplayer configuration that uses OSS or ALSA and not the sound engine that prevents from playing several songs together. Edit ~/.mplayer/conf and add a line like 'ao=esd' under Gnome or 'ao=arts' under KDE.
</p>


#### I get totally or partially blank screens when using XGL

<p>Try (not tested) using xnest (install it if required). That should start Jajuk using a generic X configuration using ``Xnest&nbsp;:1 &amp; DISPLAY=":1" jajuk``
(Feedbacks are welcomed)
</p>


#### My frame position and size is not kept between sessions or the frame is displayed at wrong position
<ul><li> Under some new Window Manager or graphical environments like XGL, frame size and position cannot be set properly due to various bugs in them. 
In these cases, we ignore previous session sizes and we set a fixed one that should fit most screen. If it is not the case, you can set a 
custom forced size by editing (jajuk closed) the ``&lt;home&gt;/.jajuk/conf.properties`` file and set a value in the ``jajuk.frame.forced_position`` line 
(format:x,y,width,height, example: ``jajuk.frame.forced_position=50,50,1350,1000`` ).
</li><li> This should <i>not</i> append under Windows, OSX and Linux with Xorg/Xfree, otherwise, please open an issue
</li></ul>


#### Jajuk blank frame and other various graphical issues using Beryl WM
<p>This is caused by an incompatibility between Sun JRE and Beryl. If under JRE 1.6, you can use&nbsp;:
</p>
<ul><li> Either <a href="http://wiki.beryl-project.org/wiki/Java" class="external text" title="http://wiki.beryl-project.org/wiki/Java" rel="nofollow">this fix</a>
</li><li> Or <a href="http://www.vikrammohan.com/blog/2006/12/31/how-to-make-java-swing-work-on-beryl-with-aiglx/|using" class="external text" title="http://www.vikrammohan.com/blog/2006/12/31/how-to-make-java-swing-work-on-beryl-with-aiglx/|using" rel="nofollow">nested X servers</a>
</li></ul>


#### Cross fade doesn't work under Linux (two mplayer processes cannot be launched concurrently)

- Under KDE, enable the sound server (artsd) from the KDE control center. Under Gnome, add this line in the ~/.mplayer/config file: "ao=esd" to use the Gnome sound server


#### Mplayer is not available and I get an "audio line occupied" message

<p>Try stopping all audio apps, check mute mode is not enable, check nothing users /dev/dsp (fuser /dev/dsp as root).
If you still have the issue, it is probably an Alsa deamon problem, please read <a href="http://forum.ubuntu-fr.org/viewtopic.php?id=12019" class="external text" title="http://forum.ubuntu-fr.org/viewtopic.php?id=12019" rel="nofollow">http://forum.ubuntu-fr.org/viewtopic.php?id=12019</a> this doc.
</p>


#### Problems displaying non-latin characters

<p>The problem may be with with xorg's locales (see <a href="http://ubuntuforums.org/showthread.php?t=301467&amp;highlight=java+text+input" class="external text" title="http://ubuntuforums.org/showthread.php?t=301467&amp;highlight=java+text+input" rel="nofollow">this thread</a>). For russian for ie, the cure is:
</p>

    sudo ln -s /usr/share/X11/locale/en_US.UTF-8 /usr/share/X11/locale/ru_RU.UTF-8


#### I have some trouble getting D-Bus to work

<p>Look at the items described at <a href="/jajuk_manual_d_bus.html#Troubleshooting" title="D-Bus">D-Bus#Troubleshooting</a>.
</p>


#### [OSX &gt;= 10.8] Message&nbsp;: "Jajuk can't be opened because it is from an unidentified developer."
<p>From Montain Lion, Apple forces developers to be "verified". You can still launch Jajuk using several workarounds, see <a href="http://www.wikihow.com/Install-Software-from-Unsigned-Developers-on-a-Mac" class="external text" title="http://www.wikihow.com/Install-Software-from-Unsigned-Developers-on-a-Mac" rel="nofollow">this page</a> for instance. Note that Jajuk is a Free software (as in "Free speech" but also as in "Free beer") and that we don't plan to deal with this kind of software restriction policy nor to pay or spend time and privacy to be 'identified' by Apple. 
</p>


#### I use OS X 10.4 and I have no Java 6 available for my system, what's the last supported version of jajuk running under Java 5&nbsp;?

<p>The last Jajuk version to run under Java 5 is 1.5.3. Please check <a href="http://downloads.sourceforge.net/jajuk/jajuk-macos-1.5.3.zip" class="external free" title="http://downloads.sourceforge.net/jajuk/jajuk-macos-1.5.3.zip" rel="nofollow">http://downloads.sourceforge.net/jajuk/jajuk-macos-1.5.3.zip</a> . This version is no more supported by the Jajuk team.
</p>

