# Usage

## Initializing
Call **Everyplay.initEveryplay(IEveryplayListener listener, Activity rootActivity)** when you wish to initialize Everyplay.

## Recording
* Call **Everyplay.startRecording()** to start recording.
* Call **Everyplay.stopRecording()** to stop recording.
* Call **Everyplay.pauseRecording()** to pause recording.
* Call **Everyplay.resumeRecording()** to resume recording after pause.
---
* Call **Everyplay.isRecording()** to check whether recording is active.
* Call **Everyplay.isPaused()** to check whether recording is currently paused.
* Call **Everyplay.isSupported()** to check whether Everyplay is supported on device.
* Call **Everyplay.isRecordingSupported()** to check whether Everyplay recording is supported on device.

## Additional functionality
* Call **Everyplay.takeThumbnail();** to take a thumbnail of the recording. This will cause IEveryplayListener.onEveryplayThumbnailReadyAtTextureId(int textureId, int portraitMode); to fire after the thumbnail has been prepared. You must set a target texture for the thumbnail using Everyplay.setThumbnailTargetTextureId(int) before using this.
* Call **Everyplay.setThumbnailTargetTextureId(int)** to set a target texture for the thumbnail. Once a thumbnail is taken, it will be applied to this target texture.
* Call **Everyplay.setMotionFactor(int)** to affect the quality of the recording. The function clamps the value given between 1 and 4. Default quality is 2. Higher value produces better quality video at cost of file size.
* Call **Everyplay.setTargetFPS(int)** to affect the frame rate the video is being captured. Higher capture frame rate produces smoother video at cost of file size.
* Call **Everyplay.setLowMemoryDevice(int)** with value 1 to lower the memory cost of the plugin. This will increase CPU usage slightly.
* Call **Everyplay.setAudioResamplerQuality(int)** to set the audio resampler to compatibility mode. The function clamps the value given between 0 and 1. Default setting is 0. Set this to 1 if you hear snapping, popping or crackling in your recorded video.
* Call **Everyplay.setMaxRecordingMinutesLength(int)** to set maximum length for a recording. The length is counted from the end of the recording. If you set this to 1 and record for 2 minutes, the recording will contain the LAST 1 minute. 
* Call **Everyplay.setMaxRecordingSecondsLength(int)** to set maximum length for a recording. The length is counted from the end of the recording. If you set this to 15 and record for 30 seconds, the recording will contain the LAST 15 seconds.

## Accessing video
* Call **Everyplay.playLastRecording();** to play back last recording and allow user to trim it.
* Call **Everyplay.showEveryplaySharingModal();** to share the video using the device's share modal.
* Call **Everyplay.getFilePath();** to get the path to the video file. This will cause IEveryplayListener.onFileReady(String filepath) to fire after the video has been prepared. 

## Events
* **IEveryplayListener.onEveryplayShown()** - This event will fire when the Everyplay video player has been opened.
* **IEveryplayListener.onEveryplayHidden()** - This event will fire when the Everyplay video player has been closed.
* **IEveryplayListener.onEveryplayReadyForRecording(int enabled)** - This event tells whether the device is currently ready to start a recording session. This event will fire multiple times during the lifetime of the app.
    * If the parameter is non-zero, the device is ready to start a recording. Otherwise it is not.
* **IEveryplayListener.onEveryplayRecordingStarted()** - This event will fire when a recording has been started.
* **IEveryplayListener.onEveryplayRecordingStopped()** - This event will fire when a recording has been stopped.
* **IEveryplayListener.onFileReady(String filepath)** - This event will fire when Everyplay.GetFilepath() has been called and the video has successfully been prepared.
    * The parameter contains the path to the recorded file.
* **IEveryplayListener.onEveryplayThumbnailReadyAtTextureId(int textureId, int portraitMode)** - This will fire when Everyplay.TakeThumbnail() has been called and the thumbnail has successfully been prepared.
    * First parameter identifies the texture, second parameter indicates whether the thumbnail was taken in portrait orientation.
