---
title: Editing tags and properties
layout: default
---
Go back to the [TOC](/manual/main.html)

# Editing tags and properties
You can set tags from :

- Tracks and Files Table views. If you don't see the property column, check it in the table column selector by clicking on the top-right icon of the table (see [using tables in views](Using_tables_in_views.html) Table view / Select columns to show). You also need to enable the table "edit" button.
- The Property dialog for any item (see below).

### The Property dialog
The Property dialog can be used to display and edit all properties for a single item or a multiple-selection. It is accessible from:

- The table views (right click on the element(s) -&gt; _Properties_)
- The tree views (right click on the element(s) -&gt; _Properties_)
- The playlist repository view (right click on a playlist -&gt; _Properties_).

<div class='info'>You can also use the Alt-Enter keystroke.</div>

Notes:

- For music files, genres, artists and albums we show both item(s) (left side) and associated track(s) (right side) properties for convenience.
- Custom properties names are in blue to distinct them.
- In case of multiple selection, the Property dialog only display common properties that can be changed. A blank field means that items have different values, change it and apply to update every items together.

Property dialog contains these columns:

- _Property name_ (custom properties in blue).
- _Property value_ (editable or not according with situation and rules).
- _Link_: If value is itself an item, click on the button to display associated property dialog.
- _Type_: Property type.

When all properties are set, click on ``Apply`` to update properties and commit them in music files if tag properties.

### Tags
Some properties are stored in collection and in the music files itself (like ID3 tags) at the same time. These properties are: genre, artist, album, track name, year, comment and track #.

If you change tags via another application, use "Perform a deep tag scan" option and launch a device refresh to take them into account in Jajuk (see [view preferences](View_preferences.html)).

Note that tags are stored in Unicode (UTF-16LE) in files. This encoding is compatible with all players (Windows Media Player or Winamp for instance) and allows Asian people to correctly edit tags using Jajuk.

### Get tags online
Jajuk enables to change all tracks for an album using CDDB music online databases (like freedb). To use it, select "Get tag online" function on a directory node in Physical Files Tree view in contextual menu.

Go back to the [TOC](/manual/main.html)