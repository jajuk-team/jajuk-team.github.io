---
title: New features - Jajuk
layout: default
---

# New Features Highlights in Jajuk <Gute Laune> 1.10

## Webradios enhancements

### New Webradio view

[New Web Radio View](/images/ss_webradio_view.png)

- Presets and custom webradios are listed in a table and can be launched by double-cliking
- New wizard to add custom radio
- Shows a genre for each webradio
- Supports radio filtering by any radio property (genre, name...)
- Columns can be selected and the selection is saved
- This new view is displayed by default along with the Queue view 

Webradio current track

The webradio current tracks (if provided by the station) are now displayed in the information panel, window title and few others places. Image:ss_webradio_current_track.png
Webradio button now available from slimbar

Image:ss-1_10-1.png
Stop after this track

A new feature is available from queue view : "Stop after track" makes Jajuk stops only when current track is done.

Image:ss_stop_after.png
Better Animation/title view experience

- The "Animation" view has been renamed "Title" view
- Animation stops on left click
- Animations can be controlled using the new "Enable Title view animation effect" in Preferences view/ GUI tab (effect disabled by default, so enable it if you want to keep the effects running)
- This option affects also the full screen view 

Image:ss-1_10-21.png
Rating system enhancements
Export/import of ratings

It is now possible to import or export ratings from the Preference view / Ratings/history tab. This allows to transfer ratings from one installation to another and also to combine ratings from multiple installations, ratings are merged based on the file-contents via hashing.

Image:ss-1_10-20.png
New manual rating system

From Jajuk 1.10 aka "Gute Laune", a manual rating system is enabled using preference level detailed below. It is available from the Preferences View / History/Ratings tab. For instance, setting "Classic" preference forces rating to 100% and setting preference to "Good" force it to 50%.

Image:ss-1_10-3.png
Preference is available from the "Preferences" menu

This allows to get the preference value without having to expand the preferences menu.

Image:ss-1_10-4.png
Mirrow option now available from fullscreen mode

Like in cover views, it is now possible to switch covers display between mirror effect (default) and regular display by clicking on it.
Last.fm exclusion

It is now possible to exclude some tracks from audioscrobbling (last.fm submission) using the new "scrobble" properties available from tracks properties dialog.

Image:ss-1_10-2.png
Playlist shuffle feature

A new shuffle button in playlist view allows fast shuffling of a playlist during its edition.

Image:ss-1_10-6.png
Custom properties available in patterns

Custom properties can be used in patterns on current playing track.

Image:ss-1_10-7.png
It is now possible to drop the splashscreen

Use the new "Show splashscreen at startup" GUI option if you want to avoid startup splashscreen.

Image:ss-1_10-8.png
Confirmations enhancements

Image:ss-1_10-9.png

- Reset "Don't show again" : Sometimes, Jajuk show a dialog with the "don't show again" option. It is now possible to reset the choices from the preference view / Confirmations tab to get them back.
- New "before writing tags" confirmation : If enable, a dialog is shown before actually writing tags into audio files. 

Cover view busy label

Instead of previous searching label, a busy label turns inside the entire cover view for a better visual effect and to avoid being stuck with previous track cover.

Image:ss-1_10-10.png
Fade out

Sound is now faded out when stopping or pausing for a better audio experience (there is no GUI option to disable it but the "jajuk.options.fade_out" special option can be set).
Bit perfect

The new Sound/"Bit perfect" option make sure you get the best possible sound. It disables any gain or sound processing option from mplayer. Note that under this mode, sound volume is disabled, you'll have to set volume from your operating system mixer.

Image:ss-1_10-11.png
Keep the original file time when changing tag

The new "Preserve files date" option in Preference view / Options tab allows to keep an audio file date even when setting its tags.

Image:ss-1_10-12.png
Show videos option

Jajuk has not been designed for videos in mind even if videos are managed. Reading video in continue mode for instance can be annoying. The new "Show videos" option in Preference view / Options tab (false by default) allows to drop Jajuk video supports. Videos are then no more recognized as Jajuk known file and are no more visible from the graphical interface.

