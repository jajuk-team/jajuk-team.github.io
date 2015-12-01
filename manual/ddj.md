---
title: Digital DJ
layout: default
---
Go back to the [TOC](/manual/main.html)

# Digital DJ

![Image:ddj](/images/200706_digital_DJ_wizard.png)

### What's a digital DJ ?
A digital DJ is just like a real one: it generates music playlists according to rules (kind of public, atmosphere, transitions...). 
Listening the collection using the shuffle mode is nice but not smart enough to produce a really good party time. 
Using DJs will allow you to delegate all the programing stuff to your favorite jukebox !

The digital DJ wizard is available from the ``Configuration`` top menu / ``Configure Digital DJ``. 

### What's an ambience ?
DJs can use the concept of ambience. An ambience is simply a set of music genres. For example, "Techno" ambience can group Euro-Techno, 
House, Trance and Goa styles together. Jajuk comes with preselected ambiences out of the box but you can create new ones or add/remove 
styles from them.

See [Ambience walkthrough](ambiences.html) for details.

### Types of DJs
Three kinds of DJs are currently available: transition, proportion or ambience-based DJs. 
All DJs have commons attributes.

#### Common attributes
- DJ name
- Rating level (from 1 to 4 stars): specify quality we expect from played tracks (using integrated rating system). 1 means no filter, 4 means only best ones.
- Cross-fade duration (seconds) between two tracks.
- Unicity: can a track be played several times in a party ?

#### Transitions-based DJ
A transition-based DJ generated the playlist using transition rules. For instance, ask the DJ to play two [Rock or Acoustic] genre tracks, then to play three [Jazz or Acid] tracks...

#### Proportions-based DJ

Using a proportion-based DJ, you can specify how many tracks set of styles you want to listen. For example, you can select 30% of [Rock or Acoustic] and 40% of [Blues or Folk]. If total is bellow 100%, the DJ will fill the playlist with shuffle tracks from your collection.

#### Ambience-based DJ
This DJ is very basic, indeed: it simply plays shuffle tracks of a given ambience.

### How to use DJs ?
The entry point for DJ feature is the DJ button (see the [commands](commands.html)).

- A single click on the DJ icon requires selected DJ to generate and launch a new playlist. Note that this feature is available from the systray as well.
- You can select the default DJ by clicking on the drop down button and checking a DJ if you have some. Note that the selected DJ name is also displayed as a tooltip on the DJ button.

### The DJ Wizard
To manage DJs (create, delete, modify), open the DJ Wizard using "Manage DJs" item in the drop down list of the DJ smart function button or from the Configuration, Manage DJs.

#### Creating a DJ
- Select "Create a DJ" in the first screen.
- Select the DJ mode: transition, proportion or ambience-based DJ.
- Fill up general options.
- Fill up DJ mode specific options.

#### Selecting styles for transition or proportion DJs
Transition and proportion DJs require to select styles using Genres Selection Window (appears when clicking on genres buttons). You can select one or more genres by using shift or control keys. If you want to select automatically all genres for a preselected ambience, select the ambience using the combo box at the top of the window (Caution: according to genres you already selected in previous transitions or proportions, only remaining ones are still available).

Go back to the [TOC](/manual/main.html)