---
title: Jajuk Members Guide
permalink: /Jajuk_Members_Guide/
---

''Welcome to new Jajuk members, have fun ! ''

Executive summary
-----------------

-   Create user accounts on:
    -   For developers on [the ticket system](http://trac.jajuk.info/) and [Gitorious](http://gitorious.org)[1]
    -   [Optional] For any role : on this mediawiki website if you want to edit it.
-   Subscribe to relevant Mailing lists[2]
    -   For any member : [*jajuk-developers*](http://lists.sourceforge.net/mailman/listinfo/jajuk-developers)
    -   For translators only : [*jajuk-i18n*](http://lists.sourceforge.net/mailman/listinfo/jajuk-i18n)
-   [Optional] Subscribe to relevant RSS feeds
    -   Wiki: [Jajuk wiki - Recent changes [en](http://wiki.jajuk.info/index.php?title=Special:Recentchanges&feed=rss)]
    -   Trac timeline: [Jajuk trac: Timeline](http://trac.jajuk.info/timeline?milestone=on&ticket=on&ticket_details=on&wiki=on&max=50&daysback=90&format=rss)
    -   [Gitorious timeline](http://gitorious.org/jajuk/jajuk)[3]
    -   SourceForge [Project summary](http://sourceforge.net/export/rss2_projsummary.php?group_id=91412)

<references/>
Main websites at a glance
-------------------------

|---|---|
|[400px](/Image:website_main.png "wikilink") [Main website](http://jajuk.info)|[400px](/Image:website_trac.png "wikilink") [Trac Ticket manager](http://trac.jajuk.info)|
|[400px](/Image:website_ci.png "wikilink") [Integration server](http://integration.jajuk.info)|[400px](/Image:website_social_coding.png "wikilink") [Social coding](http://gitorious.org/jajuk)|
|[400px](/Image:website_quality.png "wikilink") [Quality Center](http://nemo.sonar.codehaus.org/project/index/org.jajuk:jajuk)|[400px](/Image:website_sf.png "wikilink") [Sourceforge services](http://sf/net/projects/jajuk)|

Project General Rules
---------------------

### Team rules

We ask members to follow these basic rules:

-   Members have to communicate in English
-   Members have to subscribe to relevent communication streams (see [\#Executive summary](/#Executive_summary "wikilink"))

General contract is :

-   No remuneration, Jajuk is a benevolent work
-   Every work is copyrighted under GPL license and due to 'Jajuk team', no individual copyrighting

### Leaving project

-   Members are seen as inactive after a period of 6 months but are welcomed to come back at any time.
-   Former and current members list is available from this [Jajuk Team](/Jajuk_Team "wikilink")

Daily builds
------------

Jajuk daily builds, associated javadoc and test coverage/results are available from the [Jajuk Continuous Integration website](http://integration.jajuk.info).

Official Jajuk Members Roles and Guides
---------------------------------------

|Role name|Role Description|Main Role Guides|
|---------|----------------|----------------|
|Documentation Manager|Organizes and manages documentation|[Documentation Manager Guide](/Documentation_Manager_Guide "wikilink")|
|Documentation Writer|Jajuk documentation maintenance|[Documentation Writer Guide](/Documentation_Writer_Guide "wikilink")|
|Java Developer|Code features in the [trac](/trac "wikilink")|[Java Developer Guide](/Java_Developer_Guide "wikilink")|
|Media Designer|Web and User Interface design|[Media Designer Guide](/Media_Designer_Guide "wikilink")|
|Packager|Create packages for OS distribution|[Packager Guide](/Packager_Guide "wikilink")|
|Project Admin|Project lead manager|[Project Admin Guide](/Project_Admin_Guide "wikilink")|
|Promoter|Public relation, publishing news on forums, download sites, keep them up to date|[Promoter Guide](/Promoter_Guide "wikilink")|
|Tester|Jajuk qualification|[Tester Guide](/Tester_Guide "wikilink")|
|Translator|Jajuk user interface translation|[Translator Guide](/Translator_Guide "wikilink")|
|System Admin|Administrator of project's servers|[System Admin Guide](/System_Admin_Guide "wikilink")|

Check out for open positions on [Help Wanted](/Help_Wanted "wikilink") page

Chat
----

-   Jabber is the default chat system, jajuk@conference.jabber.org is the default chat room.
-   For information, we recommend these jabber clients: Linux: Pidgin, Kopete, Gajim; Windows: Pandion, Exodus; Java: Jeti and this Jabber server: [<span class="icon">jabber.org</span>](http://jabber.org)
-   Chat request: A chat request should be sent under the form of an e-mail on the developer list and contain at least following information:
    -   [CHAT] <subject> as a title
    -   [SUBJECT] <a detailled subject to speak about>
    -   [INVITED] <some people, all the list, a group...>
    -   [MANDATORY] <mandatory people>
    -   [TIME] <date/time (don't forget to provide the timezone you use like UTC/GMT, PST, CET/CEST..)>

Votes
-----

If we are less than 7 active people in the team, the role owner should decide at the end even if the majority is against him. The other persons may not have the expertise to make a decision but everybody is encouraged to express their view.

We use the developer mailing list to send vote requests. Each request should contain following information:

-   [VOTE] in the message title
-   In the message body:
    -   [SUBJECT]: theme and goal of the vote
    -   [METHOD]: voting method of this vote. Standard voting methods are:
        -   [<span class="icon">Apache Group voting system</span>](http://httpd.apache.org/dev/guidelines.html) for binary decisions.
        -   [<span class="icon">Cumulative Vote</span>](http://en.wikipedia.org/wiki/Cumulative_voting) on 100 points for single choice among a set of elements
    -   [DEADLINE]: Provide an ending date for the vote
    -   [VOTING POPULATION]: Details people concerned by the vote
    -   [CHOICES]: Clearly identifies options that can be taken (A, B, C for ie)
    -   [HITS] (recommended): Provide maximum of information to help people taking their decision (advantages/drawbacks for each choice for ie)

Jajuk Brand Identity Guidelines
-------------------------------

See the separate page [Brand Identity Guidelines](/Brand_Identity_Guidelines "wikilink").

Tracker
-------

[Access Jajuk trac system](http://trac.jajuk.info/). Trac is web-based project management and bug-tracking tool. It allows users to create, view and assign tickets to Jajuk Members and developers. Tickets have the main following properties:

-   **Type**: the type of the ticket (e.g.: Bug, Feature, Task, Discussion, etc...)
-   **Component**: the project's part the ticket applies (e.g.: Java Developer, Packager, Tester, etc...)
-   **Version**: the version of Jajuk the ticket is related to
-   **Milestone**: the milestone version of the project the ticket is due to be resolved
-   **Priority**: the priority over tickets of the same component
-   **Status**: *new* (ticket waiting owner to take action), *assigned* (ticket owner has accepted to fix it), *reopened*, *closed*

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

### Trac Administration

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

Each Jajuk major release owns a [code name](/Jajuk_codenames "wikilink") .

Release process
---------------

The Jajuk release process usually takes from 8 to 10 weeks.

-   The release process is announced with a message in the developer mailing list (make sure you subscribed to this list). The version branch is then created and all developments are then frozen in this branch (however, it is still possible to work on the next version in trunk). English labels are frozen as well to allow translators to start working.
-   Translators can complete their translations during the entire process. Note that translators can work on current releases even outside release process periods. Read the [Translator Guide](/Translator_Guide "wikilink") for more information about translation work.
-   Testers qualify and developers fixes bugs discovered during this period. See the [Tester Guide](/Tester_Guide "wikilink"). An e-mail is send on developer list at each Release Candidate.
-   When we find the last [RC](/RC "wikilink") stable enough, it is released as a final on Sourceforge and a maintenance branch is created. We wait at least 2 days between last RC and final release
-   The communication delegate sends the news in Freshmeat and other web sites after one week without critical issue

See also [build a release](/build_a_release "wikilink")

User documentation
------------------

Jajuk is now a pretty large software using a few relatively advanced concepts like perspectives & views, custom properties or devices. As a developer, you will obviously have to know and understand the application concepts. All of them are described in the [User guide](http://jajuk.info/manuals.html), please make sure to read it in depth.

[Category:Workspaces](/Category:Workspaces "wikilink") [Category:Jajuk Members Workspace](/Category:Jajuk_Members_Workspace "wikilink")

[1] Once your Gitorious account created, you can watch the [Gitorious](http://gitorious.org/jajuk) public Jajuk git repository] and clone it. Then you will be able to submit your changes to the official repository using the 'Merge request' feature. Long term coders may become members of the core team, then be able to push directly to the official repository.

[2] Please note that most communication is done using these mailing lists.

[3] Note that a daily digest of the gitorious activity is also send on the developer mailing list.