---
title: Files tree view
layout: default
---
Go back to the [TOC](/manual/main.html)

# Files tree view
This view can be found in the _Files perspective_. It allows to select or browse devices upon a physical point of view. In this view, you will find:

- **Devices** as you created them in the Device view. Devices contain directories.
- **Directories**
- **Audio files** that Jajuk supports
- **Playlists**

### Notes
- Cover files are not visible in the tree
- Tree configuration (nodes expands, collapses) is saved for next Jajuk session

You can select any item in the tree, all contextual menu action will be applied recursively. For example, if you selected both your _ROCK_ main directory and your _POP_ main directory, then you right click and select **Play shuffle**, Jajuk will play randomly all your _ROCK_ and _POP_ tracks.

## Dragging and dropping items
At any time, you can drag one or more items (and drag them into the [Queue view](view_queue.html) or 
the [Playlists view](view_playlists.html).for instance). 

Press CTRL or SHIFT to select several items. A drop into the [Queue view](view_queue.html) will result into an immediate play of your selection. 

**Play** or **Push** default behavior during a drag and drop can be set in the [Preferences view](view_preferences.html), ``Mode`` tab.

## Graphical synchronization with the table
If the tree view synchronization toggle button is set, a click in the Table causes the tree to auto-expand to show associated items.

- The tables and trees graphical synchronization can be controlled independently on each table or tree view.
- Even playlists are managed : selecting a playlist in the playlist view expand the Files tree view accordingly.
- The synchronized state of each view is saved between sessions.
- The "collapse all" button allow to quickly collapse recursively the entire tree.

## Contextual menu
Many actions (like **Play**, **Push**, **Create a report** or **Properties**) are available from the different items using 
contextual menu (right click). The features can depend on the nature of the item.

Items contextual menu includes :

### Devices only
- **Configure**: Open Device wizard to configure device.
- **Mount**: perform a mount (see [using devices](devices.html))
- **Unmount**: perform an unmount (see [using devices](devices.html))
- **Force Refresh**: Perform a device forced refresh to read tags again (see [using devices](devices.html))
- **Synchronize**: Perform a synchronization (see [using devices](devices.html)). It is enabled only if the device is configured to be synchronized with another one.
- **Test**: check (or "ping") the device to check if it is really available
- **Get tags online**: Search tags online (CDDB) for tracks found at device root
- **Removed device** : Fast remove of a device from the collection without using the [view devices](View_devices.html)

### Directory only
- **Force Refresh**: Perform a refresh for this directory and its sub-directories only (see [using devices](devices.html))
- **Get tags online**: Search tags online (CDDB) for tracks found in this directory
- **Desynchronize**: flag this selection so it will not taken into account at next synchronization
- **Resynchronize**: reset desynchronize flag
- **Organize files**: organize files according tags (see [files organizer](files_organizer.html))

#### Any
- **Play**: Stop current track and play selection
- **Push**: Don't stop current track but simply add the selection into the queue
- **Play shuffle**: Stop current track and play selection randomly (note that this mode is automatically used when playing a track if you set ``shuffle mode`` in [Commands view](commands.html))
- **Play repeat**: Stop current track and play selection in a loop (note that this mode is automatically used when playing a track if you set ``repeat mode`` in [Command view](commands.html))
- **Copy**: copy selection
- **Cut** : cut selection
- **Paste**: paste selection
- **Rename**: rename selection
- **Delete**: delete selection
- **Add** to favourites: Add recursively items to ``bestof playlist``
- **Create a report**: Create an HTML or XML report
- **Properties**: show item properties

Go back to the [TOC](/manual/main.html)