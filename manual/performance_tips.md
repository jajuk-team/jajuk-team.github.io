---
title: FAQ - Jajuk
layout: default
---

Go back to [TOC](/manual/main.html)

# Performances Tips
Read that chapter if you encounter some performances drawbacks or if you want consume less memory, disk, CPU or Network bandwidth using Jajuk.

## CPU usage

- On a PC/P4M 1.8Ghz, Jajuk uses about 9% CPU for mp3 and 3% for Ogg Vorbis. On a Centrino 1.8 Ghz: 0% of CPU usage detected.
- Tips to reduce CPU Usage:
  - In your current perspective, don't keep opened views that you don't need
  - Increase devices refresh period (In Devices view / Device dialog) so Jajuk refreshes collection less often. 

## Memory Usage

- Jajuk usually uses 100 MB of memory or more for large collections when using all its features. This can sound a lot but keep in mind that Jajuk comes with a lot of image manipulation (e.g. Covers or Album catalog view). Even with optimizations, there is still a basic amount of memory footprint we can't go bellow.
- A JVM runs inside a reserved memory heap. The JVM takes all the Xms MB of memory at startup and requires more memory to the OS only if necessary. For a big size collection, it takes about 65MB maximum of memory but 40MB should be enough most of the time.
- Tips to reduce memory consumption:
  - Using Jajuk slimbar instead of full window dramatically cuts memory costs.
  - Don't open perspectives you don't use (perspective memory is used only once opened)
  - Limit size of Albums catalog view page size (Preference view / GUI tab / Catalog view)
  - Remove any view that you don't need all the time, they can be opened again quickly if needed. This should include the ones automatically minimized in some perspectives. Good candidates usually are Animation View, Album Catalog View, Wikipedia View, Statistics View.
  - On 64-bit systems with 64-bit JVM, add the Java VM argument "-XX:+UseCompressedOops" to the startup script. This is available since 1.6.0_14, however make sure to use newer versions of the JDK, e.g. 1.6.0_20, as early versions had severe bugs with this option. See [1] for some description of this option. 

**Note:** You will need to restart Jajuk to actually see reduction in memory usage for these suggestions as Java usually keeps allocated memory and does not free it any more.
Bandwidth

- If you have a low Internet connection, avoid using advanced online covers options (see next chapter).
- If you use a network drive-type device, check refresh frequency (default: 5 mins) because Jajuk scans all the device with this given frequency and this uses bandwidth. Increase duration if the collection changes few.
- Disable Scrobbling (Preference view / LastFM tab)
- Extreme solution : disable any Internet access from jajuk (in top menu -> Configuration) 

## Covers performance tuning

These options are available in the Parameter View / Cover tab.

- "Use auto-cover" option (default=yes) uses network bandwidth.
- You can reduce covers size by setting lower minimum and maximum cover sizes.
- You can increase or decrease the time out when downloading a cover in the Parameter view/ Network tab. 

## Tags performance tuning

At first refresh or during a forced refresh, all tags are read again. This takes a while. Use "Force refresh" function only if you want to update tags changed by another application.
Collection performance tuning

These options are available in the view preferences, Advanced tab.

- If your collection uses mainly non-European characters (like Asian languages), choose UTF-16 as collection encoding : that will reduce collection file size and accelerate startup parsing. Do not use this option if you use European languages because you collection file would then grow. 

## Animation View performance tuning

Animation view uses Java 2D. CPU overhead can be significant, especially with screen resolution higher that 1200x1024. On a P4 1.8Ghz with a resolution of 1024x768, the overhead is about 2 or 3% but reaches 10 or more with a resolution of 1400x1200.
JVM customization

- If you have a really big collection (more than 150 or 200 GB), you may increase -Xms parameter.
- You can set a -Xmx parameter to restrict memory usage to this value (example: -Xmx600M)
- Use -Xloggc:<file name> to trace memory usage if needed. 

Go back to [TOC](/manual/main.html)