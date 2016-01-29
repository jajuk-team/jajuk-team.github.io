---
title: Jajuk Team - Jajuk
layout: default
---

# Contribute

## Team members
Check the [list of contributors](/members.html) 

## Want to donate ?
Check the [Donation page](/donation.html) 

## Want to translate Jajuk ?
Check the [Translation guide](/translator_guide.html) 

## Want to hack Jajuk ?
Please provide your contributions from GitHub through pull requests. Ask us before implementing large features.
Please read the [developer guide](/developer_guide.html).

## Integrator procedures
Find here [the procedures](/integration_procedures.html) when adding a library, when releasing or when adding a langpack.

## Main websites at a glance

<table id="screenshots">
<tr>
	<td><img src="/images/website_main.png" style="width:350px;" title="Main website" alt="Main website"/> <a href="http://www.jajuk.info">Main website</a></td>
	<td><img src="/images/website_github.png" style="width:350px;" title="Github" alt="Github"/> <a href="https://github.com/jajuk-team/jajuk">Github</a></td>
</tr>
<tr>
	<td><img src="/images/website_hudson.png" style="width:350px;" title="Integration server" alt="Integration server"/> <a href="http://integration.jajuk.info:8080">Integration server</a></td>
	<td><img src="/images/website_quality.png" style="width:350px;" title="Quality Center" alt="Quality Center"/> <a href="http://nemo.sonarqube.org/dashboard/index/org.jajuk:jajuk">Quality Center</a></td>
</tr>
</table>

### Team rules
We ask members to follow these basic rules:

- Members have to communicate in English
- Subscribe to [mailing list](http://lists.sourceforge.net/mailman/listinfo/jajuk-developers)
- Follow [Git instructions](/git.html)
- No remuneration, Jajuk is a benevolent work
- Every work is copyrighted under GPL license and due to 'Jajuk team', no individual copyrighting


### Daily builds

Jajuk daily builds and test coverage/results are available from the [Jajuk Continuous Integration website](http://integration.jajuk.info:8080). 
Please make sure you didn't broke the build. All unit tests should pass as well or fix them. 

#### Version rules
-   Jajuk releases follow this version scheme: <major>.<minor>.<fix>. Example: 1.1.4 : Fourth fix release of second minor release of first major release.
-   When starting a minor release testing process (about one or two months), we create a specific branch used for fixes (during this time, commiters can continue to work in the trunk). Example: one month before 1.1 official release, a "1.1" branch is created. All fixable bugs found against minor version are double-fixed in the release and in the trunk branches (fix against maintenance branch, then fixes are merged into trunk). For example, an issue discovered in 1.1 is fixed in the ''1_1 ''branch AND in the trunk (1.2 development release).
-   Major and minor releases are maintained during a single minor releases (for example, 1.1 is maintained until 1.2 is released) and a fix pack release (x.y.z) is released ASAP if critical bug found or about every one or two weeks for minor issues.

#### Code names

Codenames in Jajuk refers to songs names that have been performed by different artists but this is not an absolute rule. No more than two or three words easy to remember and eventually to pronounce worldwide.

-    1.11: Deepest Blue by Deepest Blue
-    1.10: Gute Laune by Tosca
-    1.9: Killer Queen by Queen
-    1.8: Breathless by Shankar Mahadevan
-    1.7: Firestarter by Prodigy
-    1.6: Summertime, composed by George Gershwin
-    1.5: Lothlorien By Enya
-    1.4: Aerodynamic by Daft Punk
-    1.3: My Dear Country by Norah Jones 
    
### Major release process

The Jajuk release process usually takes from 8 to 10 weeks.

-   The release process is announced with a message in the developer mailing list (make sure you subscribed to this list). The version branch is then created and all developments are then frozen in this branch (however, it is still possible to work on the next version in trunk). English labels are frozen as well to allow translators to start working.
-   Translators can complete their translations during the entire process. Note that translators can work on current releases even outside release process periods.
-   Testers qualify and developers fixes bugs discovered during this period. An e-mail is send on developer list at each Release Candidate.
-   When we find the last RC stable enough, it is released as a final on Sourceforge and a maintenance branch is created. We wait at least 2 days between last RC and final release
-   The communication delegate sends the news in Freshmeat and other web sites after one week without critical issue

### User documentation

Jajuk is now a pretty large software using a few relatively advanced concepts like perspectives & views, custom properties or devices. As a developer, you will obviously have to know and understand the application concepts. 
All of them are described in the [User guide](/manual/main.html), please make sure to read it in depth and to 
upgrade it required. 
The documentation is done as a Jekyll website available from [https://github.com/jajuk-team/jajuk-team.github.io](https://github.com/jajuk-team/jajuk-team.github.io).


 
