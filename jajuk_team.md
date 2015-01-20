---
title: Jajuk Team - Jajuk
layout: default
---

''Welcome to new Jajuk members, have fun ! ''

A successful project requires many people to play many roles. Some members write code or documentation, while others are valuable as testers, submitting patches and suggestions.

Contact us on :

 - [Twitter](http://twitter.com/jajukproject)

 - [Google+](https://plus.google.com/116653776869968419005)

Want to help : subscribe to [mailing list](http://lists.sourceforge.net/mailman/listinfo/jajuk-developers)

The team is comprised of Members and Contributors. Members have direct access to the source of a project and actively evolve the code-base. Contributors improve the project through submission of patches and suggestions to the Members. The number of Contributors to the project is unbounded. Get involved today. All contributions to the project are greatly appreciated.

<a name="Executive summary">Executive summary</a>
-----------------

- Follow [Git instructions](/git.html)

Main websites at a glance
-------------------------

<table id="screenshots">
<tr>
	<td><img src="/images/website_main.png" style="width:350px;" title="Main website" alt="Main website"/> <a href="http://www.jajuk.info">Main website</a></td>
	<td><img src="/images/website_github.png" style="width:350px;" title="Github" alt="Github"/> <a href="https://github.com/jajuk-team/jajuk">Github</a></td>
</tr>
<tr>
	<td><img src="/images/website_hudson.png" style="width:350px;" title="Integration server" alt="Integration server"/> <a href="http://integration.jajuk.info">Integration server</a></td>
	<td><img src="/images/website_quality.png" style="width:350px;" title="Quality Center" alt="Quality Center"/> <a href="http://nemo.sonarqube.org/dashboard/index/org.jajuk:jajuk">Quality Center</a></td>
</tr>
</table>

Project General Rules
---------------------

### Team rules

We ask members to follow these basic rules:

-   Members have to communicate in English
-   Members have to subscribe to relevent communication streams (see [our Git page](/git.html))

General contract is :

-   No remuneration, Jajuk is a benevolent work
-   Every work is copyrighted under GPL license and due to 'Jajuk team', no individual copyrighting

### Leaving project

-   Members are seen as inactive after a period of 6 months but are welcomed to come back at any time.

Daily builds
------------

Jajuk daily builds, associated javadoc and test coverage/results are available from the [Jajuk Continuous Integration website](http://integration.jajuk.info).

Official Jajuk Members Roles and Guides
---------------------------------------

|Role name|Role Description||
|---------|----------------|----------------|
|Documentation Manager|Organizes and manages documentation|The doc manager is responsible for the documentation health. He will probably be doc writer himself but also organizes and manages others contributors in this area.|
|Documentation Writer|Jajuk documentation maintenance||
|Java Developer|Code features||
|Media Designer|Web and User Interface design||
|Packager|Create packages for OS distribution||
|Project Admin|Project lead manager||
|Promoter|Public relation, publishing news on forums, download sites, keep them up to date||
|Tester|Jajuk qualification||
|Translator|Jajuk user interface translation|Translators should subscribe on the translators mailing list to get information about internationalization issues and translation update needs. |
|System Admin|Administrator of project's servers|The role of Jajuk System Admin is to maintain the different servers of the project. Instructions to build, maintain, backup and restore the server platform are available in the internal SysAdmin guide. |

Chat
----

-   Jabber is the default chat system, jajuk@conference.jabber.org is the default chat room.
-   For information, we recommend these jabber clients: Linux: Pidgin, Kopete, Gajim; Windows: Pandion, Exodus; Java: Jeti and this Jabber server: [<span class="icon">jabber.org</span>](http://jabber.org)
-   Chat request: A chat request should be sent under the form of an e-mail on the developer list and contain at least following information:
    -   \[CHAT\] subject as a title
    -   \[SUBJECT\] a detailled subject to speak about
    -   \[INVITED\] some people, all the list, a group...
    -   \[MANDATORY\] mandatory people
    -   \[TIME\] date/time (don't forget to provide the timezone you use like UTC/GMT, PST, CET/CEST..)

Votes
-----

If we are less than 7 active people in the team, the role owner should decide at the end even if the majority is against him. The other persons may not have the expertise to make a decision but everybody is encouraged to express their view.

We use the developer mailing list to send vote requests. Each request should contain following information:

-   \[VOTE\] in the message title
-   In the message body:
    -   \[SUBJECT\]: theme and goal of the vote
    -   \[METHOD\]: voting method of this vote. Standard voting methods are:
        -   [<span class="icon">Apache Group voting system</span>](http://httpd.apache.org/dev/guidelines.html) for binary decisions.
        -   [<span class="icon">Cumulative Vote</span>](http://en.wikipedia.org/wiki/Cumulative_voting) on 100 points for single choice among a set of elements
    -   \[DEADLINE\]: Provide an ending date for the vote
    -   \[VOTING POPULATION\]: Details people concerned by the vote
    -   \[CHOICES\]: Clearly identifies options that can be taken (A, B, C for ie)
    -   \[HITS\] (recommended): Provide maximum of information to help people taking their decision (advantages/drawbacks for each choice for ie)

### General Jajuk Teams trac rules

Following rules apply to tickets:

-   Please create a 'Task' ticket even for small changes
-   When closing a ticket: please provide a comment. If the ticket is referring to other tickets (especially for *duplicate tickets*), please give the tickets references in your comment. You can easily search for other tickets with trac search function.
-   Tickets not related to the Jajuk software itself (server works, promotion, tools...) should not have assigned version or milestone number (set void version and void roadmap).

### TODO after a fix or a feature coding

-   If not already done, assign ticket to yourself (so we know did what)
-   Close the ticket once done (it is sometimes difficult to know if a ticket is done when a lot of ticket are still opened)
-   For bugs, write as a comment on which branch (usually trunk and last maintenance branch) you applied the fix so we don't have to check this later.
-   For bugs to fix on several branches : please fix only the maintenance branch, not trunk as we will merge all changes on the maintenance branch to trunk at each fixpack release.

### Github issues administration

Manage Milestones:

-   The default **Milestone** must be set to *"To Be Qualified by Jajuk Team"*
-   When releasing a new Jajuk version, the current **milestone** version must be closed

Manage Versions:

-   A **version** must be created per already released version
-   The default **version** must be set to <void> to force users to select a release
-   When releasing a new Jajuk version, the current **version** must be created

Version rules
-------------

-   Jajuk releases follow this version scheme: <major>.<minor>.<fix>. Example: 1.1.4 : Fourth fix release of second minor release of first major release.
-   When starting a minor release testing process (about one or two months), we create a specific branch used for fixes (during this time, commiters can continue to work in the trunk). Example: one month before 1.1 official release, a "1.1" branch is created. All fixable bugs found against minor version are double-fixed in the release and in the trunk branches (fix against maintenance branch, then fixes are merged into trunk). For example, an issue discovered in 1.1 is fixed in the ''1_1 ''branch AND in the trunk (1.2 development release).
-   Major and minor releases are maintained during a single minor releases (for example, 1.1 is maintained until 1.2 is released) and a fix pack release (x.y.z) is released ASAP if critical bug found or about every one or two weeks for minor issues.

### Code names

Codenames in Jajuk refers to songs names that have been performed by different artists but this is not an absolute rule. No more than two or three words easy to remember and eventually to pronounce worldwide.

-    1.11: Deepest Blue by Deepest Blue
-    1.10: Gute Laune by Tosca
-    1.9: Killer Queen by Queen
-    1.8: Breathless by Shankar Mahadevan
-    1.7: Firestarter by Prodigy
-    1.6: Summertime, composed by George Gershwin
-    1.5: Lothlorien By Enya, from Shepherd Moons album
-    1.4: Aerodynamic by Daft Punk
-    1.3: My Dear Country, from Norah Jones, album Not Too Late 
    
Release process
---------------

The Jajuk release process usually takes from 8 to 10 weeks.

-   The release process is announced with a message in the developer mailing list (make sure you subscribed to this list). The version branch is then created and all developments are then frozen in this branch (however, it is still possible to work on the next version in trunk). English labels are frozen as well to allow translators to start working.
-   Translators can complete their translations during the entire process. Note that translators can work on current releases even outside release process periods.
-   Testers qualify and developers fixes bugs discovered during this period. An e-mail is send on developer list at each Release Candidate.
-   When we find the last RC stable enough, it is released as a final on Sourceforge and a maintenance branch is created. We wait at least 2 days between last RC and final release
-   The communication delegate sends the news in Freshmeat and other web sites after one week without critical issue

User documentation
------------------

Jajuk is now a pretty large software using a few relatively advanced concepts like perspectives & views, custom properties or devices. As a developer, you will obviously have to know and understand the application concepts. All of them are described in the [User guide](/jajuk_manual.html), please make sure to read it in depth.


<a name="donation">Donate</a>
------
If you use Jajuk and want to help the project to be financially balanced, please use the donate SourceForge page to send money to the project. See the [project budget](/budget.html).

If you are a Flattr user, you may want to flattr this project (see the Flattr icon on every page of this website)

Bitcoin donation : 1M1hLxNbKux81DQjdK9mTbMZv54vPvYDB5 




[3] Note that a daily digest of the gitorious activity is also send on the developer mailing list.
