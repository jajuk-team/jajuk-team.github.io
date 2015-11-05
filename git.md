---
title: Git - Jajuk
layout: default
---

# Git

Jajuk leverages Git SCM since jan 2011. This page centralizes information dealing with developing Jajuk with Git.

[1]: http://google.com/- - "Google"
 
###Quick guide for new developers

(Ask on the list if you need help with Git)

- Create a GitHub account
- Fork jajuk on GitHub (it's a matter of clicking on the "fork" button)
- Clone your forked GitHub repository on your own computer (git clone <your GitHub project>)
- Commit your changes into your own jajuk repository on your computer
- Push your commits into your own GitHub repository
- Submit your commits by doing a "pull request" from the GitHub website. IMPORTANT : create a topic branch for each pull request.
- Discuss on your request using the GitHub wiki
- Pull your commits when it's ok 

###Documentation

Git is very powerful and innovative but also very different from Subversion we used previously and is also more complex. We assume that you understand basic concepts of Git. If it is not the case, please read first (by preference order) :

- Git for Eclipse users (quick overview)
- Pro Git online book
- Git community book
- Egit manual 

###Public Git Repository

The Git URL for clone/push is

 ssh://git@github.com:jajuk-team/jajuk.git or https://github.com/jajuk-team/jajuk.git

###Git and Eclipse

Most Jajuk developers currently use Eclipse (but it is not mandatory) and Jajuk is Eclipse-ready (.project and .classpath Eclipse configuration files are provided out of the box). Eclipse recent releases comes with the eGIT plugin enabled.


###Branching workflow
Branching workflow (CC-BY-SA Vincent Driessen)

We use this worflow, please make sure to read it carefully. To sum up :
- The master branch (default git branch) is only for released code and is the most stable code around. Only the integrator should commit to this branch. Make sure to checkout develop branch (see below) before starting to work.
- The develop branch is a permanent branch and is the project mainstream. CI is done against this branch. You should work or merge your changes to this branch.
- A release-x.y branch is created during a release stabilization (few weeks before release) and is kept for maintenance until the release is no more supported. Changes against intermediate releases (RC) are merged back to the develop branch at each RC.
- Topic or hotfix branches for temporary work are encouraged and should be merged into the develop branch. These branches are local only, please don't push them into the GitHub repository, except if they are some kind of test to unforeseeable future integration. 

- Make sure to create a topic branch for every fix or new feature, this makes merges easier.
- Rebasing is encouraged to preserve history from rebased branch. However, please don't rebase commits already pushed to GitHub[1].
- A git-flow super-command is available, we advice its use, see also this screencast. 

See [http://progit.org/book/ch3-6.html](http://progit.org/book/ch3-6.html)

###Social coding

We use GitHub. The most prominent features brought by GitHub to our project are :

- Git public repository (technically, it is a regular Git repository but is our reference)
- Allows to easily comment the commits from a web interface
- Allows easy forking : non members are encouraged to fork Jajuk (done in a single click in GitHub !) and to push "Pull requests" afterwards that the Jajuk members can integrate easily. 

GitHub repositories interactions are summed up bellow

![Jajuk Git interactions](/images/Jajuk_github.png)
