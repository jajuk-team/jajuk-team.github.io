---
title: Translator guide
layout: default
---
# Translator guide

## Target
Anyone can translate Jajuk, no computer science is required. Note this is a voluntary work. 

For any question or comments, please contact us. 

Current Jajuk version translation should take few hours and upgrade only few minutes.

## Jajuk translation
* Jajuk uses a custom internationalization (i18n) system based on a XML file that allow translators to edit directly text files even when using non-european characters. 
Langpack files are named ``jajuk_{locale}.properties`` where {locale} is a ISO language code.
 These files are located in the ``src/main/resources/org/jajuk/i18n`` directory.
``jajuk.properties`` contains default resource bundle (English) and you have a property file for each language.

* Get the property file of your choice as a source language. Example: take last release of ``jajuk.properties`` as English source language or any other property file in this directory.
* The simplest way to translate Jajuk is using the Github integrated file editor. You just need a GitHub account, to fork the [jajuk-team/jajuk project](https://github.com/jajuk-team/jajuk), to edit existing files or to add a new file to the ``src/main/resources/org/jajuk/i18n directory`` and to perform a pull request (ask if you need help). 
* Create your text file. It should begin with:

<pre>
#Jajuk {your language} langpack.
#Written by : {your name}
#Copyright {current year} The Jajuk Team, this is part of Jajuk distributed under the GPL V2 license
#FROM {source language} {current date in YYYY/MM/DD format}
</pre>

Example:

<pre>
#Jajuk Galician langpack.
#Written by : Xabier Cancela
#Copyright 2008 The Jajuk Team, this is part of Jajuk distributed under the GPL V2 license
#FROM en 2012/06/11
</pre>

  * You have to write your files in Unicode UTF-8 encoding. If you don't know how to set the encoding, please contact us. This is handled correctly by the GitHub code editor so we advice to use it to create of update your files.  
  * Look at file structure: It is a simple key=value format. Example:
<pre>
ParameterView.73=Check this if you allow others people to come read music from your box
ParameterView.74=Password :
ParameterView.75=Set password access to your box. 
</pre>

  * Simply translate each value, Previous example in French:

<pre>
ParameterView.73=Accepter que d'autres utilisateurs lise la musique située sur votre machine
ParameterView.74=Mot de passe :
ParameterView.75=Fixez un mot de passe à votre machine.
</pre>

  * Translate even lines like Language_desc_*=* (other languages names) and add a new line with your own language.
  * Some lines are under comments like "limited size". In this case, make sure to keep your translation short to ensure correct display.
  * Send us your work as a property file with your local ( ex: ``jajuk_ru.properties`` for Russian ).

## Optional, for translators with developer skills
If you want to test your work (ant must be installed):

  * Edit ``{jajuk installation path}/src/org/jajuk/util/Messages.java`` file and search for line :
```java
public static final String[] locales = { "en", "fr", "de", ...};
```
  * Then, add your your own locale.
  * Copy your properties file in the ``{jajuk installation path}/src/org/jajuk/i18n`` directory
Go in the ``{jajuk installation path}`` directory where you can find the build.xml file
  * Rebuild Jajuk typing ``ant -lib . package_jar``
  * Launch Jajuk and set language in the parameter view of the configuration perspective.
  * Check your work.

## Translation upgrades
As you can imagine, Jajuk evolves and new releases brings new labels or change them. Before new releases, 
the packager sends messages to the project mailing list to request translation upgrade. 
Note that if some new labels are not translated, they will simply be displayed in English. Hence, a partial langpack is not critical. 
The hard work is the first translation : upgrade a translation usually requires only few minutes. 
You only need a web browser and a text editor supporting UTF-8 (see suggested text editors in the Jajuk translation section). 
You can upgrade your translation whenever you want. What you have to do when upgrading a translation is :

  * If your source (FROM) language is NOT English, make sure it is up to date before upgrading it.
  * Check your ``#FROM`` comment at the beginning of your file, it should contain the date of your last upgrade.
  * Perform a 'diff' between this release and the current version.
  * Remove old labels, modify and add new ones.
  * Upgrade the #FROM comment with the translated release.
  * Commit your file or contact us.

## Tips
  * Do not modify keys but only values. In ``Label.1=foo``, ``Label.1`` is the key and ``foo`` is the value.
  * If a value contains a ``\ ``, do not drop it, it means there is a space at line start.
  * Blanks at the end of a line are usually on-purpose to have some space in the combined text when it is concatenated with some value, don't cut them off.
  * Keep ``<html>``, ``</html>`` or others tag strings.
  * Keep all punctuation and specials characters like ``[``,``.`` and so on...
  * Try to keep values length near from source ones so labels will not be too long and stay visible.
  * Use a spelling corrector.
  * Detect obsolete labels
  * For developers who want to find labels no more used in code (please remove them from ``jajuk.properties`` so translators avoid useless work), use the scripts in ``jajuk/src/tools`` :
    * ``detect_dead_labels.sh`` to find dead labels
    * ``clean_dead_labels.sh`` to drop them
