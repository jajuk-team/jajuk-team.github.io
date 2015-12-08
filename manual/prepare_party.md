---
title: Prepare a party
layout: default
---
Go back to the [TOC](/manual/main.html)

# Prepare a party
The **Prepare party** is functionality to export sets of music along with a generated playlist to an external location for playing outside of Jajuk. It is also suitable for exporting parts of the collection for playing on MP3 players. Some features are specifically geared towards more limited devices, e.g. by limiting the chosen media types to only one media format if the MP3 player can not cope with other formats.

## How to prepare a party
There are two ways to start exporting media files:

1. By choosing ``Prepare Party`` from the ``Tools`` top menu, you can start to prepare a party from a wide range of sources

2. By choosing the ``Prepare Party`` icon ![image:ext_drive_16x16.png](/images/Ext_drive_16x16.png) in the [Playlist View](view_playlists.html), you can export the set of files selected in the current playlist.

### Define which media files to choose
If the party is started from the ``Tools`` top menu, you get a number of choices for how the media files are selected.

You can choose from many different sources, among them Ambiences, DJs, Playlists, New files, BestOf, Queue :
![Image](/images/Prepare_party_1.png)

For DJs, Ambiences and Playlists you can choose one of the available items from the combo box. The combo box is enabled as soon as this source is selected.

<div class='info'>Choices are disabled if there is nothing to choose from, e.g. if there is no Digital DJ defined.</div>

### Limit the selected files
As next step you can choose from a number of different settings to limit the amount and type of media files.

![Image](/images/Prepare_party_2.png)

The type selection allows to limit the selected files to one type of media. If you additionally select the conversion option, Jajuk will attempt to convert media files to the selected target type.

For conversion, the external tool PACPL (Perl Audio Converter) is used, take a look at [Using Perl Audio Converter](pacpl.html) for instructions how to set this up.

<div class='info'>Conversion can be a time consuming operation as PACPL needs to first convert to a raw format (WAV) and only then can encode to the target format if both source and target format are some compressed format.</div>

If you choose to normalizing filenames, Jajuk will renmae any special character in the filename in order to circumvent problems when using certain filesystem types, e.g. some Windows FAT partition types do not allow characters like umlauts.

### Define the target of the set of files
And finally you can choose where to put the files, any available folder can be chosen:

![Image](/images/Prepare_party_3.png)


Go back to the [TOC](/manual/main.html)