Image:ss-1_10-13.png
Systray click force display option

This new option in GUI tab force main window display when left-clicking on the systray instead of displaying/hiding it (default).

Image:ss-1_10-14.png
Bitrate visible from duplicate finder

The bitrate (quality) of found audio files are now displayed in duplicate finder dialog so it is easy to select to keep files of a quality instead of another.

Image:ss-1_10-15.png
Others enhancements includes :

- A better filtering focus behavior in table views
- Removal of the annoying ctrl-backspace keystroke
- Lyrics view now displayed by default with cover view in Files and Tracks perspectives
- The "push on selection" option is now honored in catalog view
- The refresh dialog now displays the number of files having disappeared since the last refresh
- The confusing "Show album popups" option has been renamed "Show large tooltips when hovering over albums"
- A new shortcut : ctrl alt N force current track notification
- A lot of code refactoring and a few performance enhancements 

New Features Highlights in Jajuk <Killer Queen> 1.9
Better table/tree synchronization

Image:ss_sync_tree_table.png

- The tables and trees graphical synchronization can be controlled independently on each table or tree view (thanks to the new toggle button at the top of each tree or table view).
- Even playlists are managed : selecting a playlist in the playlist view expand the Files tree view accordingly.
- The synchronized state of each view is saved between sessions.
- New "collapse all" button in trees 

Note : The old "table/tree sync" option no more exists.
Repeat all feature

New "repeat all" mode : Play the entire queue in a loop.

Note : We also re-introduced the Continue mode toggle button directly into the command panel (in 1.8, it was only available from Modes menu).

Image:ss_repeat_all.png
Drag and drop enhancements

- Drop to given position 

Note : if you already use Jajuk, disable the "Push on drag and drop" option in Preferences view / "Options" tab to make it work this new way.

- Support for multiple rows selection dragging (only from tables, not trees).
- Dragging of a playlist to a queue now push the entire playlist content.
- Dragging of every item in trees or tables (albums, artists, directories, device ...) is now supported and is done recursively. 

New patterns

- Pattern for balloon display
- Pattern for notification messages (lower part of the main window) 

Image:ss_new_patterns.png
New notification system

- Notifications can now be set in the preferences view.
- Three modes : none notification, toast (new mode) or systray balloon. 

Image:ss_notif.png
Extra tags : it is now possible to see any tag from jajuk

Image:extra_tag_configurations.png

Note : Jajuk supports now all tags supported by the jaudiotagger tag library
Read covers from tags

If a cover is stored in your music file, Jajuk can display this cover now. You can also set a tag cover as the default cover for the whole album.
Mac OSX support

Jajuk Mac experience has been largely improved :

- mplayer now embedded with Jajuk, no more need to install it separately
- Many fixes of OSX-specific issues 

Prepare Party reworked

"Prepare Party" exports sets of music to an external location and create a playlist so it can be played out from Jajuk. This feature was fully rewritten for 1.9 and is now much more powerful. It is also suitable for exporting parts of the collection for playing on MP3 players. Some features are specifically geared towards more limited devices, e.g. by limiting the chosen media types to only one media format if the MP3 player can not cope with other formats.

- You can choose from many different sources, among them Ambiences, DJs, Playlists, New files, BestOf, Queue: 

- You have many options for limiting the amount of data as well as converting the music files to other formats 

- And finally you can choose where to put the files: 

The functionality is available as part of the "Tools" menu and in the Playlist View, where it opens with the current playlist pre-selected.
Lyrics view improvements

- Jajuk now supports read/write lyrics from/to tags
- Support of lyrics read/write to txt files if tags are not available or writable
- Lyrics deleting support 

Slimbar improvements

Image:slimbar_new_1.9.png
Donation feature

- Donation window is available from help menu 

Image:donation.png
Others enhancements includes :

- Baning a track now stops it immediately
- Ctrl-F keystroke focuses the search box
- Covers mirroring now configurable in Preferences view and a fast switch is also available by clicking on the cover in the Covers view.
- New minimize to tray option
- Memory footprint reduction and many small memory leaks fixed
- Faster GUI
- Large code refactoring and unit test coverage 