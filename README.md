# Android programming @ Coventry University

![](.md_images/347.JPG)

Hello! Welcome to Android activities at Coventry University experience day!

In this session, you'll have a little taste of what our students do at Coventry. In particular, what you see right now is a (much) simplified version of the material we use for our undergraduate module 'Mobile Applications Development'. If you're curious, the full set of material can be found here:

* [Android App Development](https://github.com/covcom/300CEM)
* [iOS App Development](https://github.com/covcom/301CEM)

## A little background

First of all, let's ask a question - what is Android? Well, the answer depends on who you ask. There're several different levels to define Android: on the very deep level, it's a Linux operating system that controls a bunch of hardware and sensors. This is the same as any other operating systems such as Mac/Windows; on the very superficial level, Android are devices such as Samsung Galaxy or HTC; For us, Android developers, Android is an application runtime that we can develop mobile apps.

Android has been around for a while, hence we have different versions. For each version of Android, we have a 'sweet' codename with the latest being 'Nougat' (Android 7.0)

![Android Codename](http://www.geektech.in/wp-content/uploads/2016/07/Android-Nougat-Release-Date.png)

What do I need to become an Android developer? The short answer is you'll need the Java language and Android Studio, which is an IDE (integrated development environment). And of course a smart brain! Some will ask, do I have to have an Android device to be a developer? No, you don't. Even though last year our students were given Moto 360s (Moto E2s the year before, all free of charge), you don't have to own an Android device.

## A step-by-step tutorial

In this section, you have 2 small tasks to achieve, each of which will last about 20 minutes. If you get stuck at any time, put your hands up and someone will help you. I assume you all know something about programming. If not, let us know. 

### Task 1: start a project from template

Follow the steps below to create and run your first Android app:

1. Click the Start menu and navigate to Android Studio, click on it to start the application.
    
    ![start](.md_images/start.png)
    
    If you see the following window, choose 'I do not have...' and click OK.
    
    ![start](.md_images/install.png)
    
2. Then click on 'Start a new Android Studio project'.
    
    ![start](.md_images/new.png)
    
3. In the window that pops up, give it a name such as 'Hello Android'. In 'Project location' settings select your desired location.
    
    ![start](.md_images/hello.png)
        
4. Next screen asks you to choose minimum SDK. The default value should do. If you want to know more about this minimum SDK, click on 'Help me choose' and read the info that comes up. 
    
    ![Android_Platform_API_Version_Distribution](.md_images/Android_Platform_API_Version_Distribution.png)
    
5. Keep clicking Next until you see Finish. Then click Finish to create your first Android project. Your screen should look similar to below:
     
    ![activity_main_xml_-_Hello_Android](.md_images/activity_main_xml_-_Hello_Android.png)
    
    If this is the first time Android Studio is being run on the computer, this step might take a while. You need to wait until the taskbar finishes to move to the next step.
    
    ![start](.md_images/build.png)
    
6. You're ready to run the app you just created. The reason you don't have to own an Android device to become a developer is that you can run an Android simulator. That is a computer program that simulates the behavior of a real Android phone or tablet. Now let's make sure you have the default AVD installed. 
    
    Click Tools ==> Android ==> AVD Manager to show the AVD Manager
    
    ![start](.md_images/avd.png)
    
    You should see something similar to below (
    
    > If you're lucky to be in the second group, you'll have one created for you already. You can safely ignore this step, or you can still create a new one if you wish.
    
    ![start](.md_images/newavd.png)
    
    Click 'Create Virtual Device' button and use system image API 23 to create a new one (the other image that is available is API25, try not to use it as it hasn't been fully tested). 
    
    Once created, click the little green triangle to run it. You might have to wait a while for it to load.
    
    ![start](.md_images/runavd.png)
    
    On some of the machines, this will give you an error 'Cannot launch AVD in emulator'. If this happens to you, we have Nexus 7 tablets to run your app.
5. Now click Run ==> Run 'app' to run the app you just created. In the window that pops up, click 'Launch emulator' and choose the desired AVD if you have more than one. BTW, you should only have 1 AVD running, otherwise, the system will be rather slow. You will see HelloAndroid running in AVD similar to the one below.
    
    ![hello_android](.md_images/hello_android.png)
    
### Task 2: customize layouts and run on a real device

This task will again take about 20 minutes to complete. Follow steps below to create another app:

1. In Android Studio, click 'Start a new Android Studio project', and give it a name such as 'Hello Me'.
2. In 'Project location' settings select your desired location. 
3. Use all default settings until you see Finish. These steps are the same as in the previous section and should become the *de facto* standard.
4. Double click to open 'activity_main.xml' if it’s not opened already.
    
    ![Content main](.md_images/content_main.png)
    
5. Under default settings, the 'Text' view will show. If not, click on the Text tab to switch to the text view. Then, click 'Preview' tool window to the right edge of the IDE to bring up the Preview window. Your whole workbench should look similar to below.
    
    ![Content main](.md_images/text_view.png)
    
6. Delete texts contained between '<span>&lt;</span>TextView' and the closing '/>'. You'll see that the words 'Hello World' disappeared on the preview window.
        
7. Click the 'Design' tab to switch to the design view. Locate and drag the following four widgets from Palette to the layout one by one:  TextView, (another) TextView, Plain Text, and Button. Your Component Tree should look at the following
    
    ![Content main](.md_images/component_tree.png)
    
8. At this point, if you click one of the widgets you just dragged onto the graphical layout, you can change its properties using the Properties window. Try to change some of the properties to see the effects, and we’ll change them back later.
    
    > The graphical layout in the design view is not to be confused with preview in the text view. The preview tool is more powerful for example sometimes it gives error messages such as 'Rendering Problems'.
    
9. Click the 'Text' tab to go back to the text view. Manually edit the xml file, make it look like the following
    
    ```xml
    <TextView
      android:id="@+id/textViewDisplay"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_alignParentLeft="true"
      android:layout_alignParentStart="true"
      android:layout_alignParentTop="true"
      android:text="Hellow World"
      android:textSize="24sp" />

    <TextView
      android:id="@+id/textView2"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_alignLeft="@+id/textViewDisplay"
      android:layout_alignStart="@+id/textViewDisplay"
      android:layout_below="@+id/textViewDisplay"
      android:layout_marginLeft="19dp"
      android:layout_marginTop="56dp"
      android:text="Name:"
      android:textAppearance="@style/TextAppearance.AppCompat.Small" />

    <EditText
      android:id="@+id/editText"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_alignBaseline="@id/textView2"
      android:layout_alignBottom="@id/textView2"
      android:layout_marginLeft="36dp"
      android:layout_toRightOf="@id/textView2"
      android:ems="10"
      android:inputType="textPersonName" />

    <Button
      android:id="@+id/button"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_below="@+id/editText"
      android:layout_marginTop="22dp"
      android:layout_centerHorizontal="true"
      android:text="Display" />
    ```
    
10. Open MainActivity.java, create a method called onButtonClick that looks like below:
    
    ```java
     public void onButtonClick(View view) {
        EditText editName = (EditText) findViewById(R.id.editText);
        TextView textDisplay = (TextView) findViewById(R.id.textViewDisplay);
        String nameToDisplay = editName.getText().toString();
        textDisplay.setText("Hello " + nameToDisplay);
    }
    ```
    Note when you first use a class that hasn't been imported, Android Studio will show the class name in red. You'll need to import the class. The keyboard shortcut to do the importing is 'alt' + 'enter'.
    
11. Go back to the layout file activity_main.xml you modified earlier, change the Button tag to include the following attribute:
    
    ```xml
    android:onClick="onButtonClick"
    ```
    > In order to create a method that responds to user clicks, the method needs to have a signature of 'public void doSomething(View view)'.
    
12. Now you need to ask one of our staff to connect Nexus 7 to your machine so you can run the app on a real device.

13. Run this app and select Nexus 7 as the target. Once you input something, for example, your name and click Display, your name will appear in the greeting message. 
    
    ![hello jianhua](.md_images/hello_jianhua.png)

## Our past students and projects

We're **one of the first** UK universities that offer courses in mobile app development. In fact, our past students have done some excellent work in the course and are very successful in their career. 

Here are some projects and apps our students developed for the module and also in their free time:

![](https://github.com/freshollie/MonkeyboardAndroidRadioApp/raw/master/screenshots/main_interface.png)

[Monkeyboard Android Radio App](https://github.com/freshollie/MonkeyboardAndroidRadioApp) created by Oliver Bell, who is currently a 2nd-year Computer Science student completed our Android module in 2016.

![](https://lh3.googleusercontent.com/NDC_hS0j9dXtLqYbuhb0iYavYdTCcXlmyAwNj1r2l16bCvksguZDwBRp7TWCd6u4Agk=h310-rw)

Swiftnotes is an Android app developed by Adrian Chifor. The app is available in [Play store](https://play.google.com/store/apps/details?id=com.moonpi.swiftnotes) and source code for the app can be found [here](https://github.com/adrianchifor/Swiftnotes).

![](.md_images/furger.png)

Squash Simulation is an Android app developed by Fabian Furger. Sourcecode for the app can be found [here](https://github.com/furgerf/Squash/tree/master/Squash%20Simulation). There's an introduction for this app on [YouTube](https://www.youtube.com/watch?v=4VqZXWbodaY).

**Have fun! Hope to see you soon!**