---
title: Linux Rpm Installation Guide - Jajuk
layout: default
---

# Linux Rpm Installation Guide

## Targeted platforms

Any Linux distributions supporting rpm (Mandriva, Redhat/Fedora).

## Requirements

- [Mandatory] Java Runtime environment (JRE) 1.6 and above. Not sure if you already have Java ? Check this [link](http://javatester.org/version.html).
- [Mandatory] 1024x768 screen resolution and higher
- [Strongly recommended] MPlayer 1.0 pre8 and above available from the PATH variable (this will provide better sound quality and more audio formats such flac) 

## Installing JRE from a RPM

- Download RPM and follow instructions from [http://www.java.com/en/download/help/linux_install.xml](http://www.java.com/en/download/help/linux_install.xml)
- Check you now use the new JRE by opening a console and typing: 

    java -version

- If java command is not found, update PATH variable accordingly. 

## Jajuk Installation

We provide a single package for Linux (jajuk-{version}-noarch.rpm). This RPM should work with most Linux distributions but menu icons may not be created (in this case, please do it manually if required). To install, use your favorite graphical tool (Yast, Drake...) or log as root and launch:

    rpm -ivh jajuk-<version>.rpm

Notes:

It can take a while for shortcut to appear in menu.
Note that you can also install Jajuk under Linux using the Java_installer_guide. 

## Run

Use the new menu shortcut if created
Or simply type jajuk in a console : 

    $ jajuk

## Upgrade

To upgrade Jajuk, log as root and use:

    rpm -Uvh jajuk-<version>-noarch.rpm

It is safe to install the new release over previous one without uninstalling, Jajuk supports backwards compatibility.
Jajuk doesn't support downwards compatibility: A Jajuk release may not work with a collection built by a newer release than the one you use. 

## Uninstallation

If you installed using RPM, use your favorite graphical tool (Yast, Drake...) or log as root and use: 

    rpm -e jajuk

## Support

If you need help, check out our [FAQ](/jajuk_faq.html) and our [manual](/jajuk_manual.html).
