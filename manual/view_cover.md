---
title: Cover view
layout: default
---
Go back to the [TOC](/manual/main.html)

# Cover view
This cover view displays local (files on your disk or inside audio files) or remote (from the Web) covers. 
It can be configured in the Preference view/Covers tab.

### Notes

- Covers size is limited to 2 MB to avoid memory issues. All local or remote covers over this size are just ignored.
- When looking for local covers, Jajuk takes all supported image files found in the current directory or inside the current played track tags but also in all directories of the track. For instance, if you play a track from your hard disk and this file is also on a mounted CD with different covers, Jajuk will display all of them. It is useful because this way, you can save covers (see later) without having to know on which device you saved them.
- If no default cover is set (see "Default cover" action bellow), Jajuk displays first local files beginning by ``cover`` or ``front``

## Control panel
- ![Image:previous_16x16.png](../images/Previous_16x16.png) Display previous cover

- ![Image:next_16x16.png](../images/Next_16x16.png) Display next cover

- ![Image:delete_16x16.png](../images/Delete_16x16.png) Delete physically the cover from your disk. By default, you will have a confirmation (can be set in the [Preferences view/ Confirmations tab](view_preferences.html#confirmations-tab))

- ![Image:save_16x16.png](../images/Save_16x16.png) Save a current remote cover in the current track directory using its original name

- ![Image:save_16x16.png](../images/Save_16x16.png) + CTRL: Save a current remote cover on your disk using path and name of your choice

- ![Image:ok_16x16.png](../images/Ok_16x16.png). If the cover is a remote cover not already on the disk, it will be downloaded and saved first.

- **Size (L, T or @)**: Gives size in KB of this image. A ``L`` means it 's a local image, ``T`` a tag image and ``@`` means it's a remote image.

- **x/y**: Gives current index over total number of covers available

    - ![Image:accuracy_low_16x16.png](../images/Accuracy_low_16x16.png) Low accuracy

    - ![Image:accuracy_medium_16x16.png](../images/Accuracy_medium_16x16.png) Medium accuracy

    - ![Image:accuracy_high_16x16.png](../images/Accuracy_high_16x16.png) High accuracy

    - ![Image:author_16x16.png](../images/Author_16x16.png) Artist

    - ![Image:album_16x16.png](../images/Album_16x16.png) Album

    - ![Image:track_16x16.png](../images/Track_16x16.png) Title



- **Search type**, set accuracy for remote covers (used only if you use the Auto-cover feature, this is the default). Low, medium and high accuracy performs search on both the artist and the album names. The difference is than the more the accuracy will be high, the less you will get covers but the more the chance of getting a right cover is high. Artists, Album and Title only perform searches respectively on the artist, the album and the track title.
    
    - ![Image:accuracy_low_16x16.png](../images/Accuracy_low_16x16.png) Low accuracy
    
    - ![Image:accuracy_medium_16x16.png](../images/Accuracy_medium_16x16.png) Medium accuracy
    
    - ![Image:accuracy_high_16x16.png](../images/Accuracy_high_16x16.png) High accuracy
    
    - ![Image:author_16x16.png](../images/Author_16x16.png) Artist
    
    - ![Image:album_16x16.png](../images/Album_16x16.png) Album
    
    - ![Image:track_16x16.png](../images/Track_16x16.png) Title

## Cover view options
You can benefit from advanced cover option (see [Preference view/ Covers tab](view_preferences.html#covers-tab) for more details). You can tell Jajuk to:

- Enable/disable online cover search
- Shuffle covers
- Set minimum and maximum size for remote covers
- Mirrow covers

<div class="info">You can also tune network options like proxy and connection 
time out if you experience problems getting remote covers 
(see <a href="view_preferences.html#network-tab">Preferences view/ Network tab</a>).
</div>

Go back to the [TOC](/manual/main.html)