
# 100 Q\&A: Android Media in Mobile Application Development

- Android media capabilities
- Handling media files (audio, video, images)
- Media APIs
- Media storage, media playback, capture, and sharing
- Device compatibility for media features
- Multimedia in the Android project structure and resources

---

## **1. What types of media are supported by Android out of the box?**

- **A:** Android supports images (PNG, JPG, GIF), audio (MP3, AAC, AMR), and video (MPEG-4, H.264) formats.


## **2. Where should you store audio or video files for direct access as app resources?**

- **A:** In the `res/raw/` directory, so you can access them via resource IDs.


## **3. Where should you store media files you want to access as plain files (file streams)?**

- **A:** In the `assets/` directory.


## **4. What is the difference between the `res/raw/` and `assets/` directories?**

- **A:** Files in `raw/` are accessed via resource ID (R.raw.filename) and must have valid resource names. Files in `assets/` can have any name and are accessed using an AssetManager.


## **5. Which XML resource type is used for vector images?**

- **A:** Drawable resources, especially with `vector` drawables (SVG-like XML files in `res/drawable/`).


## **6. How can you display an image in an Android Activity?**

- **A:** Use an `ImageView` widget and set its source to a drawable or bitmap.


## **7. Which widget is commonly used for image display in layouts?**

- **A:** `ImageView`


## **8. How do you play audio from the `raw/` resource folder?**

- **A:** Use the `MediaPlayer` class:

```java
MediaPlayer mp = MediaPlayer.create(context, R.raw.soundfile);
mp.start();
```


## **9. What Android class do you use for video playback in Activities?**

- **A:** `VideoView`


## **10. How do you play a video stored in resources with `VideoView`?**

- **A:** Set the URI with `setVideoURI(Uri)` and call `start()` on the `VideoView`.


## **11. What is the role of `MediaStore` in Android?**

- **A:** It provides a unified interface to access and organize media files (audio, video, images) stored on the device.


## **12. Which permission is required to access external storage for media?**

- **A:** `READ_EXTERNAL_STORAGE` (and `WRITE_EXTERNAL_STORAGE` if writing in legacy devices).


## **13. What is the recommended way to handle media permissions in Android 6.0+?**

- **A:** Request permissions at runtime using the Android permission model.


## **14. Which Android API is used to capture a photo with the device camera?**

- **A:** Use `Intent(MediaStore.ACTION_IMAGE_CAPTURE)` to launch the camera for image capture.


## **15. How can your app receive the captured image from the camera Intent?**

- **A:** Use `onActivityResult()` with the photo returned as a Bitmap or URI.


## **16. How do you record audio from the microphone in Android?**

- **A:** Use the `MediaRecorder` class and request `RECORD_AUDIO` permission.


## **17. What is the API for playing audio streams (online radio or music)?**

- **A:** `MediaPlayer` can play streams by setting a streaming URL as the data source.


## **18. Name two libraries often used for image loading and caching.**

- **A:** Glide, Picasso.


## **19. What is the `ContentResolver`'s role in media?**

- **A:** It provides access to media content via URIs, enabling CRUD operations on media files.


## **20. How do you share an image from your app to other apps?**

- **A:** Use an `Intent` with `ACTION_SEND` and set the MIME type and Uri of the image.

---

### **Device Compatibility \& Media**

## **21. How can you declare that your app requires a camera?**

- **A:** In `AndroidManifest.xml`,

```xml
&lt;uses-feature android:name="android.hardware.camera" android:required="true"/&gt;
```


## **22. How do you check if the device supports video recording?**

- **A:** Use `getPackageManager().hasSystemFeature(PackageManager.FEATURE_CAMERA_ANY)` and check camera capabilities.


## **23. What happens if you declare a required hardware feature (e.g., camera) in your manifest?**

- **A:** The Play Store blocks installation on devices lacking that feature.


## **24. How can you make a media feature optional for your app?**

- **A:** Set `android:required="false"` in the `&lt;uses-feature&gt;` tag and check for hardware support at runtime.

---

### **Media in Project Structure**

## **25. Where do you put an app's launcher icon(s)?**

- **A:** `res/mipmap-*/` directories.


## **26. Where are layout files for media UIs stored?**

- **A:** In `res/layout/` as XML files.


## **27. How do you reference an audio file in `res/raw` from Java code?**

- **A:** Use `R.raw.filename` (without file extension).


## **28. How do you include external media libraries in an Android project?**

- **A:** Add them as dependencies in `build.gradle`, e.g.,
`implementation 'com.github.bumptech.glide:glide:4.14.2'`


## **29. What file formats are recommended for storing sound effects?**

- **A:** Short effects: OGG or MP3 in `res/raw`.


## **30. What about storing large media files in an app?**

- **A:** Store large files in `assets/` or download on demand; APK size is limited.

---

### **Practical Media APIs \& Methods**

## **31. How do you trigger the device’s default image picker from your app?**

- **A:** Use an Intent with `ACTION_PICK` and the Images Media URI from `MediaStore`.


