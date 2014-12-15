---
title: Mac Os Installation Guide - Jajuk
layout: default
---

# Linux Debian Installation Guide

## Requirements

- [Mandatory] Java Runtime environment (JRE) 1.6 and above. Not sure if you already have Java ? Check this [link](http://javatester.org/version.html).
- [Mandatory] 1024x768 screen resolution and higher
- [Strongly recommended] MPlayer 1.0 pre8 and above available from the $PATH (this will provide better sound quality and more audio formats such flac) 

## Install mplayer and Java

    $ sudo apt-get install mplayer sun-java6-jre

## Configure the default Java

We need to configure it at the default java (selection 6, /usr/lib/jvm/java-6-sun/jre/bin/java, in the example below)

    $ sudo update-alternatives --config java   

    There are 6 alternatives which provide `java'.

      Selection    Alternative
    -----------------------------------------------
              1    /etc/alternatives/kaffe-system/bin/java
              2    /usr/bin/gij-wrapper-4.0
              3    /usr/lib/jvm/java-1.5.0-sun/jre/bin/java
              4    /usr/bin/gij-wrapper-4.1
     +        5    /usr/lib/jvm/java-gcj/jre/bin/java
     *        6    /usr/lib/jvm/java-6-sun/jre/bin/java 

     Press enter to keep the default[*], or type selection number: 6
     Using `/usr/lib/jvm/java-6-sun/jre/bin/java' to provide `java'.

## Install jajuk

- Using apt-get or synaptic or adept_manager

Jajuk is now part of Debian. you can install it using your favorite package manager. You can check version availability on [http://packages.debian.org/jajuk](http://packages.debian.org/jajuk). Note however that the Debian version may be outdated and older than Jajuk official deb file.
Using the .deb (RECOMMENDED)

This file is available from [Download](download.html)

<code>    $ sudo dpkg -i jajuk_<version>.deb</code>

## Start Jajuk

Use created shortcuts or from the console, if your path, if set correctly, just type from the command line:

    $ jajuk

## Upgrade

- It is safe to install the new release over previous one without uninstalling, Jajuk supports backwards compatibility.
- Jajuk doesn't support downwards compatibility: A Jajuk release may not work with a collection built by a newer release than the one you use. 

## Support

If you need help, check out our [FAQ](/jajuk_faq.html) and our [manual](/jajuk_manual.html).

## Uninstallation

    sudo apt-get remove jajuk

### Java Installer

- Launch uninstaller by clicking on the menu Jajuk ->'Uninstall'. 