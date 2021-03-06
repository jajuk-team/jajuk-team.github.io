---
title: Integration procedures
layout: default
---
* auto-gen TOC:
{:toc}

# Integration procedures

## New langpack
* Add register in ``LocaleManager.LOCALES``
* Add a language in [Features / Supported languages ](/features.html)
* Add a ``Language_desc_`` line in ``jajuk.properties``
* Check the language has a auto-description (a ``Language_desc_`` line for its language)
* Add a langpack in ``jajuk.nsis``
* Commit the flag in ``resources/icons/16x16``
* Add the new langpack into QDWizard Langpack class

QDWizard specific :

* Edit ``history.apt``
* Generate and deploy : ``mvn deploy``

## About the packaging
* Packaging scripts are in the ``src/packaging`` directory
* All the packaging is now performed from the build_full.xml ant script (no more Maven, alien...)
* We no more use Maven because:
  * some of the dependencies are not available from maven central ;
  * most OS-specific build tools only under ant, not maven ;
  * most Linux distribution (like Debian) uses ant to package java projects and not maven.
* The junit tests are now launched from the ant scripts
* The build_full.xml prepares the build_enduser.xml ant script (it set the version, renames it to build.xml and put it into the source package so the end user that downloaded the source package has just to perform an 'ant' command to build Jajuk)
* The compilation, jajuk.jar creation and tests code is factorized into the build_enduser.xml ant script, the build_full.xml ant script call it for these purposes so the same ant code is used by the global build and the end-user build.
* We no more use executable jajuk.jar (with a MANIFEST), but only -cp (-classpath) options with '*' wildcard. This has several advantages :
  * simpler ant script ;
  * no more MANIFEST file to maintain when removing/adding or changing a lib version ;
  * possibility to change lib relative path from jajuk.jar from an OS to another (for a better match of each OS or Linux distribution conventions).
* The Debian package is now platform independent as we no more bring the dbus native library (libunixsocket-java). This library is already available under Debian so we now have an optional package dependency.
* Most RPM-flavor distribution (except Fedora) doesn't come with libunixsocket-java livrary, so we had to bring it into our RPM. 

## Build a release
<div class='info'>
[major] tasks applies on x or x.y releases only like 2.0 or 1.7 , 
[minor] applies to x.y.z fix releases like 1.6.7 ,
[RC] applies to release candidates
</div>

### Legals
- [major] Update the Dependencies and Derivative sections in [Legals](/legals.html)
- [major] Update ``AUTHORS.txt`` file sorted by commits numbers using :
``git log --format='%aN <%aE>' | awk '{arr[$0]++} END{for (i in arr){print arr[i], i;}}' | sort -rn | cut -d\  -f2-``

### Code
<div class='info'>We assume that we are about to release branches created using <a href='http://jeffkreeftmeijer.com/2010/why-arent-you-using-git-flow/'>git-flow</a></div>

- [all] Refresh workspace, make sure to pull every commit
- [all] Check copyright year in ``Const.java``
- [all] Commit and push all changes in jajuk project
- [all] Check stashed code
  - ``git stash list``
  - ``git stash show -p stash@{<n>}``
- [major] Cleanup code (imports, formating and clean-up)
- [minor,major] Search for ``System.out`` (14 in ``src/main/java`` so far)
- [major] Detect and drop useless labels from every langpack (``jajuk.properties`` files)
- [all] In ``build_full.xml`` of the hotfix[minor] or the release[major] branch, bump version :
  - Set the last ``version`` (remove ``dev``)
  - Change ``test_flag`` from ``test`` to ``notest``
  - Commit the bump : ``git commit -a -m "Bump version for release x.y.z"``
  - [major] ``git-flow release finish release-x_y_z``
  - [minor] ``git-flow hotfix finish release-x_y_z`` (Changes from hotfix branch will be merged back to master AND develop branches. It should be avoided but if you already reported the changes or you can't do the merge, you can make the merge, commit it (even with conflicts) and then revert it from develop branch using : ``git revert -m 1 HEAD`` )
- Push : ``git push origin``
- Launch the final build from the CI server
- Disable the maintenance job from jenkins
- [all] Test it a minima under several OS
- [all] push tags (git-flow already tagged using the branch name) : ``git push origin --tags``

 
- [minor,major] Create a release on Github
- [major] Update the manual
- [major] Create a README page : [http://jajuk.info/index.php/Release_notes_x.y](http://jajuk.info/index.php/Release_notes)
- [minor,major] Change Download and Main page
- [minor,major] Check website (links, pages...)
- [all] Close bugs, known issues and Features at github
- [all] Set the due date and close the milestone at github

### Others
- [all] Upgrade the version in the [version file](https://github.com/jajuk-team/jajuk-team.github.io/blob/master/repository/pad/jajuk_pad.xml)
- [all] Send a message in the developer list
- [major] If ``default_webradios.xml`` list changed, update file at [http://svn2.assembla.com/svn/common-jukebox/common-jukebox/src/main/resources/preset_radios.xml](http://svn2.assembla.com/svn/common-jukebox/common-jukebox/src/main/resources/preset_radios.xml)
- [all] Update and publish Jajuk pad at [http://publisher.appvisor.com/](http://publisher.appvisor.com/) (date + version:+ exe url; 5 lines to change).

## Prepare the next version after a release
These actions should be done before or just after a major release to create a new major version environment.
- Create a support branch
- Update ``Const.TEST_VERSION`` and ``Const.JAJUK_CODENAME`` constants

