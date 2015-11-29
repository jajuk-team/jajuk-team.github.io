---
title: Hidden options
layout: default
---
Go back to [TOC](/manual/main.html)

# Hidden options
This is a non-exhaustive list of special tuning options not accessible from the graphical interface, mainly used for troubleshooting purpose. 
Beware that **you must stop Jajuk before editing the ``conf.properties``** file, otherwise your changes will be overridden at next Jajuk close.

### Options available from the conf.properties file
These options are editable in the file ``[Jajuk repository]/conf.properties`` 
(if you didn't change the Jajuk configuration path, this file is located at [home directory](/homedir.html)``/.jajuk/conf.properties``

- ``jajuk.frame.forced_position`` [default=""]: set forced Jajuk frame size and position at startup in x,y,width height format. Example: ``jajuk.frame.forced_position=10,10,1000,800``
- ``jajuk.options.visible_planned`` [default=10]: number of planned tracks visible from the queue view (a planned track is in continue mode a track that is not explicitly launched but will be played when current selection is done).
- ``jajuk.collection_charset`` [default=``UTF-8``]: Collection charset. UTF-16 is optimized in size for Asian languages and UTF-8 is optimized for European languages. If the collection contains mainly Asian characters, the collection file will be smaller when using UTF-16.
- ``jajuk.stats.min_value_genre_display`` [default=2] : Minimum percentage of tracks of a given genre to be shown in the Stat view (and not in the 'others' part of the chart).

### Options available from Command line
These options are in the Java ``-Dkey=value`` form. They can be set in jajuk (Unix) / jajuk.bat or shortcut (Windows).

- ``-Dworkspace=[absolute path]`` : Force the Jajuk configuration path from CLI (this directory should contain a ``.jajuk`` directory)

Go back to [TOC](/manual/main.html)