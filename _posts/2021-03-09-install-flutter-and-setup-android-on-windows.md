---
id: 85
title: 'How to Install Flutter and Setup Android on Windows [Step by Step]'
date: '2021-03-09T08:29:37+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.stackvidhya.com/?p=85'
permalink: /install-flutter-and-setup-android-on-windows/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_seo_score:
    - '79'
rank_math_focus_keyword:
    - 'install flutter'
rank_math_primary_category:
    - '2'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
inline_featured_image:
    - '0'
rank_math_analytic_object_id:
    - '53'
ss_social_share_disable:
    - '0'
socialsnap_share_count_timestamp:
    - '2023-08-31 23:27:16'
ss_total_share_count:
    - '0'
ss_ss_click_share_count_envelope:
    - '1'
rank_math_og_content_image:
    - 'a:2:{s:5:"check";s:32:"86dac6d1bbfc9be0b4db91069c80973e";s:6:"images";a:0:{}}'
categories:
    - Flutter
tags:
    - flutter
    - installation
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

[Flutter](http://flutter.dev/) is one of the tools for developing native cross platform applications for Android, iOS, web and Desktop with single Programming Language ([Dart](https://www.dart.dev)) and Codebase.

As the [Official Flutter Docs](https://flutter.dev/) says,

> Flutter is Google’s UI toolkit for building beautiful, natively compiled applications for [mobile](https://flutter.dev/docs), [web](https://flutter.dev/web), and [desktop](https://flutter.dev/desktop) from a single codebase.

In this tutorial, you’ll learn how to install Flutter and setup Android in your Windows Machine.

## <span class="ez-toc-section" id="pre-requisites"></span>Pre-Requisites<span class="ez-toc-section-end"></span>

- System with Windows OS 7 or later.
- [Windows PowerShell 5.0](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-windows-powershell) (Preinstalled with Windows 10).
- [Git for Windows](https://git-scm.com/download/win) . Ensure you select **Use Git from the Windows Command Prompt** while installing.

## <span class="ez-toc-section" id="step_1_%e2%80%93_downloading_the_flutter_sdk"></span>Step 1 – Downloading the Flutter SDK<span class="ez-toc-section-end"></span>

In this step, you’ll download the Flutter SDK (Software Development Kit).

Flutter SDK is the collection of tools that compiles the Dart code to native machine code for Android, iOS, web and Desktop.

First, head over to [Windows install – Flutter](https://flutter.dev/docs/get-started/install/windows).

Next, Click the button shown in the image below.  
![Download Flutter SDK](https://imgur.com/cXKYZgh.jpg)

You’ll see that Flutter SDK is downloading as zip file.

Finally , after the SDK file is downloaded. Go to the zip file and extract it to a Folder of your choice.

Don’t extract your files to location where you need Administrator priviliges like C:\\Program Files\\. Instead, make sure you extract in a different folder like C:\\src\\flutter\\

You’ve successfully installed Flutter on your Windows machine.

### **Optional**

You can execute Flutter Commands by moving to the extracted folder under bin directory.

Open the command prompt and execute the below command.

```
<pre class="wp-block-code">```
cd C:\src\flutter\bin
```
```

Now the current working directory of the command will be changed to flutter installation directory.

Execute the below command.

```
<pre class="wp-block-code">```
flutter --version
```
```

You’ll see the below output.

```
<pre class="wp-block-code">```
Flutter 1.22.6  
```
```

In the next step, you’ll update the System path pointing to the `flutter\bin` directory.

## <span class="ez-toc-section" id="step_2_%e2%80%93_updating_the_system_path"></span>Step 2 – Updating the System Path<span class="ez-toc-section-end"></span>

In this step, you’ll update the System path to access flutter.exe so you can access the `flutter` commands anywhere from the system.

First, you’ll search for `env` in your Windows search. (or) you can open **Edit your System Environment Variables** from your Control panel.

Next, click the *Edit your System Environment Variables*.  
You’ll see a new Window named **Environment Variables** is being opened.  
![Environment variables in Windows](https://imgur.com/Ir0rz6V.jpg)  
Next, Under the *User Variables* select **path**.

**Note:** If path is not present in your *User Variables*, you will create a new variable named *path*.

Next, add the value as `path/to/the/flutter/bin/`.

For Example, `C:\src\flutter\bin\`. Ensure you replace the value with your local file path to `flutter\bin\`.

Finally, press the OK button.

`If you've already installed Dart on your system. then add the `path/to/the/flutter/bin/` before `path/to/the/Dart/bin`.<br></br>You've successfully setup Flutter command line interface by adding the `flutter\bin` in your path.`

## <span class="ez-toc-section" id="step_3_%e2%80%93_running_flutter_commands"></span>Step 3 – Running Flutter Commands<span class="ez-toc-section-end"></span>

In this step, you’ll learn some basic commands in Flutter.  
First, you’ll execute the below command in your Command prompt.

```
<pre class="wp-block-code">```
flutter
```
```

You’ll see the below output.

```
<pre class="wp-block-code">```
Manage your Flutter app development.

Common commands:

  flutter create <output directory>
    Create a new Flutter project in the specified directory.

  flutter run [options]
    Run your Flutter application on an attached device or in an emulator.

Usage: flutter <command> [arguments]

Global options:
-h, --help                  Print this usage information.
-v, --verbose               Noisy logging, including all shell commands
                            executed.
                            If used with --help, shows hidden options.
-d, --device-id             Target device id or name (prefixes allowed).
    --version               Reports the version of this tool.
    --suppress-analytics    Suppress analytics reporting when this command runs

    --packages              Path to your ".packages" file.
                            (required, since the current directory does not
                            contain a ".packages" file)

Available commands:
  analyze           Analyze the project's Dart code.
  assemble          Assemble and build flutter resources.
  attach            Attach to a running application.
  bash-completion   Output command line shell completion setup scripts.
  build             Flutter build commands.
  channel           List or switch flutter channels.
  clean             Delete the build/ and .dart_tool/ directories.
  config            Configure Flutter settings.
  create            Create a new Flutter project.
  devices           List all connected devices.
  doctor            Show information about the installed tooling.
  downgrade         Downgrade Flutter to the last active version for the curren

                    channel.
  drive             Runs Flutter Driver tests for the current project.
  emulators         List, launch and create emulators.
  format            Format one or more dart files.
  gen-l10n          Generate localizations for the Flutter project.
  install           Install a Flutter app on an attached device.
  logs              Show log output for running Flutter apps.
  precache          Populates the Flutter tool's cache of binary artifacts.
  pub               Commands for managing Flutter packages.
  run               Run your Flutter app on an attached device.
  screenshot        Take a screenshot from a connected device.
  symbolize         Symbolize a stack trace from an AOT compiled flutter
                    application.
  test              Run Flutter unit tests for the current project.
  upgrade           Upgrade your copy of Flutter.

Run "flutter help <command>" for more information about a command.
Run "flutter help -v" for verbose help output, including less commonly used
options.
```
```

You will use `flutter doctor` command to know about the tools, which are required to run Flutter.  
Finally, You’ll run the below command to check whether the installation is successful along with detailed report of the components.

```
<pre class="wp-block-code">```
flutter doctor
```
```

  
— **flutter** – specifies the base command for Flutter.  
— **doctor** – gives a detailed report of the Flutter installation.

You’ll see the below output.

```
<pre class="wp-block-code">```
Doctor summary (to see all details, run flutter doctor -v):
[√] Flutter (Channel stable, 1.22.6, on Microsoft Windows [Version 6.1.7601],
    locale en-US)
[✗] Android toolchain - develop for Android devices  
✗ Unable to locate Android SDK.  
Install Android Studio from:  
[https://developer.android.com/studio/index.html](https://developer.android.com/studio/index.html)  
On first launch it will assist you in installing the Android SDK  
components.  
(or visit [https://flutter.dev/setup/#android-setup](https://flutter.dev/setup/#android-setup) for detailed  
instructions).  
If the Android SDK has been installed to a custom location, set  
ANDROID_HOME to that location.  
You may also want to add it to your PATH environment variable.
...
```
```

You’ll see that there was issue in your Android SDK. (If there is no issue for you in Android SDK, you can feel free to skip ahead to Step 5 – Installing Plugins for Adroid Studio).

You’ll learn how to install Android SDK in the next step.

## <span class="ez-toc-section" id="step_4_%e2%80%93_setting_up_android_sdk"></span>Step 4 – Setting Up Android SDK<span class="ez-toc-section-end"></span>

In this step, you’ll install Android Studio and setup Android SDK.

First, download Android Studio as zip file or executable file from the [Official site](https://developer.android.com/studio).  
![Download Android Studio Button](https://imgur.com/QCS2VGN.jpg)

Next, you’ll install the Android Studio by following the setup wizard.

**Note:** Android SDK will be downloaded when you install Android Studio.

Press the Finish Button.

In the Next window, hoose the ‘**Don’t import Settings option**’.

Finally, press the **OK** button.

You’ve successfully installed Android Studio and setup Android SDK in your Windows machine.

## <span class="ez-toc-section" id="step_5_%e2%80%93_installing_plugins_for_android_studio"></span>Step 5 – Installing Plugins for Android Studio<span class="ez-toc-section-end"></span>

In this step, you’ll install Flutter and Dart plugins in Android Studio.

First, open Android Studio.

Then, click **Configure**, then, click **Plugins**.

**Note:** If your using older version( &lt; v3.6.3.0 ) of Android Studio, First, you’ll go to **File&gt;Settings&gt;Plugins**. then, Select **Marketplace**.

Next, Select Flutter and Dart plugin.

Finally, press Yes when prompted

**You’ve to restart Android Studio** to see the newly added plugins.

You’ve **successfully setup Android Studio as a Code Editor** for Flutter.

In the next step, you’ll setup Android Emulator.

## <span class="ez-toc-section" id="step_6_%e2%80%93_setting_up_android_emulator"></span>Step 6 – Setting Up Android Emulator<span class="ez-toc-section-end"></span>

In this step, you’ll use the Android Virtual Device (AVD) manager to setup a Android Virtual Device.

AVD Manager is a tool that comes with Android Studio. It helps you to build and maintain Android Virtual Devices on the go. It is very easy and quick to create a virtual device using AVD manager.

First, you’ll open your Android Studio.

Then select **Tools -&gt; Android -&gt; AVD Manager.**

Select **Create Virtual Device** option.

Now you’ll configure the device definition and press the **Next** button.

You’ll select the latest system image of Android.

In that window, select **Hardware – GLES 2.0** to enable [hardware acceleration](https://developer.android.com/studio/run/emulator-acceleration) and press the **Next** button and press **finish**.

You’ve **successfully setup a virtual device in Android Studio using AVD manager**.

You can verify the setup by launching the AVD manager.

To launch the Virtual device, Press on the play button.

You’ll see the Android Virtual device is booted and loaded in your Windows machine.

## <span class="ez-toc-section" id="step_7_%e2%80%93_verifying_the_flutter_installation"></span>Step 7 – Verifying the Flutter Installation<span class="ez-toc-section-end"></span>

In this step, you’ll execute the `flutter doctor` command to verify whether the Flutter installation along with Android setup is successful.

Open the Command Prompt and execute the below command.

```
<pre class="wp-block-code">```
flutter doctor -v
```
```

You’ll see the below output.

```
<pre class="wp-block-code">```
Doctor summary (to see all details, run flutter doctor -v):
[√] Flutter (Channel stable, 1.22.6, on Microsoft Windows [Version 6.1.7601],
    locale en-US)
[√] Android toolchain - develop for Android devices (Android SDK version 28.0.3)

[√] Android Studio (version 3.5)
[√] VS Code (version 1.53.2)
[√] Connected device (1 available)

• No issues found!
```
```

You’ll see **No issues found**, this verifies that the Flutter Installation and setup is successful.

**Note:** If you found issue in Connected Device, ensure your Android virtual Device is running. If not, you’ll open your Android Studio and go to **Tools -&gt; Android -&gt; AVD Manager**, and **press the run icon** in the Virtual Device list.

In the next step, you’ll create a default Flutter app and view it in your Android virtual Device.

## <span class="ez-toc-section" id="step_8_%e2%80%93_running_a_default_flutter_app"></span>Step 8 – Running a Default Flutter App<span class="ez-toc-section-end"></span>

In this step, you’ll put to test everything you’ve done so far. You’ll create a new Flutter application and view it in your Android Virtual Device. You’ll do all of mentioned without writing a single line of code.

Open command prompt and **navigate to the folder** where you would like to create your Flutter Application.

For Example, to create your Flutter application in the location `D:\Projects\Flutter`, execute the below commands.

Navigate to the Local Disk (**D:**)using the below command

```
<pre class="wp-block-code">```
D:
```
```

Create a new folder named Projects using the below command.

```
<pre class="wp-block-code">```
mkdir Projects
```
```

Move to `Projects `directory using the below command.

```
<pre class="wp-block-code">```
cd Projects
```
```

Create a new Folder named Flutter, using the below command.

```
<pre class="wp-block-code">```
mkdir Flutter
```
```

Navingate to the newly created `Flutter` folder, using the below command.

```
<pre class="wp-block-code">```
cd Flutter
```
```

Now execute the below command to create the flutter application in the desired directory.

```
<pre class="wp-block-code">```
flutter create app_name
```
```

You’ll see the below output.

```
<pre class="wp-block-code">```
Creating project app_name...
  app_name\.gitignore (created)
  app_name\.idea\libraries\Dart_SDK.xml (created)
  app_name\.idea\libraries\KotlinJavaRuntime.xml (created)
  app_name\.idea\modules.xml (created)
  app_name\.idea\runConfigurations\main_dart.xml (created)
  app_name\.idea\workspace.xml (created)
  app_name\.metadata (created)
  app_name\android\app\build.gradle (created)
  app_name\android\app\src\main\kotlin\com\example\app_name\MainActivity.kt
  (created)
  app_name\android\build.gradle (created)
  app_name\android\app_name_android.iml (created)
  app_name\android\.gitignore (created)
  app_name\android\app\src\debug\AndroidManifest.xml (created)
  app_name\android\app\src\main\AndroidManifest.xml (created)
  app_name\android\app\src\main\res\drawable\launch_background.xml (created)
  app_name\android\app\src\main\res\mipmap-hdpi\ic_launcher.png (created)
  app_name\android\app\src\main\res\mipmap-mdpi\ic_launcher.png (created)
  app_name\android\app\src\main\res\mipmap-xhdpi\ic_launcher.png (created)
  app_name\android\app\src\main\res\mipmap-xxhdpi\ic_launcher.png (created)
  app_name\android\app\src\main\res\mipmap-xxxhdpi\ic_launcher.png (created)
  app_name\android\app\src\main\res\values\styles.xml (created)
  app_name\android\app\src\profile\AndroidManifest.xml (created)
  app_name\android\gradle\wrapper\gradle-wrapper.properties (created)
  app_name\android\gradle.properties (created)
  app_name\android\settings.gradle (created)
  app_name\ios\Runner\AppDelegate.swift (created)
  app_name\ios\Runner\Runner-Bridging-Header.h (created)
  app_name\ios\Runner.xcodeproj\project.pbxproj (created)
  app_name\ios\Runner.xcodeproj\xcshareddata\xcschemes\Runner.xcscheme (created)

  app_name\ios\.gitignore (created)
  app_name\ios\Flutter\AppFrameworkInfo.plist (created)
  app_name\ios\Flutter\Debug.xcconfig (created)
  app_name\ios\Flutter\Release.xcconfig (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Contents.json (created)

  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-1024x1024@1x.p

  ng (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-20x20@1x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-20x20@2x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-20x20@3x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-29x29@1x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-29x29@2x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-29x29@3x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-40x40@1x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-40x40@2x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-40x40@3x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-60x60@2x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-60x60@3x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-76x76@1x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-76x76@2x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\AppIcon.appiconset\Icon-App-83.5x83.5@2x.p

  ng (created)
  app_name\ios\Runner\Assets.xcassets\LaunchImage.imageset\Contents.json
  (created)
  app_name\ios\Runner\Assets.xcassets\LaunchImage.imageset\LaunchImage.png
  (created)
  app_name\ios\Runner\Assets.xcassets\LaunchImage.imageset\LaunchImage@2x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\LaunchImage.imageset\LaunchImage@3x.png
  (created)
  app_name\ios\Runner\Assets.xcassets\LaunchImage.imageset\README.md (created)
  app_name\ios\Runner\Base.lproj\LaunchScreen.storyboard (created)
  app_name\ios\Runner\Base.lproj\Main.storyboard (created)
  app_name\ios\Runner\Info.plist (created)
  app_name\ios\Runner.xcodeproj\project.xcworkspace\contents.xcworkspacedata
  (created)
  app_name\ios\Runner.xcodeproj\project.xcworkspace\xcshareddata\IDEWorkspaceChe

  cks.plist (created)
  app_name\ios\Runner.xcodeproj\project.xcworkspace\xcshareddata\WorkspaceSettin

  gs.xcsettings (created)
  app_name\ios\Runner.xcworkspace\contents.xcworkspacedata (created)
  app_name\ios\Runner.xcworkspace\xcshareddata\IDEWorkspaceChecks.plist
  (created)
  app_name\ios\Runner.xcworkspace\xcshareddata\WorkspaceSettings.xcsettings
  (created)
  app_name\lib\main.dart (created)
  app_name\app_name.iml (created)
  app_name\pubspec.yaml (created)
  app_name\README.md (created)
  app_name\test\widget_test.dart (created)
Running "flutter pub get" in app_name...                            5.9s
Wrote 71 files.

All done!
[√] Flutter: is fully installed. (Channel stable, 1.22.6, on Microsoft Windows
    [Version 6.1.7601], locale en-US)
[√] Android toolchain - develop for Android devices: is fully installed.
    (Android SDK version 28.0.3)
[√] Android Studio: is fully installed. (version 3.5)
[√] VS Code: is fully installed. (version 1.53.2)
[√] Connected device: is fully installed. (1 available)

In order to run your application, type:

  $ cd app_name
  $ flutter run

Your application code is in app_name\lib\main.dart.
```
```

You’ve successfully created your first Flutter application.

Navigate to the folder containing newly created Flutter application.

```
<pre class="wp-block-code">```
cd app_name
```
```

Finally, you can run your Flutter application using the below command.

```
<pre class="wp-block-code">```
flutter run
```
```

You can see the Flutter application is launched in your Android Virtual Device.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this tutorial, you’ve installed Flutter, setup Android in Flutter, created a default Flutter app and launched it in your Android Device. Flutter is one of the fast emerging technologies in Software Development.

As a next step, you can create your own Flutter applications for Android.