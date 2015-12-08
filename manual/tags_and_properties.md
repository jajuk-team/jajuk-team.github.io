---
title: Editing tags and properties
layout: default
---
Go back to the [TOC](/manual/main.html)

# Editing tags and properties
You can set tags and properties from :

- Tracks and Files Table views. If you don't see the property column, check it in the table column selector by clicking on the top-right icon of the table (see [using tables in views](using_tables_in_views.html) Table view / Select columns to show). You also need to enable the table ``edit`` button.
- The Property dialog for any item (see below) from any view.

## The Property dialog
![Image](/images/properties.png)

The Property dialog can be used to display and edit all properties for a single item or a multiple-selection. It is accessible from:

- The table views (right click on the element(s), then ``Properties``)
- The tree views (right click on the element(s)n then ``Properties``)
- The playlist repository view (right click on a playlist, then ``Properties``).

<div class='info'>You can also use the Alt-Enter keystroke.</div>

The Property dialog contains the following fields :

- _Property name_ (custom properties in blue).
- _Property value_ (editable or not according with situation and rules).
- _Link_: If value is itself an item, click on the button to display associated property dialog.

When all properties are set, click on ``Apply`` to update properties and commit them in music files if tag properties.

### Notes:
- For music files, genres, artists and albums we show both item(s) (left side) and associated track(s) (right side) properties for convenience.
- Custom properties names are in blue to distinct them.
- In case of multiple selection, the Property dialog only display common properties that can be changed. A blank field means that items have different values, change it and apply to update every items together.

### Tags
Some properties are stored in collection and in the music files itself (like ID3 tags) at the same time. These properties are: genre, artist, album, track name, year, comment and track number.

If you change tags via another application, use "Perform a deep tag scan" option and launch a device refresh to take them into account in Jajuk (see [Preferences view](view_preferences.html)).

Note that tags are stored in Unicode (UTF-16LE) in files. This encoding is compatible with all players (Windows Media Player or Winamp for instance) and allows Asian people to correctly edit tags using Jajuk.

### Get tags online
Jajuk enables to change all tracks for an album using CDDB music online databases (like freedb). To use it, select "Get tag online" function on a directory node in Physical Files Tree view in contextual menu.

# Extra tags
![Image](/images/Extra_tag_configurations.png)

By default, Jajuk only work with a small number of tags (artist, year...) but the music files may content many others. You can enable any tag into Jajuk using the "Extra Tag Configurations" dialog.

If you want Jajuk to display extra tags, i.e. the composer of a mp3 file, you must add these extra tag to your Jajuk collection. You can do this easily with the new extra tag configurations. 

You can start the configurator by clicking on the menu "Properties" / "Extra Tag Configurations".

Extra tags can only be displayed. After you activated them, a deep refresh of your collection is performed. After that, you can enable the tag in every file table, where you want to display it.

# Custom properties 
![Image](/images/custom_properties.png)

Jajuk offers a way to add custom attributes on almost any item (files, playlists, artists, albums...).

- Imagine you're not happy with the integrated rating system : just create a custom 'my rate' number attribute on tracks.
- You want to store physical location of your CDs ? Create a String custom attribute on devices.
- You want to store the date you listened tracks ? Create a date-based custom property
- and so forth...

### Important notes
- Custom properties data is only stored in jajuk internal database and NOT in music files like audio tags (ID3 for ie) so this information will *NOT* be accessible from others players or jukeboxes.
- If you use this feature intensively, consider making backup of your collection files (see [Backup collection](devices.html#collection-backup-and-restore)).

## How to create a new custom property ?
In frame top menu, select _Properties_ / _Create custom property_ :

- _Item_: Choose the item type you want to add custom property on. It can be physical (Device, Directory, File, Playlist) or tag-based (Genre, Artist, Album, Track...).
- _Custom property name_: The property name. Note that some names are reserved like "name, id...". You will get an error message if you try to use them.
- _Type_: Property type. Jajuk supports: Numbers, Float, Strings, Dates or Booleans (true/false).
- _Default value_ (optional): A given default value. Depending on property type, you will be able to set it in the text field, using the date picker or checking the check box. If no default value is given, Jajuk uses these default values: Numbers: ``0``, Float: ``0.0``, Strings: ``""``, Dates: ``[current day]``, Boolean: ``false``.

Then, click on ``OK`` to create the custom property.

## How to remove a custom property ?
In frame top menu, select ``Properties`` / Remove _custom property_. The remove property wizard features:

- _Item_: Choose the item type for which you want to remove custom property.
- _Custom property name_: The property name.

Then, click on ``OK`` to remove the custom property. Note that all values will be lost for this attribute. In case of manipulation error, see [Restore collection](devices.html#collection-backup-and-restore).

### How to set values ?
Values for custom properties are set just like any other.

### Using custom properties the Web 2.0 way
Custom properties allow a "web 2.0" flavor searches:
- Create a String custom properties on an item type (tracks, albums, files...)
- Edit tags on items you want to tag, example: "lyrics woman" on an item and "man lyrics" on another one
- Perform a search by filtering on the new created custom properties (or keep using the "any" filter). The search ignore words order so you can search for "man lyrics" or "woman" to find tagged items

#### Tag your music using your key word: a concrete example
- In the perspective "Tracks", go in menu "Properties", create a new custom property using Item: "Title", Custom property name: "tag", type: "string".
- Now start tagging your music. Select in the "Tracks tree" or "tracks table" window items you want to put the same tag, do a right click. At the bottom of the property window, there is the custom property "Tag" were you can enter your key words. For this example we create a few selections with tags such as:
    - Selection 1: "jazz trio piano bass saxophone live"
    - Selection 2: "jazz piano male singer live"
    - Selection 3: "jazz female singer"
    - Selection 4: "jazz bigband"
    - Selection 5: "pop piano female singer live"

- You can now perform search on tags in the filter bar (top of the "tracks table" view). Select filter "any" or "tag", then enter your key words. For example "live singer" will list any track tagged before in selection 1 and 5.


Go back to the [TOC](/manual/main.html)