Welcome to Everyplay. To get started, make sure you have an account registered, and that you have a unique client ID
for your game. You can get these along with the latest integration instructions at https://developers.everyplay.com/

You can always download the latest SDK upgrades directly from https://github.com/everyplay/everyplay-android-sdk

Looking for iOS version? See https://github.com/everyplay/everyplay-ios-sdk
<br />
Looking for Unity plugin? See https://github.com/everyplay/everyplay-unity-sdk
<br />
Looking for Adobe AIR version? See https://github.com/everyplay/everyplay-air-sdk

Everyplay SDK is licensed under the Apache License, Version 2.0 (http://www.apache.org/licenses/LICENSE-2.0.html) with restrictions. Please see Everyplay Terms of Service at https://everyplay.com/developer-terms-of-service for more information.

For now, each SDK release has an expiration date. After expiring, there's a warning dialog on launch
that recommends to upgrade the SDK. Apps downloaded from the Google Play Store or similar distribution
channels won't have this behaviour.

Current and previous expiration dates:

- 2015-01-31 (releases from 1.1.3 to CURRENT)
- 2014-09-14 (releases from 1.1 to 1.1.2)
- 2014-05-31 (releases from 1.0.5 to 1.0.6)
- 2014-04-30 (releases from 1.0.3 to 1.0.4)
- 2014-03-31 (releases from 1.0 to 1.0.2)

Everyplay SDK/Android - Release Notes
=====================================

### v1.2 - Nov 28th 2014 (build 1200)

- Generic:
    - Generic optimizations against the new Everyplay community

    - New navigation top bar design to give more space while browsing

    - Network access and caching optimizations

    - Internal changes for UI theming support

    - 3rdparty java code is relocated to another package namespace
      to avoid conflicts

    - Performance updates to media merging and trimming

    - Everyplay.setMaxRecordingMinutesLength didn't trim the
      resulting video, fixed

    - Fixed potential crash issue with camera photo picker

    - Upload performance improvements

    - Everyplay.initEveryplay now retains IEveryplayListener

    - Try-catch blocks for rare exceptions added

### v1.1.6 - Nov 10th 2014 (build 1160)

- Generic:
    - Changes to activity handling in code and on AndroidManifest.xml
      to fix GPU driver issues and potential crashes

    - Improved AAC encoded sound quality

    - Improved Facebook behaviour for the future

### v1.1.5 - Oct 9th 2014 (build 1150)

- Generic:
    - Fixed Facebook sharing to work against Facebook API 2.0
      and later

### v1.1.4 - Oct 1st 2014 (build 1140)

- Generic:
    - Video resolution handling improvements

### v1.1.3 - Aug 27th 2014 (build 1130)

- Generic:
    - First official support for non-Unity game engines. For Android
      example applications, check out:

      https://github.com/Everyplay/everyplay-android-examples

    - Now comes with Adobe AIR support:

      https://github.com/Everyplay/everyplay-air-sdk

    - Some devices and applications had image quality issues/artifacts
      before video encoding step, fixed

    - Starting recording with HUD-less enabled could have caused frame
      glitch once while starting, fixed

    - Fix network retry handling in Everyplay splash screen

    - Analytics improvements

    - Unity plugin relocated to https://github.com/everyplay/everyplay-unity-sdk

### v1.1.2 - June 17th 2014 (build 1120)

- Generic:

    - Fixed recording from not working if changing MSAA anti-aliasing
      state during runtime

    - Fixed a potential Qualcomm specific issue with rendering
      modal share dialog borders

    - Improved upload handling

    - Improved videoplayer thread safety

- Unity plugin:

    - Fixed iOS build error against Unity 4.5.1

    - Fixed a potential exception error with Xcode project editor

    - Updated WWW constructor parameters for Unity 4.5+

### v1.1.1 - May 20th 2014 (build 1110)

- Generic:

    - Workaround for ImgTec PowerVR GPU driver behaviour that
      could cause entire device to freeze after initialization

    - Fix videoplayer seeking from causing a crash on some
      devices with faulty drivers

    - Fix for potential video encoding thread hanging on some
      devices like Samsung Galaxy S3

    - Improved sending onEveryplayRecordingStarted listener events

    - Add onEveryplayAccountDidChange listener event

### v1.1 - May 14th 2014 (build 1100)

- Generic:
    - Everyplay now uses Facebook SDK for improved, seamless Facebook login support.
      If not linked into the project, the old login convention applies

    - The new improved Facebook login shares via Everyplay Facebook application,
      not through your existing Facebook application credentials. For immediate
      use, you might need to send your iOS bundle information or Android key
      hash to get started, please contact support@everyplay.com. We're currently
      working on making this step automated without extra work required on
      developers behalf

    - Generic graphics optimizations and improvements to graphics
      related resource allocating and releasing, which could have
      led to invalid graphics state in earlier releases

    - Improved recording state handling, orientation changing while
      recording etc

    - Worked around OpenGL performance issue that could happen on some devices
      after returning from Everyplay videoplayer activity that's triggered by
      playLastRecording method

    - Fixed a rare exception crash thrown by MediaCodec.dequeueInputBuffer

    - Improved movie merging behaviour and exception handling

    - Don't show 'Launch game' button when the game is already active one

    - Improved onEveryplayReadyForRecording(int enabled) listener events
      to return false for more cases where the recording isn't going to
      be supported

- Unity plugin:
    - Improved Facebook integration, this requires the use of "Facebook for Unity" asset
      available from the Asset Store

    - Lots of internal plugin changes and file location changes for better Unity integration,
      the migration should be seamless without removing previous assets

    - New prefables integration. Instead of dragging a prefab to your first scene
      you may use the Edit / Everyplay Settings menu to enable Everyplay and to
      set your game credentials. This also allows you to temporarily disable
      Everyplay without removing the package

    - Double check that clientId, secret and redirectURI settings have merged into
      the new Edit / Everyplay Settings menu after upgrading

    - Calling Everyplay through the SharedInstance is now deprecated. You may still
      use the old way, but the recommended way is to call Everyplay.methodName

    - Added checkboxes to new Everyplay settings menu for enabling Everyplay per
      platform (iOS/Android)

    - iOS Everyplay.framework and bundle are now directly embedded into the package
      and used as the only option

    - Old test button functionality in Everyplay.prefab has been moved to
      Plugins/Everyplay/Helpers/EveryplayTest.prefab. A new simplified one can
      be enabled through Edit / Everyplay Settings menu

### v1.0.5 - April 7th 2014 (build 1051)

- Generic:
    - Build 1051: Workarounds for Vivante / HiSilicon GPU
      driver behaviour while not recording and early work
      towards supporting it in general

    - Fixed multiple OpenGL graphics state issues that
      were triggered on some devices and use cases

    - Fixed potential frame flickering and jerking issues

    - Fixed thumbnail graphics issues and rare crashes

    - Improved the image quality of downscaled video frame

- Unity plugin:
    - New graphics integration support for iOS

### v1.0.4 - March 10th 2014 (build 1041)

- Generic:
    - Fixed a regression with OpenGL ES1 support

    - UI localization support for Simplified Chinese

    - Workaround for Broadcom VideoCore IV related crash and
      early work towards supporting it in general

### v1.0.3 - March 5th 2014 (build 1030)

- Generic:
    - First bunch of graphics optimization improvements, especially for Qualcomm
      and Mali GPUs. Depending on hardware used, up to 4x framerate improvement
      while recording

    - Generic activity handling improvements

    - There's now a warning dialog if the developer has not configured clientId,
      clientSecret and redirectUri. They're required before entering Everyplay
      related activities

    - Nexus 10 support now enabled from server side remote settings

### v1.0.2 - February 7th 2014 (build 1020)

- Generic:
    - Apps submitted to Play Store didn't remove the sandbox status
      or the ability to upload private videos

    - Fixed some sluggish activity behaviour when swapping activities
      to/from the video player

    - Localization improvements

### v1.0.1 - February 4th 2014 (build 1010)

- Generic:
    - Fixed video trimming feature in release build

### v1.0 - February 3rd 2014 (build 1000)

- Generic:
    - Initial public release with Unity support, others to follow

      For recording support, most devices running Android 4.1 (API level 16)
      or later should work

      For just browsing and using Everyplay social features, a device running
      Android 4.0 (API level 14) or later is required

      It's possible to target an application to run on older versions than 4.0,
      but all Everyplay SDK methods are non-functional

      Due to wide range of driver behaviour, hardware encoders, GPUs and
      Android version differences out there, Everyplay SDK caches device specific
      settings online from a remote server

      Until the settings are successfully received, the recording support is
      automatically disabled. After receiving the server response, the recording
      support is either enabled or continued to be disabled to workaround devices
      known to cause trouble. Next time the application is started, the settings
      are applied from the cache immediately upon startup without requiring network
      access

      It is also the fastest way to react when encountering unknown devices that
      could cause trouble, either by remotely disabling recording support or tuning
      device specific settings, in best case without requiring an SDK/application
      upgrade

- Unity plugin:
    - Unity 4.3 works out of the box with Build & Run

    - Unity 4.2 works as well, but you need to disable Version Control through
      Edit -> Project Settings -> Editor; to make up Android build improvements
      that have only been implemented in 4.3 release or later

    - Unity 4.1 and older releases work through some manual labor:

        - Disable Version Control through Edit -> Project Settings -> Editor or
          be prepared to manually remove all *.meta files from the exported project
          folder

        - Export an Eclipse project

        - Open the exported project. If there's a AndroidManifest.xml parse error,
          you may need to re-save it as UTF-8 (without BOM) in your favorite text
          editor

        - Append the following lines to project.properties:
```
          android.library.reference.1=Plugins/Android/everyplay
          manifestmerger.enabled=true
```

- Known issues:
    - Main focus is on testing the completeness of the SDK, multiple
      performance enhancements are currently in the works

    - Live FaceCam functionality is not yet implemented, Unity FaceCam
      functions currently return false or no-op on Android

    - No FaceCam commentary option in video editor yet
