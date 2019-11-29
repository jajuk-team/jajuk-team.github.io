# Windows
Jajuk works with Java 1.8, 9, 11, 13 +
You can use the [Oracle JRE](https://www.java.com/) but we advice to use the fully Open Source AdoptOpenJDK  distribution :
* Download the [AdoptOpenJDK](https://adoptopenjdk.net/index.html) installer
* Launch the installer with the `Updating the JAVA_HOME environment variable` and `Updates registry keys HKLM\SOFTWARE\JavaSoft` options enabled
* Download the Jajuk Windows installer (`Jajuk-setup-<version>.exe</version>`) and launch it.

# Linux (shell installer)

* Install a compatible Java version
Jajuk requires a Java Runtime Environment (JRE) 1.8 or later (tested successfully with openjdk 11 and 13).
If you get an error similar to `java.lang.UnsatisfiedLinkError: Can't load library: /usr/lib/jvm/java-11-openjdk-11.0.5.10-0.fc29.x86_64/lib/libawt_xawt.so`, you use a headless JRE. Try to install a full JRE (`java-11-openjdk-devel.x86_64` for instance).

Note that we no more provide distribution specific package because it has been proved to be too brittle and time consumming. We now provide a simple shell installer that only sets the PATH and creates the app launcher for the current user. The binaries stay in place.

* Downlaod the `jajuk-linux-<version>.tar.gz` file
* Extract it into a definitive location and run the installer :
```
$ cd <location>
$ tar xzpvf jajuk-linux-<version>.tar.gz
$ ./installer 
```
Note that using the installer is optional, you can simply start jajuk from the extracted location :
```
$ ./jajuk
```

# MacOS
* Install Java for MacOS 
* Download the `jajuk-macos-11.0.zip` 
* Extract the app file and launch it
