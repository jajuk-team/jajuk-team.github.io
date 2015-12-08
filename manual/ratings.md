---
title: Rating system
layout: default
---
Go back to the [TOC](/manual/main.html)

# Ratings

Jajuk comes with an semi-automatic rating system that learns tracks you like the most based on the 
frequency you listen to them and that allows to set personal preferences to increase or decrease the final ratings.

## Summary

- A track rating is an integer value between zero (worse or never listen) and 100 (best)

- The rating is set on tracks, not audio files. That means that all duplicates files for the same track share the same rate.

- Tracks rating is usually displayed as a set of stars in tables or others popups (from zero to four stars). Exact rating value is available as a tooltip by moving mouse over the stars.

- A track that has never been listened owns a zero rate.

- Final rating is computed by mixing these information up (for more details, see bellow) :
    - The listening rate (how long in seconds a track has been actually listen in comparison with maximum possible listening duration whose value is [number of hits * track duration]). When user stops playing a track or switch to a new track, the listening rate decreases.
    - The number of times the track has been listen. Note however that the importance of this value decreases with the number of hits. For example, a track that has been listen 100 times will have almost the same final rate that the same listened 200 or 1000 times but significantly higher than a track listened only once.
    - The user preference factor (can be set using the preference combo in [commands](commands.html) or [slimbar](slimbar.html)). Available preferences factors are :
        - Increase final rating : classic, excellent, good
        - Neutral for final rating : no preference
        - Decrease final rating : average, poor, junk

- The preference menu available from most views in Jajuk (trees, tables..) allows to set a preference on a group of tracks all together (recursively on a directory or on an artist for instance).

## The banning system

You can tell Jajuk to ban some tracks so they will not be included anymore in automatically built selections (when using [smart functions](commands.html#smart) for instance).

- Note that banned tracks are still visible from jajuk views and can still be launched manually as desired.
- Pardon function remove the banning flag from the track(s)
- Banning / Pardon features is available from [commands](commands.html), slimbar for currently playing track and from the Preference view in most tree or table views. Like preferences, you can ban/pardon a group of tracks all together (recursively on a directory or on an artist for instance).

## How to reset ratings ?

In [Preferences view /History /Ratings](view_preferences.html#historyratings-tab) :

- **Reset ratings** set the entire collection tracks rate to zero but keep preferences (set manually by users)
- **Reset preferences** reset the user preferences to "no preferences" and recomputes all tracks final ratings. Tracks play history is kept.
- Use both functions to totally reset rates.

## More details on rating computation

- The rating system study details is available [here](http://github.com/jajuk-team/jajuk/issues/1174).
- The current final rating formula is :

![Image](/images/Rating_formula.png)

where :

- _totalplaytime_ is the total time in seconds a track has been played
- _trackduration_ is the track length is seconds
- _nbplays_ is the number of times a track has been launched
- _max (nbplays)_ is the max nbplays value among the entire collection
- _preference_ is the user-set preference factor [-3;3]

### Manual ratings

A manual rating system is also available using preference level detailed bellow. 
It is available from the Preferences View / History/Ratings tab. For instance, setting "Classic" 
preference force rating to 100% and setting preference to "Good" force it to 50%.

Go back to the [TOC](/manual/main.html)