## **32. How do you select an image from the gallery?**

- **A:**

```java
Intent intent = new Intent(Intent.ACTION_PICK, MediaStore.Images.Media.EXTERNAL_CONTENT_URI);
startActivityForResult(intent, PICK_IMAGE);
```


## **33. How do you display a video in a UI layout?**

- **A:** Use `VideoView` and place it in XML layout.


## **34. How can you start background music playback in an app?**

- **A:** Use `MediaPlayer` in a `Service` for background playback.


## **35. What library supports advanced video playback, including streaming and adaptive bitrate?**

- **A:** ExoPlayer.


## **36. How do you create a SoundPool for short, low-latency sound effects?**

- **A:**

```java
SoundPool soundPool = new SoundPool.Builder().setMaxStreams(2).build();
int soundId = soundPool.load(context, R.raw.sound, 1);
soundPool.play(soundId, 1, 1, 1, 0, 1);
```


## **37. How do you check if an image is too large for device memory before loading?**

- **A:** Use BitmapFactory.Options to check image dimensions before loading.


## **38. How do you downscale an image before displaying?**

- **A:** Use `BitmapFactory.Options.inSampleSize` when decoding.


## **39. What is the advantage of using Glide or Picasso for image loading?**

- **A:** Automatic caching, async loading, and memory management.


## **40. How do you capture a video with the camera app?**

- **A:** Use Intent:
`Intent(MediaStore.ACTION_VIDEO_CAPTURE)`

---

### **Permissions \& Security**

## **41. Which permission is required to record video?**

- **A:** `CAMERA` and optionally `RECORD_AUDIO` for audio in video.


## **42. Which permission is needed to play audio/media from the internet?**

- **A:** No special permission for streaming, but need INTERNET if accessing over network.


## **43. What’s new with storage permissions starting from Android 10?**

- **A:** Scoped storage: apps cannot freely access all files. Use MediaStore and Storage Access Framework.


## **44. How can you request permission for audio or video recording at runtime?**

- **A:** Use `ActivityCompat.requestPermissions()` and handle the callback.


## **45. Why should you not include copyrighted media in your APK?**

- **A:** Legal issues-use Creative Commons or own media only.

---

### **Media Playback and Capture**

## **46. What is the main class for audio playback?**

- **A:** `MediaPlayer`


## **47. How do you pause/resume playback in MediaPlayer?**

- **A:** `mediaPlayer.pause();` and `mediaPlayer.start();`


## **48. What is the main class for playing short sounds?**

- **A:** `SoundPool`


## **49. What Android component is best for voice recording?**

- **A:** `MediaRecorder` with setAudioSource.


## **50. How do you capture a screenshot of the current Activity?**

- **A:** Use the view’s drawing cache, or `PixelCopy` on API 26+.


## **51. How do you get a thumbnail of a video file?**

- **A:** Use `ThumbnailUtils.createVideoThumbnail()`.


## **52. How do you detect if a device supports a specific media codec?**

- **A:** Use `MediaCodecList` and `MediaCodecInfo` classes.


## **53. What should you use for audio focus (pausing/resuming playback on calls)?**

- **A:** `AudioManager` requests and listeners.


## **54. How do you access media files from the SD card?**

- **A:** Use `MediaStore` URIs and request permissions.


## **55. What is the best way to play online video streams (e.g., YouTube)?**

- **A:** Use `YouTubePlayer` API, or for general streaming, use ExoPlayer.

---

### **Image, Audio, Video Resource Handling**

## **56. How do you support alternative images for different screen densities?**

- **A:** Provide `drawable-mdpi`, `drawable-hdpi`, etc. versions of your images.


## **57. What are Nine-patch images?**

- **A:** Special PNGs that can stretch to accommodate variable content.


## **58. How do you create an animation from multiple images?**

- **A:** Use `AnimationDrawable`.


## **59. How do you resize an image in code before saving it?**

- **A:** Use `Bitmap.createScaledBitmap()`.


## **60. How can you edit or manipulate images in Android?**

- **A:** Use the `Bitmap` API, `Canvas`, and `Paint`.

---

### **Media Sharing and Broadcast**

## **61. How do you send a video to another app?**

- **A:** Use an `Intent` with `ACTION_SEND` and set type to `"video/*"`.


## **62. How do you pick an audio file from device storage?**

- **A:** Use `Intent.ACTION_PICK` with MediaStore.Audio.Media.EXTERNAL_CONTENT_URI.


## **63. How do you detect new media (image, audio, video) on the device?**

- **A:** By monitoring MediaStore for new entries or file observers.


## **64. How do you notify the media scanner to scan a new file?**

- **A:** Call `MediaScannerConnection.scanFile()`.

---

### **Specialized Media Use Cases**

## **65. What class is used for camera APIs in Android 5+ (Lollipop and above)?**

- **A:** `android.hardware.camera2`


## **66. How do you implement a custom camera UI?**

