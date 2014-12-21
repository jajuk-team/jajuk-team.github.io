---
title: New features 1.9 - Jajuk
layout: default
---

<a name="top"></a>

# New Features Highlights in Jajuk <Killer Queen> 1.9

## Better table/tree synchronization

![Sync tree table](/images/jajuk_sync_tree_table.png)

- The tables and trees graphical synchronization can be controlled independently on each table or tree view (thanks to the new toggle button at the top of each tree or table view).
- Even playlists are managed : selecting a playlist in the playlist view expand the Files tree view accordingly.
- The synchronized state of each view is saved between sessions.
- New "collapse all" button in trees 

Note : The old "table/tree sync" option no more exists.

## Repeat all feature

New "repeat all" mode : Play the entire queue in a loop.

Note : We also re-introduced the Continue mode toggle button directly into the command panel (in 1.8, it was only available from Modes menu).

![Repeat all feature](/images/jajuk_repeat_all.png)

## Drag and drop enhancements

- Drop to given position 

Note : if you already use Jajuk, disable the "Push on drag and drop" option in Preferences view / "Options" tab to make it work this new way.

- Support for multiple rows selection dragging (only from tables, not trees).
- Dragging of a playlist to a queue now push the entire playlist content.
- Dragging of every item in trees or tables (albums, artists, directories, device ...) is now supported and is done recursively. 

## New patterns

- Pattern for balloon display
- Pattern for notification messages (lower part of the main window) 

![New patterns](/images/jajuk_new_patterns.png)

## New notification system

- Notifications can now be set in the preferences view.
- Three modes : none notification, toast (new mode) or systray balloon. 

![Repeat all feature](/images/jajuk_notification_system.png)

## Extra tags : it is now possible to see any tag from jajuk

![Extra tags](/images/jajuk_extra_tag_conf.png)

Note : Jajuk supports now all tags supported by the jaudiotagger tag library

## Read covers from tags

If a cover is stored in your music file, Jajuk can display this cover now. You can also set a tag cover as the default cover for the whole album.

## Mac OSX support

Jajuk Mac experience has been largely improved :

- mplayer now embedded with Jajuk, no more need to install it separately
- Many fixes of OSX-specific issues 

## Prepare Party reworked

"Prepare Party" exports sets of music to an external location and create a playlist so it can be played out from Jajuk. This feature was fully rewritten for 1.9 and is now much more powerful. It is also suitable for exporting parts of the collection for playing on MP3 players. Some features are specifically geared towards more limited devices, e.g. by limiting the chosen media types to only one media format if the MP3 player can not cope with other formats.

- You can choose from many different sources, among them Ambiences, DJs, Playlists, New files, BestOf, Queue: 

![Prepare Party 1](/images/jajuk_prepare_party_1.png)

- You have many options for limiting the amount of data as well as converting the music files to other formats 

![Prepare Party 2](/images/jajuk_prepare_party_2.png)

- And finally you can choose where to put the files: 

![Prepare Party 3](/images/jajuk_prepare_party_3.png)

The functionality is available as part of the "Tools" menu and in the Playlist View, where it opens with the current playlist pre-selected.

## Lyrics view improvements

![Lyrics view improvements](/images/jajuk_lyrics_view.png)

- Jajuk now supports read/write lyrics from/to tags
- Support of lyrics read/write to txt files if tags are not available or writable
- Lyrics deleting support 

## Slimbar improvements

![Slimbar improvements](/images/jajuk_slimbar_improvements.png)


## Donation feature

- Donation window is available from help menu 

![Jajuk donation](/images/jajuk_donation.png)

## Others enhancements includes :

- Baning a track now stops it immediately
- Ctrl-F keystroke focuses the search box
- Covers mirroring now configurable in Preferences view and a fast switch is also available by clicking on the cover in the Covers view.
- New minimize to tray option
- Memory footprint reduction and many small memory leaks fixed
- Faster GUI
- Large code refactoring and unit test coverage

<hr />

Go back to [the top](#top "New features 1.9")
