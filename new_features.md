---
title: New features - Jajuk
layout: default
---

<a name="top"></a>

# New Features Highlights in Jajuk <Gute Laune> 1.10

## Webradios enhancements

### New Webradio view

![New Web Radio View](/images/jajuk_webradio_view.png)

- Presets and custom webradios are listed in a table and can be launched by double-cliking
- New wizard to add custom radio
- Shows a genre for each webradio
- Supports radio filtering by any radio property (genre, name...)
- Columns can be selected and the selection is saved
- This new view is displayed by default along with the Queue view 

### Webradio current track

The webradio current tracks (if provided by the station) are now displayed in the information panel, window title and few others places.
![Webradio current track](/images/jajuk_webradio_current_track.png)

### Webradio button now available from slimbar

![Jajuk slimbar](/images/jajuk_slimbar.png)

## Stop after this track

A new feature is available from queue view : "Stop after track" makes Jajuk stops only when current track is done.

![Jajuk stop after](/images/jajuk_stop_after.png)

## Better Animation/title view experience

- The "Animation" view has been renamed "Title" view
- Animation stops on left click
- Animations can be controlled using the new "Enable Title view animation effect" in Preferences view/ GUI tab (effect disabled by default, so enable it if you want to keep the effects running)
- This option affects also the full screen view 

![Jajuk title view experience](/images/jajuk_enable_title_view_animation.png)

## Rating system enhancements

### Export/import of ratings

It is now possible to import or export ratings from the Preference view / Ratings/history tab. This allows to transfer ratings from one installation to another and also to combine ratings from multiple installations, ratings are merged based on the file-contents via hashing.

![Jajuk export/import of ratings](/images/jajuk_export_import_ratings.png)

### New manual rating system

From Jajuk 1.10 aka "Gute Laune", a manual rating system is enabled using preference level detailed below. It is available from the Preferences View / History/Ratings tab. For instance, setting "Classic" preference forces rating to 100% and setting preference to "Good" force it to 50%.

![New manual rating system](/images/jajuk_new_manual_rating.png)

### Preference is available from the "Preferences" menu

This allows to get the preference value without having to expand the preferences menu.

![Preferences menu](/images/jajuk_preferences_menu.png)

## Mirror option now available from fullscreen mode

Like in cover views, it is now possible to switch covers display between mirror effect (default) and regular display by clicking on it.

## Last.fm exclusion

It is now possible to exclude some tracks from audioscrobbling (last.fm submission) using the new "scrobble" properties available from tracks properties dialog.

![Last.fm exclusion](/images/jajuk_last_fm.png)

## Playlist shuffle feature

A new shuffle button in playlist view allows fast shuffling of a playlist during its edition.

![Playlist shuffle feature](/images/jajuk_playlist_shuffle.png)

## Custom properties available in patterns

Custom properties can be used in patterns on current playing track.

![Custom properties](/images/jajuk_custom_properties.png)

## It is now possible to disable the splashscreen

Use the new "Show splashscreen at startup" GUI option if you want to avoid startup splashscreen.

![Show splash screen](/images/jajuk_show_splashscreen.png)

## Confirmations enhancements

![Confirmations enhancements](/images/jajuk_confirmations_enhancements.png)

- Reset "Don't show again" : Sometimes, Jajuk shows a dialog with the "don't show again" option. It is now possible to reset the choices from the preference view / Confirmations tab to get them back.
- New "Before writing one or more tags" confirmation : If enable, a dialog is shown before actually writing tags into audio files. 

## Cover view busy label

Instead of previous searching label, a busy label turns inside the entire cover view for a better visual effect and to avoid being stuck with previous track cover.

![Cover view busy](/images/jajuk_cover_view_busy.png)

## Fade out

Sound is now faded out when stopping or pausing for a better audio experience (there is no GUI option to disable it but the "jajuk.options.fade_out" special option can be set).

## Bit perfect

The new Sound/"Bit perfect" option make sure you get the best possible sound. It disables any gain or sound processing option from mplayer. Note that under this mode, sound volume is disabled, you'll have to set volume from your operating system mixer.

![Bit perfect](/images/jajuk_preferences_bit_perfect.png)

## Keep the original file time when changing tag

The new "Preserve files date" option in Preference view / Options tab allows to keep an audio file date even when setting its tags.

![Preserve files date](/images/jajuk_preserve_files_dates.png)

## Show videos option

Jajuk has not been designed for videos in mind even if videos are managed. Reading video in continue mode for instance can be annoying. The new "Show videos" option in Preference view / Options tab (false by default) allows to drop Jajuk video supports. Videos are then no more recognized as Jajuk known file and are no more visible from the graphical interface.

![Show videos option](/images/jajuk_show_videos.png)

## Systray click force display option

This new option in GUI tab force main window display when left-clicking on the systray instead of displaying/hiding it (default).

![Force display option](/images/jajuk_force_display.png)

## Bitrate visible from duplicate finder

The bitrate (quality) of found audio files are now displayed in duplicate finder dialog so it is easy to select to keep files of a quality instead of another.

![Force display option](/images/jajuk_bitrate_visible.png)

## Others enhancements includes :

- A better filtering focus behavior in table views
- Removal of the annoying ctrl-backspace keystroke
- Lyrics view now displayed by default with cover view in Files and Tracks perspectives
- The "push on selection" option is now honored in catalog view
- The refresh dialog now displays the number of files having disappeared since the last refresh
- The confusing "Show album popups" option has been renamed "Show large tooltips when hovering over albums"
- A new shortcut : ctrl alt N force current track notification
- A lot of code refactoring and a few performance enhancements 

[New Features Highlights in Jajuk \<Killer Queen\> 1.9](/new_features_1.9.html)

<hr />

Go back to [the top](#top "New features")

