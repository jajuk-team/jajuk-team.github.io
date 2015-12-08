---
title: Preferences view
layout: default
---
Go back to the [TOC](/manual/main.html)

# The Preferences view
This view contains all the Jajuk preferences. You will have to press the _Apply_ button in the lower part of the view to actually apply changes. You can reset everything to the 'factory' defaults by clicking on the _restore defaults_ button (the changes are then applied).

<div class='info'>Security notice: all passwords set here (proxy password, Last.FM password...) are *not* stored in clear in the jajuk configuration files but obfuscated.</div>

<div class='info'>Note that few [hardly used options](http://jajuk.info/index.php/Special_options) are not accessible using the graphical interface but can be set by editing the configuration file.</div>

### Options tab
This tab contains some general options:

- **Language** [default=your system locale if supported or English otherwise]: Interface language. Needs a restart to be taken into account.
- **Only show available tracks** [default=false]: If checked, Jajuk hides all items located on unmounted devices.
- **Push on selection** [default=false]: If checked, Jajuk default behavior when double-clicking on a track or when selecting an item in instant search box is to push it into the queue, not to play it.
- **Push on drop** [default=false]: If checked, Jajuk default behavior when drag and dropping a track is to push it into the queue, not to play it.
- **Enable Hotkeys**[Windows only] [default=false]: If set, keystrokes (see list in [keys shortcuts](keys.html)) like ``F8`` work even when jajuk window has not the focus.
- **Use parent directory as album name** [default=true]: If the album tag is not available, take parent directory name as album name.
- **Show videos** [default=false]: If unset, jajuk don't take video-types files into account in the collection.
- **Preserve file date** [default=false]: Preserve files "last modification date", even when setting tags.

### Modes tab
This tab contains player engine preferences:

- **Intro begin position (%)** [default=0]: For intro mode, beginning track position in percent.
- **Intro length (sec)** [default=20]: For intro mode, track length in seconds.
- **Best of playlist size** [default=20]: Size of the _bestof_ smart playlist (see [using playlists](using_playlists.html))
- **Time limit of novelties (days)** [default=30]: After this number of day since first refresh, the tracks are no more novelties and will not be chosen any more by the novelties function (Command view).

### Sound tab
This tab contains Sound preferences:

- **Cross-fade duration** [default=5]: Cross-fade duration in seconds between two tracks. Zero means no cross-fade. 
- **Use Audio normalization** [default=false]: Enables mplayer normalization to avoid big gain differences between tracks.
- **Enable bit-perfect** [default=false]: Disable the mixer (sound volume) and any other option that could affect sound quality like audio normalization. Use your OS mixer to change volume or mute once enabled.

### GUI tab
- **Show large tooltips when hovering over albums** [default=true] : Should Jajuk show popups on thumbs ? (mainly in [view catalog](view_catalog.html) and [view suggestions](view_suggestions.html))
- **Show splash screen at startup** [default=true] : Show splash screen at startup in main Window mode (it is always disabled in slimbar or full screen mode).
- **Font size** [default=12]: font size used mainly in tree and table views
- **Notification Popup on track change**[default=None]: Select the type of notification at track change : none, system balloon or toast (a toast is a notification popup that appears briefly on the screen and disappears by itself).
- **Theme** [default=Nebula]: Color theme to use
- **Perspective bar icons size** [Default=32 pixels, from 16 to 56 pixels]: set here the size of the perspective chooser buttons on the left. Under 32 pixels, the text under buttons is no more displayed.
- **Catalog view preferences**
    - '**Catalog view page size** [default=200]: set here the number of albums by page in the [view catalog](view_catalog.html). Zero means all in one
    - The **Refresh thumbnails** button deletes all thumbnails (any size) so they will be rebuilt at next display.

- **Title view preferences**
    - '**Enable Title view animation effect** [default=false]: whether the [title view](view_title.html) show animated text.

### Startup tab
This tab is used to select Jajuk startup mode [default=Last one at last position]:

- **Nothing**: no track at all is launched at startup.
- **Last one from beginning**: last track is fully played.
- **Last one at last position**: last track is launched at position you stopped it when exiting Jajuk.
- **Shuffle track**: A shuffle track from the entire collection.
- **Best of track**: A track from your best of..
- **Novelties**: A track from your novelties.
- **Track/radio**: choose a track or a webradio by making a search in the text field.

### Patterns tab
This tab is used to fine tune several patterns

- **File Organizer** : set pattern used when using the [files organizer](files_organizer.html).
- **Title view** : set text pattern of [Title view](view_title.html) (variables are the same that Organizer's pattern)
- **Frame title** : set text pattern of Jajuk main window.
- **Balloon pattern** : This pattern set the text to be displayed by balloon notifier (you can select the notifier in the GUI tab) at track change. Note that the Toast notifier is not affected by this setting as it uses a static built-in pattern to render fine HTML pattern with image.
- **Information pattern** : This pattern set the text to be displayed in the information view (lower part of the screen).

### History/Ratings tab
See also the [Jajuk rating system](ratings.html).

- **History duration** [default=-1]: Number of days you want to keep history. -1: infinite, 0: no history.
- **Clear History** button: Clears the history bar.
- **Reset ratings** button: Reset all tracks ratings to zero.
- **Reset preferences** button: Reset user-defined preferences.
- **Export ratings** button: Write ratings of all tracks to a file so you can import it to another installation of Jajuk that has the same files.
- **Import ratings** button: Read in ratings that were exported from another installation of Jajuk. The rating of all matching files will be updated.

### Last.FM tab
- **Enable Last.FM information queries**: Allow jajuk to make queries to Last.FM web services in order to display various information on playing artist like similar artists and others albms in the [Suggestions view](view_suggestions.html)
- **Scrobble my listening**: Allow Jajuk to send information on titles you listen to Last.FM website in order to feed your Last.FM profile (check [http://last.fm](http://last.fm) website). Jajuk caches scrobbles when offline and submit them back at next online jajuk session startup.
- **Last.FM user name**: Last.FM login name you used when creating your Last.FM profile
- **Last.FM password**: Last.FM password you used when creating your Last.FM profile

### Webradios
- **Reload presets** button : Reload presets webradios from Jajuk website (keep custom keywords).

### Covers tab
This tab is used to tune covers (see [view_cover](view_cover.html)).

- **Shuffle cover** [default=false] : Shuffle covers when playing a new album.
- **Grab covers online** [default=true] : Grab remote covers from the Web.
- **Mirrow covers** [default=false] : If checked, the cover will be tilted and mirrowed.
- **Mirrow covers in full screen mode** [default=true] : If checked, the cover will be tilted and mirrowed in full screen mode.
- **Save covers Windows Explorer friendly** [default=false] : Save downloaded covers as folder.jpg/png/... so that the windows explorer uses them as directory icon.
- **Cover size** [default=medium or large] : Cover size filter for online searches
- **Default cover file names** [default=front;cover;folder;back;jajuk] : Jajuk takes as default covers files which name contains this text (without extension). Several values separated by semicolons can be provided. Example : ``Folder;front``.

### Confirmations tab
This tab is used to tune confirmations.

- **Before physically deleting a file** [default=true]: Ask before physically and definitively deleting a file.
- **Before exiting Jajuk** [default=false]: Ask before quitting Jajuk.
- **Before removing a device** [default=true]: Ask before removing a device. No data will be deleted on your disk but the device will be deleted from the Jajuk database.
- **Before physically deleting a cover** [default=true]: Ask before physically and definitively deleting a cover (image file).
- **Before clearing history** [default=true]: Ask before clearing history in history bar.
- **Before reseting ratings** [default=true]: Ask before reseting all tracks ratings to zero.
- **Before organizing files** [default=true]: Ask before organizing files (see [Files organizer](files_organizer.html))
- **Before writting one or more tags** [default=false]: Ask before writing a tag into an audio file)
- **Reset "Don't show again" choices** button : This makes possible to show again the choices you asked to hide.

### Network tab
This tab is used to tune network options (useful if used inside a corporate network for example)

- **Disable any Internet access from Jajuk** : disables any Internet access from Jajuk (LastFM, covers or lyrics download...).
- **Connection timeout in seconds** [default=10]: Timeout in seconds when establishing a connection to a server
- Select your HTTP proxy [Default: no proxy] : **No proxy** **HTTP proxy** or **SOCKS** proxy
- **Proxy host name** [default=**proxy**, only if Use a HTTP proxy is set]: Proxy host name or IP address.
- **Proxy port** [default=**3128** (sometimes ``8080`` for some proxies), only if Use a HTTP proxy is set]: Proxy port
- **Proxy user name** [no default]: Proxy user name
- **Proxy password** [no default]: Proxy password

### Advanced tab
This tab is used to tune some Jajuk advanced parameters

- **Backup size (MB)** [default=40MB, only if _Backup collection file_ option is set]: Maximum backup size of all collection file backups (collection_&lt;date&gt;.xml files in jajuk configuration directory).
- **Log level** [default=Warning in normal mode, debug in debug mode (-debug)]: Set the verbosity of logs in your ``[Jajuk repository]/jajuk.log`` file. Please set to _Debug_ before sending us a bug.
- **Mplayer path** [default=none]: force mplayer path
- **Mplayer arguments** [default=none]: Additional MPlayer arguments (see mplayer documentation for details):
    - to set your sound server options like `-ao esd` or `-ao arts`
    - to have only the sound of video: `-novideo`
    - to configure a sound equalizer `-af equalizer=0:0:0:0:0:-1:-1:-1:-1:-1`
    - for audio normalization use `-af volnorm`

- **Environment variables** [default=nonel]: Set environment variables used by the audio player (ARTS_SERVER under KDE or ESPEAKER under Gnome for ie). Format: ``var1=xx var2=yyy...``
- **Jajuk configuration directory** [default=user home directory]: Set the directory containing Jajuk configuration and collection library. This directory contains one or more Jajuk _repository_ (.jajuk directories, one for each test release and one single for final release). Note that you can also force this path from the command line, see [Hidden options](hidden_options.html).
- **Explorer executable path** : Set path to the program handling 'Open in Explorer' feature (in Files tree view for instance). Note that in most environments, proper path is token by default and you don't need to edit this option. XFCE Example : ``/usr/bin/thunar``

- **Use Regexp in filters** [default=false]: Use regexp strings like ``.*foo.`` in the filter field of the Table view.
- **Check Jajuk updates** [default=true]: Allow Jajuk at every startup to check on the jajuk website if a new release becomes available (can be forced manually using the Help menu / Check for updates)
- **Discovery date = file date** [default=false]: If checked, jajuk use the file date (in the operating system meaning) as discovery date, not the current date. This date is used for novelties features or for statistics.

Go back to the [TOC](/manual/main.html)