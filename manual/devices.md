---
title: Devices
layout: default
---
Go back to the [TOC](/manual/main.html)

# Devices

## Introduction
Jajuk plays music from devices. A device is a set of audio files, a drive. It can be :

- A directory
- A data CD-ROM (Note : jajuk don't support audio CDs)
- An External Hard Disk
- A Network drive (Netbios/Samba/NFS...). Under Windows, use drive letter path (like ``T:\...``) but not network favorites path or UNC paths (like : \\host\directory ).
- A MP3 player (available only if it is seen by your operating system as an external drive).

<div class='info'>In order to be readable from Jajuk, devices must be seen as regular directories by the operating system but Jajuk uses this concept to deal with particularities (for instance, a CD-ROM is read-only or a network drive shouldn't be 
scanned all over the day for performance reasons) and to provide a friendlier graphical interface (different icons by device type).</div>

A device usually contains MP3, OGG and others supported audio files, M3U playlist files and JPG/ GIF/PNG image files for covers.

A 'collection' is the sum of all the devices you created.

If your music is distributed into several directories, you'll have to create a device by directory or create a device for a common parent directory of your music files. A good practice is to centralize all your music under a common directory (like "<home>/My Music" in most operating systems) and to create a single device from this directory.

## Creating and configuration devices
Devices can be created either using the [Device view](view_devices.html) in the Configuration perspective or 
using the quick start devices wizard (``Configuration`` top menu / ``Devices wizard``).

<div class='info'>Note for Windows users: map your drives to a static Letter to make sure the drive letter 
doesn't change, otherwise, the music will no more be available. See this [Microsoft documentation](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/dm_drive_letter.mspx?mfr=true).</div>

## Refreshing devices
Jajuk uses an automatic indexing system: music files tags are not read again at each startup but Jajuk builds a collection to store their content 
(stored on the disk by default in [[home directory](/homedir.html)]``/.jajuk/collection.xml``). 
It makes Jajuk able to start up in only few seconds and be aware of any tracks from a several hundreds of GB music collection. It is also used to perform searches and filtering on the entire collection in real time.

Jajuk only knows files from refreshed devices: if you copy a file on your disk from another app, Jajuk will be aware of it only after the next device refresh. 

Device refreshing is automatic and scanning frequency can be set in the [Device view](view_devices.html). 

Default frequency for hard disk devices (directory devices) are 30 secs (0.5 minutes) and the scan often takes less than few secs so if you remove or add some files in this device, the change will be reflected into the application after about 30 seconds. Note that frequency used for network drives are much longer (default: 5 minutes) because scanning them takes a longer time and consumes network bandwidth.

Jajuk doesn't read again tags for known files. If you changed them from another app, you can force Jajuk to read them again using the "Force refresh" function in Physical Files Tree view on devices nodes or from the [Device view](view_devices.html).

Mount/unmount devices
Mount a device means to make it available and unmount it means disconnect it. You can configure devices in the Device view so they will be automatically mounted at startup. Some device can naturally be auto-mounted: a directory from your internal hard disk for example. On the other hand, we highly discourage to auto-mount some others like CD or USB keys because they are likely to be unavailable at next startup. When a mount is required on a device, Jajuk will check it is physically available (for a CD for instance) and try to access it if required. If you try to play a track located in an unmounted device, Jajuk will ask you if you want it to mount this device. In all cases, you will get an error message if the device cannot be mounted.

You can mount or unmount a device from the physical perspective with "Mount or Unmount" commands from contextual menu on selected device or from the view_devices in the Configuration perspective.

<div class='info'>The mount/unmount commands are only at the Jajuk level, Jajuk never actually sends commands to the operating system level (like mount or umount commands under Linux). It is just a flag used by Jajuk to know if it should consider a device as accessible or not.</div>

## Synchronizing devices
When creating a device (see device view documentation for more information), you can tell Jajuk to make it synchronized with another device. This allows you to copy by a single click all the new files from source device to the other. Note that you can perform partial synchronization by desynchronizing some directories in the Physical perspective / Physical Files Tree view with contextual menu on directories (watch the selection box in the Information view at the bottom to know recursive size of a selection). You can also perform bidirectional synchronizations (all new files from a device are copied to the other).

You can synchronize two devices from the physical perspective with "Synchronize" command from contextual menu on selected device or from the view_devices in the Configuration perspective.

## Collection backup and restore
All your collection and properties on your tracks are stored in the collection files (``collection*.xml`` files). By default Jajuk performs a backup of this collection file (collection-{date}.xml files) until it takes 20MB on the disk. You can set maximum backup size in the [Preferences view /Advanced tab](view_preferences.html#advanced-tab).

Restore: if you just made a manipulation error and still in Jajuk, close it. Then override collection.xml file with ``collection-{date}.xml``.

It is highly recommended to include your [[home directory](/homedir.html)]``/.jajuk directory`` (or any other collection location) into a periodic backup.

Go back to the [TOC](/manual/main.html)