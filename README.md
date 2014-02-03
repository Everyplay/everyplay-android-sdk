Welcome to Everyplay. To get started, make sure you have an account registered, and that you have a unique client ID
for your game. You can get these along with the latest integration instructions at https://developers.everyplay.com/

You can always download the latest SDK upgrades directly from https://github.com/everyplay/everyplay-android-sdk

Everyplay SDK is licensed under the Apache License, Version 2.0 (http://www.apache.org/licenses/LICENSE-2.0.html)

For now, each SDK release has an expiration date. After expiring, there's a warning dialog on launch
that recommends to upgrade the SDK. Apps downloaded from the Google Play Store or similar distribution
channels won't have this behaviour.

Current and previous expiration dates:

- 2014-03-31 (releases from 1.0 to CURRENT)

Everyplay SDK/Android - Release Notes
=====================================

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