- **A:** Use the Camera or Camera2 API to access the hardware and handle preview, capture, and save yourself.


## **67. What is the recommended way to capture high-resolution photos?**

- **A:** Use Camera2 API with the largest supported resolution.


## **68. How do you play a GIF image?**

- **A:** Use a library such as Glide with GIF support, or a custom drawable.


## **69. How do you trim a video in Android?**

- **A:** Use `MediaExtractor`, `MediaMuxer`, or third-party libraries.


## **70. How do you capture slow-motion video?**

- **A:** Use Camera2 API and supported high frame rate video profiles.

---

### **Debugging \& Performance**

## **71. How do you detect memory leaks when handling media?**

- **A:** Use Android Profiler and LeakCanary.


## **72. Why is it a bad idea to load large bitmaps directly into memory?**

- **A:** It can cause `OutOfMemoryError` and crash the app.


## **73. How can you reduce APK size with media files?**

- **A:** Compress media, use appropriate resolution, and host large files remotely if possible.


## **74. What do you use to optimize audio latency for games?**

- **A:** `AudioTrack` for low-latency audio playback.


## **75. How do you release resources after playing media?**

- **A:** Call `release()` on `MediaPlayer`, `MediaRecorder`, `SoundPool`, etc.

---

### **Media and UI**

## **76. How do you implement a photo gallery UI?**

- **A:** Use `RecyclerView` or `GridView` with an image loader for thumbnails.


## **77. How do you animate an image (e.g., fade in)?**

- **A:** Use Android `Animation` or `Animator` APIs such as `ObjectAnimator`.


## **78. How do you implement an audio visualizer?**

- **A:** Use the `Visualizer` API with audio session ID.


## **79. How can you handle video orientation?**

- **A:** Use metadata from `MediaMetadataRetriever` and adjust the `VideoView` or handle in code.


## **80. How do you overlay text on an image?**

- **A:** Draw with `Canvas` and `Paint` over a `Bitmap`.

---

### **Testing and Edge Cases**

## **81. How do you test media playback in your app?**

- **A:** Use emulators and real devices, covering various formats and error cases.


## **82. What happens if a media file is missing or corrupt?**

- **A:** `MediaPlayer` or `BitmapFactory` throws an error or returns null; always check and handle errors.


## **83. How do you handle media playback interruptions, e.g., phone call?**

- **A:** Listen to `AudioManager` for audio focus changes, pause/resume audio accordingly.


## **84. How can you run media tasks in the background?**

- **A:** Use a `Service` (or `ForegroundService` for ongoing notifications).


## **85. How do you prevent media from playing after the Activity is destroyed?**

- **A:** Release and clean up the media player in `onPause()` or `onDestroy()`.

---

### **Media and Android Manifest**

## **86. Where do you declare permissions for media features?**

- **A:** In `AndroidManifest.xml`, e.g.,
`&lt;uses-permission android:name="android.permission.RECORD_AUDIO"/&gt;`


## **87. How can you restrict your app to devices with a front camera?**

- **A:**

```xml
&lt;uses-feature android:name="android.hardware.camera.front" android:required="true"/&gt;
```


## **88. How do you specify support for HD video playback?**

- **A:** No manifest tag-detect at runtime, or mention in Play Store description.


## **89. How do you define your app can handle sharing images or videos from other apps?**

- **A:** Use an `&lt;intent-filter&gt;` for `"android.intent.action.SEND"` with appropriate MIME types.

---

### **Advanced / Miscellaneous**

## **90. What is ExoPlayer?**

- **A:** An open-source, extensible media player for Android by Google, supporting advanced streaming and DRM features.


## **91. How do you create a playlist of songs in Android?**

- **A:** Use a list of URIs/files and control `MediaPlayer` or ExoPlayer accordingly.


## **92. How do you update the lock screen with current playing song info and album art?**

- **A:** Use a MediaSession and Notification with media style.


## **93. How do you implement background video playback?**

- **A:** Use a foreground Service and handle audio/video focus properly.


## **94. How do you record and save screen video in Android?**

- **A:** Use MediaProjection API (from Android 5.0+).


## **95. How can you take a picture programmatically without user interface?**

- **A:** Use Camera2 API in a service.


## **96. How do you support media features on WearOS or Android TV?**

- **A:** Use appropriate UI components and check device features; use Leanback for TV, specific media APIs for wearables.


## **97. How do you test how your app handles lack of certain media features (e.g., no camera)?**

- **A:** Use emulators with configured device features disabled.


## **98. What is the recommended way to download large media files?**

- **A:** Use `DownloadManager` and store to app-specific storage.


## **99. How do you ensure media is not accessible by other apps (private)?**

- **A:** Store files in app's internal storage (`getFilesDir()` or `getCacheDir()`).


## **100. If your app edits photos and videos, what’s a good export folder?**

- **A:** Use `getExternalFilesDir(Environment.DIRECTORY_PICTURES)` or `DIRECTORY_MOVIES` for saved media.

---
