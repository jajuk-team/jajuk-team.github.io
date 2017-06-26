---
title: Build Jajuk
layout: default
---
Go back to the [TOC](/manual/main.html)

# Checkout the sources
``git clone https://github.com/jajuk-team/jajuk.git``   

# Build only jajuk.jar (java build)
([Ant](http://ant.apache.org) is required)  
         
```shell
cd src/scripts
ant -lib . package_jar
```
``jajuk.jar`` is built in the ``/tmp/jajuk-dist/jajuk/bin`` directory

# Build a full Jajuk distribution (Windows, OSX, Linux)
Use the [docker image](https://hub.docker.com/r/bflorat/build-jajuk/), check instructions there.

Go back to the [TOC](/manual/main.html)
