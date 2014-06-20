
###### DevAcademy Course Notes - Android Fundamental 1

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

# Hello World

After we have ADT Bundle installed, we are ready to create our Android application. First, we will setup Android Emulator also known as Android Virtual Device (AVD), then create New Android app and run it in Emulator.

## Adding new AVD

* in Eclipse menu, click **Window** then click **Android Virtual Device Manager**.

<img src="https://i.cloudup.com/jwo-SKPXU0-3000x3000.png" alt="Start AVD Manager" style="width: 500px;"/>

* You will see AVD Manager window. Click **New** to create new AVD. Fill the field in new AVD dialog
  * AVD Name : You can type any name in this field
  * Device : We will use Nexus S (480x800) since its most common screen size
  * Target : Choose Android SDK version available in your system.
  * Set SD Card size to be 128. 
  * Then click **OK**

<img src="https://i.cloudup.com/Y7av-bdZSG-3000x3000.png" alt="New AVD setting" style="width: 300px;"/>

* After AVD created, select the AVD in AVD Manager list, then click **Start** to start the AVD. If you are running on small monitor, you can choose to scale the display so you can see all the view.

<img src="https://i.cloudup.com/0rVuB_4KLv-3000x3000.png" alt="Launch AVD" style="width: 500px;"/>

* Launcing AVD might takes a while depending on your computer specification. You can close AVD Manager while waiting until it fully launched and start working on Android app. When it finished, click `OK` for every guide that might pop up in Emulator screen.

<img src="https://i.cloudup.com/yZGgFq7uMm-3000x3000.png" alt="Android emulator" style="width: 400px;"/>

## Create new Android Application Project

* In Eclipse menu, click **File** then click **New** then click **Android Application Project** 

<img src="https://i.cloudup.com/cNLIx-10xM-3000x3000.png" alt="New project" style="width: 500px;"/>

* Eclipse will show Android Application Project Wizard. This wizard will help you setup your Android app project. Fill Application Name, Eclipse will auto fill other fields. 
  * You are strongly suggested to change Package name. Package name typically reversed company domain name + application name. Typically in format : `com.YOURCOMPANYNAME.YOURAPPLICATIONNAME`. Package name must be unique as its used to identify one app from another in Android system. For example, if I want to create calculator app, I will use `com.mygreatcompany.calculator`. 
  * Below, you see choices of Android SDK version. Leave that default for now, we will back at this later.

<img src="https://i.cloudup.com/pbT1Jf3fnZ-3000x3000.png" alt="Project wizard" style="width: 500px;"/>

* Click next, use default for all steps until then finally, click Finish. You will see your project is created and Eclipse wil show `MainActivity.java` content.

<img src="https://i.cloudup.com/9bvpXrEsq1-3000x3000.png" alt="Eclipse project view" style="width: 500px;"/>

## Eclipse Project Views

As shown in previous image, there are many panels in Eclipse. Those panels are known as `View`. The default views are annotated and explained below.

<img src="https://i.cloudup.com/O0beC_expK-3000x3000.png" alt="Eclipse project view annotated" style="width: 500px;"/>

1. **Package Explorer**. Show project package files. We will explore this later.
1. **Code View**. This is the main view where you will code and edit .java, layout (.xml or graphical mode) and other files.
1. **Outline**. Outline shows tree representation of code or other files shown in main view. This will help us in navigating the code when it gets too long.
1. **Bottom Panel**. Contains several views. We will add two other views in here.

### Add new view in Eclipse

* In Eclipse menu, click **Window** then click **Show View** the click **Other**.

<img src="https://i.cloudup.com/TQrDtm4mHl-3000x3000.png" alt="Eclipse project view annotated" style="width: 500px;"/>

* In Android section, double click **Devices** to add it to bottom panel. Then add **LogCat** using the same approach. 

<img src="https://i.cloudup.com/lyJn319Rvx-3000x3000.png" alt="Add view" style="width: 500px;"/>

* In **Devices** view, you can see all devices connected to ADT. If you followed this tutorial, you will see Emulator that we created and launched before. If you have Android smartphones and tablets and have necessary driver installed, you will see your devices here.
* **LogCat** provide view for application logging. During Android application development, we will use **LogCat** to view errors and logs in our app.

<img src="https://i.cloudup.com/wI0q_wRFi2-3000x3000.png" alt="Add view" style="width: 500px;"/>

## Launch Application on Emulator

Now that we have our App Project and Emulator ready, we can compile and launch our App to the Emulator. To launch the app, right-click on your Project, click **Run As** then click **Android Application**.

<img src="https://i.cloudup.com/Tw_fBFqfL--3000x3000.png" alt="Run As Android App" style="width: 500px;"/>

You will asked to choose target device (Emulators or actual device). Wait until launcing process finished and you will see your app in the emulator.

<img src="https://i.cloudup.com/v3i6c0axQu-3000x3000.png" alt="Android emulator" style="width: 400px;"/>

Congratulations, you have created and run your first Android app!

## Android SDK Version

When you create new Android project, you see wizard dialog like below. You see options to choose Minimum SDK, Target SDK and Compile With SDK

<img src="https://i.cloudup.com/XjuW2GwfPV-3000x3000.png" alt="Android emulator" style="width: 500px;"/>

* Minimum SDK is the lowest level of Android SDK version that your app will support. There are a lot of new features since Android first introduced. You might want to change minimum SDK if you want to use new API only available from newer SDK. The Android system will prevent the user from installing the application if the system's API Level is lower than the value specified in this attribute.
* Target SDK is the attribute informs the system that you have tested against the target version and the system should not enable any compatibility behaviors to maintain your app's forward-compatibility with the target version.
* Compile With will list SDK available in your computer. By default, this will be the latest version of Android SDK in ADT Bundle which you installed. You can install more version of Android SDK using SDK manager.

You can see details on Android version history [here](http://en.wikipedia.org/wiki/Android_version_history)

### Android SDK Manager

* in Eclipse menu, click **Window** then click **Android SDK Manager**.

<img src="https://i.cloudup.com/jB9p2YaDgu-3000x3000.png" alt="Start AVD Manager" style="width: 500px;"/>

* You will see which SDK version you have installed. If you want to install another SDK version, click of the root of the SDK, check SDK platform then click install. You can also install Google APIs, Samples and Android system image (ARM or Intel version).

<img src="https://i.cloudup.com/NTk07T9NK8-3000x3000.png" alt="Start AVD Manager" style="width: 500px;"/>

