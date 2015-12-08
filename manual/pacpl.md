---
title: Using Perl Audio Converter
layout: default
---
Go back to the [TOC](/manual/main.html)

# Using Perl Audio Converter

**Perl Audio Converter** or **PACPL** is a small tool to convert media files between different formats.

It is used in the Prepare Party Wizard starting in version 1.9 of Jajuk to allow to convert media to one single format, e.g. MP3 for devices that only support this audio format.

PACPL is available at [http://pacpl.sourceforge.net/](http://pacpl.sourceforge.net/).

### Installation on Linux
On most Linux distributions it can be installed using the package system. If your Linux Distribution does not provide packages, you can download the package from the homepage and install it according to the installation instructions included.

### Installation on Windows
On Windows the following steps can be used to install PACPL:

- Install Perl, see e.g. [http://www.activestate.com/activeperl/](http://www.activestate.com/activeperl/) or [http://cygwin.com/](http://cygwin.com/)
- Install the necessary modules, this is done most easily using [CPAN](http://www.cpan.org/) with the following steps:
<pre>
perl -MCPAN -e shell
install Parse::RecDescent Carp Inline Inline::C Devel::Symdump Switch Pod::Coverage Test::Pod::Coverage MP3::Info Audio::Musepack Audio::WMA MP3::Tag Ogg::Vorbis::Header IO::String MP4::Info Audio::APETags CDDB_get
force install Audio::FLAC::Header
quit
</pre>

- Install the necessary encodes/decoders depending on the conversions that you would like to have available and put them somewhere in your Windows search path:
<pre>
AAC: faac,faad
FLAC: flac,flac
FLA: flac,flac
M4A: faac,faad
MP4: faac,faad
MP3: lame,lame
OGG: oggenc,oggdec
TTA: ttaenc,ttaenc
</pre>

Some of them can be installed via the following cygwin-packages: lame, flac, vorbis-tools. But there are also download-sources where these files are binary compiled for Windows available.

- Download PACPL from [http://pacpl.sourceforge.net/](http://pacpl.sourceforge.net/) and install it into a separate directory.
- If you are using perl from Cygwin, you will need to patch pacpl slightly to make it work when called from Java/Windows applications. Open the file "pacpl" and add the following line after the "use"-lines on top: ``fileparse_set_fstype('MSWin32');``
- Verify that PACPL works by invoking it manually as follows
<pre>
perl &lt;install-location&gt;\pacpl --help
</pre>
- Verify that PACPL can convert some audio-file by invoking the following:
<pre>
perl &lt;install-location&gt;\pacpl -to ogg "&lt;Your-Music&gt;.mp3"
</pre>
- Finally you can specify the location of the pacpl-scripts in the Prepare Party Wizard, there is a small configuration dialog that you can use to define the command to run pacpl. For Windows, this will look something like the following with the location replaced correctly:
<pre>
perl &lt;install-location&gt;\pacpl
</pre>

**See also** [PACPL-FAQ under Windows](http://pacpl.sourceforge.net/faq.html)

### Installing on MacOS
Probably similar to Windows

Go back to the [TOC](/manual/main.html)