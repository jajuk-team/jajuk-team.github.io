---
title: Files organizer
layout: default
---
Go back to the [TOC](/manual/main.html)

# Files organizer

## Files organizer
If your music files is correctly tagged but are a mess on your disks or if you want to standardize their names, 
you can can use the "Organizer" feature available from Physical Files Tree view. 

Select a directory / right click / ``Organize files``. 

This function reads ID3/OGG/others tags and renames files and directories according to them and a pattern (by default: ``artist/year-album/track-title``).  

You can change this pattern in the [Preference view/ Tags tab](view_preferences.html#patterns-tab).  

<div class='warning'>This function is available only for files with tags correctly filled.</div>

## Available fields
You can use following fields in the pattern:

-  ``%artist``: Artist of the track
-  ``%album_artist``: Album Artist (if not defined, the track-artist is used)
-  ``%album``: Album name
-  ``%genre``: Track genre
-  ``%year``: Track year
-  ``%title``: Track title
-  ``%n``: Track
-  ``%disc``: CD-number

<div class='info'>The pattern must contain at least one slash because the organizer needs to create at least one directory.</div>

Go back to the [TOC](/manual/main.html)