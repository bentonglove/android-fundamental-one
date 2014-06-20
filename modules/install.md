
###### DevAcademy Course Notes - Android Fundamental 1

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

# Android SDK Installation

Before we can start developing apps for Android, we need to install Android SDK (Software Development Kit) available in [Android developer website](http://developer.android.com/sdk/index.html). The Android SDK provides the API libraries and developer tools necessary to build, test, and debug apps for Android.

<br/>
## Android Developer Tools (ADT Bundle)

Download ADT Bundle which include Eclipse IDE (Integrated Development Environment) and ADT plugins from [here](http://developer.android.com/sdk/index.html). ADT bundle includes :

* Eclipse + ADT plugin
* Android SDK Tools
* Android Platform-tools
* The latest Android platform
* The latest Android system image for the emulator

<img src="https://i.cloudup.com/4g_jqNX328-3000x3000.png" alt="Download ADT Bundle" style="width: 500px;"/>

<br/>

The choice between 32 bit and 64 bit is depend on your computer processor. 

After downloading ADT, extract the zip file in your computer (for example, if using Windows to drive `C:\` then optionally rename the folder to `adt-bundle` - thus become `C:\adt-bundle`).

You should see in the `C:\adt-bundle` folder 
* eclipse/
* sdk/

<img src="https://i.cloudup.com/YxOdy896PL-3000x3000.png" alt="ADT Bundle" style="width: 500px;"/>

<br/>

#### Note on ADT Bundle location

ADT Bundle location in your computer might be different from this notes. Please adjust the path accordingly when you have to deal with ADT Bundle location throughout this notes.

#### Note on Operating System

In this notes, we will use Windows as reference. However, there should be not much difference with other Operating System such as Mac OS or Linux. The difference maybe in folder name convention. For example, your ADT bundle folder might be :

* In Windows : `C:\adt-bundle`
* In Mac OS and Linux : `/FOLDER/adt-bundle`

<br/>
## Installing prerequisites

Before you can run Eclipse with ADT plugins, you need to install Java SE JDK 6 or 7 available [here](http://www.oracle.com/technetwork/java/javase/downloads/index.html). 

Make sure Java is available on the `PATH`. To test, open `cmd.exe` then type `java -version`. If all setup correctly you will see some lines like shown below.

<img src="https://i.cloudup.com/_6YXO7D6qN-2000x2000.png" alt="Java -version" style="width: 500px;"/>

To setup Java in `PATH`, see guidelines in notes below

#### Java installation notes

* **JDK and JRE.** Make sure to download JDK not JRE. JDK include tools to build Java application, while JRE only include runtime to run Java application.
* **64 bit and 32 bit JDK.** If you choose to download 64 bit version of ADT Bundle, then you must install 64 bit version of JDK and same apply for 32 bit version. Otherwise you will see error when starting Eclipse. Note that ADT Bundle 32 bit can run in Windows 64 bit but ADT Bundle 64 bit can not run in Windows 32 bit.

#### Setup Java on Windows Path

These steps only applied for Windows OS. Other operating system should have their own method. Please check yourself for tutorial on internet for setup `Path` in another OS.

* Open **Environment Variables** dialog by right-click on **Computer** then click menu **Properties**

<img src="https://i.cloudup.com/G8KQCcQ3xV-3000x3000.png" alt="Computer properties" style="width: 500px;"/>

* Click **Advanced system setting** then click **Environment Variables**.

<img src="https://i.cloudup.com/QUTpVFvAkS-3000x3000.png" alt="Environment Variables" style="width: 500px;"/>

* In **System Variables**, Scroll down until you find `Path`, click on the `Path`, a dialog will pop up.
* In Variable value, add path to Java installation in your computer preceeded by `;`. For example in my computer I would add: `;C:\Program Files\Java\jdk1.7.0_51\bin`. 

<img src="https://i.cloudup.com/KFsvOihPEE-3000x3000.png" alt="Add Java to Path" style="width: 500px;"/>

* *NOTE* : Make sure you set correct path pointing to Java installation. Depending on your OS, 32 or 64 bit version, the path might be `C:\Program Files (x86)\Java` or `C:\Program Files\Java`.

## Add Android Tools in Path

Some of ADT components can be executed from command line. One of that tools is `adb` with stand for Android Debug bridge. To use these tools from command line, add two folder below to OS `Path` using previously explained steps.

* `C:\adt-bundle\sdk\platform-tools`
* `C:\adt-bundle\sdk\tools`

<br/>
## Opening Eclipse

When all is set. Start Eclipse from bly clicking `eclipse.exe` in `C:\adt-bundle\eclipse\eclipse.exe`. 

<img src="https://i.cloudup.com/WZZwAK7z7G-3000x3000.png" alt="Eclipse" style="width: 500px;"/>

After Eclipse initialized, you will be asked to select a workspace. You can continue with default folder shown or browse new location for workspace in your harddrive. 

<img src="https://i.cloudup.com/SDm3rK498f-3000x3000.png" alt="Workspace" style="width: 500px;"/>

You will then see Contribute Usage Statistics dialog. Choose between `Yes` or `No`. You will see Android IDE Welcome screen. 

<img src="https://i.cloudup.com/K1RdENQiVA-3000x3000.png" alt="Welcome" style="width: 500px;"/>

Close the Welcome screen by clicking `x` button in Android IDE tab and the Eclipse main workspace will be displayed.

<img src="https://i.cloudup.com/zoQ8CVPcKE-3000x3000.png" alt="Eclipse default view" style="width: 500px;"/>

<br/>
## Troubleshooting

* Error message : `A Java Runtime Environment (JRE) or Java Development Kit (JDK) must be available ...`. This is because Java is not available in `Path`. Follow steps outlined before on how to setup Java on Windows `Path`.
* Error message : `Failed to load the JNI shared library ...`. The following can cause this error. 
  * Mismatch architecture version (32 bit/64 bit) between Eclipse in ADT Bundle and Java. If you choose to download 64 bit version of ADT Bundle, then you must install 64 bit version of JDK and same apply for 32 bit version.
  * You have more than one version of Java in your OS. Mostly you have Windows 64 bit and you have several Java installed. To force Eclipse to choose 64 bit version of Java, open `eclipse.ini` and add following lines  

```
  -vm
  C:\Program Files\Java\jdk1.7.0_51\bin\javaw.exe
```
below the lines for `-showsplash` setting so it becomes

```
  -startup
  plugins/org.eclipse.equinox.launcher_1.3.0.v20120522-1813.jar
  --launcher.library
  plugins/org.eclipse.equinox.launcher.win32.win32.x86_1.1.200.v20120913-144807
  -product
  com.android.ide.eclipse.adt.package.product
  --launcher.XXMaxPermSize
  256M
  -showsplash
  com.android.ide.eclipse.adt.package.product
  -vm
  C:\Program Files\Java\jdk1.7.0_51\bin\javaw.exe
  --launcher.XXMaxPermSize
  256m
  --launcher.defaultAction
  openFile
  -vmargs
  -Dosgi.requiredJavaVersion=1.6
  -Xms40m
  -Xmx768m
  -Declipse.buildId=v22.3.0-887826
  -XX:MaxPermSize=512M
```


