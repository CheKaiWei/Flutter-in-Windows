# Flutter-in-Windows
Run fluttre in Windows

## Install Flutter:
### System requirements
To install and run Flutter, your development environment must meet these minimum requirements:

- Operating Systems: Windows 7 SP1 or later (64-bit)
- Disk Space: 400 MB (does not include disk space for IDE/tools).
- Tools: Flutter depends on these tools being available in your environment.
    - Windows PowerShell 5.0 or newer (this is pre-installed with Windows 10)
    - Git for Windows 2.x, with the Use Git from the Windows Command Prompt option.

### Get the Flutter SDK
Download the following installation bundle to get the latest stable release of the [Flutter SDK](https://flutter.dev/docs/get-started/install/windows)
### Update your path
Add environment variables
### Run flutter doctor
From a console window which has the Flutter directory in the path (see above), run the following command to see if there are any platform dependencies you need to complete the setup

```bash
flutter doctor
```

```bash
Doctor summary (to see all details, run flutter doctor -v):
[√] Flutter (Channel stable, v1.5.4-hotfix.2, on Microsoft Windows [Version 6.1.7601], locale zh-CN)
[!] Android toolchain - develop for Android devices
    X Unable to locate Android SDK.
      Install Android Studio from: https://developer.android.com/studio/index.html
      On first launch it will assist you in installing the Android SDK components.
      (or visit https://flutter.dev/setup/#android-setup for detailed instructions).
      If the Android SDK has been installed to a custom location, set ANDROID_HOME to that location.
      You may also want to add it to your PATH environment variable.

    X No valid Android SDK platforms found in C:\Users\108\AppData\Local\Android\sdk\platforms.
      Directory was empty.
[!] Android Studio (version 3.4)
    X Flutter plugin not installed; this adds Flutter specific functionality.
    X Dart plugin not installed; this adds Dart specific functionality.
[!] Connected device
    ! No devices available

! Doctor found issues in 3 categories.
```
This command checks your environment and displays a report of the status of your Flutter installation. Check the output carefully for other software you may need to install or further tasks to perform 

## Android setup
Flutter relies on a full installation of Android Studio to supply its Android platform dependencies. However, you can write your Flutter apps in a number of editors

### Install Android Studio
1. Download and install [Android Studio](https://developer.android.com/studio)
2. Start Android Studio, and go through the ‘Android Studio Setup Wizard’. This installs the latest Android SDK, Android SDK Platform-Tools, and Android SDK Build-Tools, which are required by Flutter when developing for Android.


### Set up your Android device
To prepare to run and test your Flutter app on an Android device, you’ll need an Android device running Android 4.1 (API level 16) or higher.

1. Enable Developer options and USB debugging on your device.[小米/MIUI如何进入开发者选项模式并打开USB调试](https://jingyan.baidu.com/article/8275fc864fe33c46a03cf699.html)
2. Install the [Google USB Driver](https://developer.android.com/studio/run/win-usb), and [update your device](https://developer.android.com/studio/run/oem-usb.html#InstallingDriver)
3. Using a USB cable, plug your phone into your computer. If prompted on your device, authorize your computer to access your device.
4. In the terminal, run the flutter devices command to verify that Flutter recognizes your connected Android device.

```bash
C:\Users\108>flutter devices
1 connected device:

MI 6 ? d235d86b ? android-arm64 ? Android 8.0.0 (API 26)
```


### Set up the Android emulator
To prepare to run and test your Flutter app on the Android emulator, follow these steps:
1. Enable VM acceleration on your machine, which use to simulate your mobolile phone.
    [Configure hardware acceleration for the Android Emulator](https://developer.android.com/studio/run/emulator-acceleration)
    1. Open the AVD Manager(Click AVD Manager AVD Manager in the toolbar).
    ![python]({{"image/Flutter/1-avd_manager.png" | absolute_url}})
    2. [Create a new AVD or edit an existing AVD.](https://developer.android.com/studio/run/managing-avds#createavd)
    3. On the Verify Configuration page, find the Emulated Performance section.
    4. Select a value for the Graphics: option.
    5. Click Finish.

2. Launch Android Studio > Tools > Android > AVD Manager and select Create Virtual Device. (The Android submenu is only present when inside an Android project.)
3. Choose a device definition and select Next.
4. Select one or more system images for the Android versions you want to emulate, and select Next. An x86 or x86_64 image is recommended.
5. Under Emulated Performance, select Hardware - GLES 2.0 to enable hardware acceleration.
6. Verify the AVD configuration is correct, and select Finish.
7. In Android Virtual Device Manager, click Run in the toolbar. The emulator starts up and displays the default canvas for your selected OS version and device.

## Problems
### 1. [unable to find git in your path](https://github.com/flutter/flutter/issues/16591)

### 2. Unable to access Android SDK add-on list
Connect your VPN and just download it!

### 3. Without so much space for install Android SDK
I need to wait for a bigger space for install.

## Source
1. [Flutter Offical Document](https://flutter.dev/docs/get-started/install/windows)