---
title: Devices view
layout: default
---
Go back to the [TOC](/manual/main.html)

# Devices view
This view displays devices you created and manages them. Please read the using devices to learn about devices principles.

Note you can also create Folder devices using the quick start devices wizard (top menu, Device wizard).

## The devices repository
In the lower part of the devices view, you will find devices you created. The green arrow on the bottom of a device means it is now mounted.

![Image](/images/New_64x64.png) Click on this shortcut to create a new device

![Image](/images/Cdrom_mount_64x64.png) Data CDROM

![Image](/images/Folder_mount_64x64.png) Folder from your hard disk

![Image](/images/Nfs_mount_64x64.png) Network drive (Netbios, Samba, NFS...). Under Windows, use drive letter path (like ``T:\...``) but **not** network favourites path or UNC paths (like ``\\server\directory``)

![Image](/images/Player_mount_64x64.png) MP3 Player.

<div class='info'>Note that you can use a player with jajuk only if it is seen by your OS as a simple USB drive, not like iPods that use proprietary protections.</div>

![Image](ext_dd_mount_64x64.png External Hard Disk or storage device like USB keys (mainly on USB or Firewire)

## Contextual menu on devices features
Full documentation of the following actions in the section using devices.

- **Mount**: Mount this device
- **Unmount**: Unmount this device
- **Test**: Test if this device is available
- **Force Refresh**: Perform a forced refresh on this device to read tags again.
- **Synchronize**: (available only if this device is configured to synchronize with another device)
- **Remove device**: Remove this device from your collection. No data will be deleted from your hard disk. You can set a confirmation dialog (is the default) in view parameter / Confirmations tab.
- **Configuration**: Manage device configuration

## The device configuration wizard
This window appears when you create a new device or when you update some properties of an existing device. You can show device properties by double clicking on it, by using contextual menu, Get Properties or by selecting the device and using the Properties button in the Control Pane. It features:

- **Device type** combo box (Cannot be changed after creation): choose the device type you wish to create
- **Device name** (Cannot be changed after creation): Enter name of the device. For example "CD A" for a CD or "Laptop" for a directory
- **Device location** (Cannot be changed after creation): full path to the device. For example "/data/music" under Unix or "d:\music" under Windows. You can use the directory selector using the button on the right
- **Refresh every (min)** : set refreshing frequency for jajuk to scan device searching for new or removed files (0: no automatic refresh). Defaults: 0.5 min for a directory-type device (hard drive), 0 for a CD, 5 minutes for network drives, 3 minutes for external hard disks or players
- **Perform an instant refresh** (default = true): Perform a device refresh immediately after creating the device. This is recommended. Note that this should take a while, especially for the first time.
- **Auto mount at startup** (checked by default for some types): Perform an auto-mount when starting Jajuk. This is recommended for directories or eventually external devices if always plugged but avoid this for CD or devices that can be unplugged or changed quite often.
- **Synchronized with** combo box : if you have more than one device, you will be able to synchronize them. The current device is the target device and the other one the source device
  <div class='info'> You can ignore recursively some directories when performing synchronization (if the two synchronized devices have not the same capacity for example) by desynchronizing directories in the Physical Files Tree / contextual menu on directories.</div>
  <div class='info'> Synchronization never performs deletes so if you renames some files on the source device, you will get both older and newer version in the target device after synchronization</div>
  - **Unidirectional synchronization**: all new files from the source device are copied to this device.
  - **Bidirectional synchronization**: all new files from one device are copied to the other.

Go back to the [TOC](/manual/main.html)