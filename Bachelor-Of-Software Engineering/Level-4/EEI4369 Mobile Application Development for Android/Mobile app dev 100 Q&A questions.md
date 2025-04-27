# Mobile application Dev 100 Q\&A questions

---

## **Introduction to Android**

1. **Q:** What is Android?
**A:** Android is a mobile operating system developed by Google, based on a modified version of the Linux kernel and other open-source software.
2. **Q:** Who developed Android?
**A:** Android was developed by Google.
3. **Q:** What kernel is Android based on?
**A:** Linux kernel.
4. **Q:** Since when has Android mobile development been Kotlin-first?
**A:** Since Google I/O in 2019.
5. **Q:** What is the official market for third-party Android applications?
**A:** Google Play Store.
6. **Q:** Name two companies that use their own Android distributions apart from Google.
**A:** Amazon and Nokia.
7. **Q:** What programming languages are primarily used for Android app development?
**A:** Java and C++.
8. **Q:** What is the latest Android version as of March 2025?
**A:** Android 16 (API Level 36).
9. **Q:** What is the Android Runtime (ART)?
**A:** A Java application runtime environment that translates application bytecode into processor-specific instructions.
10. **Q:** What was the virtual machine used before ART in Android?
**A:** Dalvik Virtual Machine.

---

## **Android Versions and Devices**

11. **Q:** How were Android versions named before Android 9?
**A:** After desserts.
12. **Q:** List three types of devices that can run Android.
**A:** Smartphones, tablets, TVs.
13. **Q:** What is an STB Box in the context of Android devices?
**A:** Set-top box.
14. **Q:** Name a wearable device that runs Android.
**A:** Smart Watch.
15. **Q:** What is the main function of the Google Play Store?
**A:** To provide a platform for downloading and updating Android apps.

---

## **Android Architecture**

16. **Q:** What are the four main layers of Android architecture?
**A:** Applications, Application Framework, Libraries/Android Runtime, Linux Kernel.
17. **Q:** What is the purpose of the Hardware Abstraction Layer (HAL)?
**A:** To provide a standard interface for hardware vendors, allowing Android to be hardware-agnostic.
18. **Q:** What are system services in Android?
**A:** Modular components like system_server and SurfaceFlinger that provide core OS functionality.
19. **Q:** What is the Android framework?
**A:** A set of Java classes and interfaces upon which Android apps are built.
20. **Q:** What is a privileged app in Android?
**A:** An app that uses both Android and system APIs and must be preinstalled as a privileged app.
21. **Q:** What is a device manufacturer app?
**A:** An app that can access Android framework implementation directly and is preinstalled on the device.
22. **Q:** What is the role of native daemons in Android?
**A:** They interact directly with the kernel or other interfaces, independent of the userspace-based HAL.
23. **Q:** Name two native libraries in Android.
**A:** libc, liblog.
24. **Q:** What is the function of the kernel in Android?
**A:** It communicates with the underlying hardware on a device.

---

## **Android Application Building Blocks**

25. **Q:** What is an Activity in Android?
**A:** A component that has a lifecycle and represents a single screen with a user interface.
26. **Q:** What is a Fragment?
**A:** A part of an activity that represents multiple screens inside one activity.
27. **Q:** What is a View in Android?
**A:** An object that knows how to draw itself to the screen.
28. **Q:** What is an Intent?
**A:** A message object representing an intention to do something.
29. **Q:** What is an Intent Receiver?
**A:** A component that executes in response to an external event.
30. **Q:** What is a Notification in Android?
**A:** A message to inform users of events across the platform.
31. **Q:** What is a Service in Android?
**A:** A component that runs in the background without a user interface.
32. **Q:** What is a Content Provider?
**A:** A component that allows an application's data to be shared with other applications.

---

## **Android Application Lifecycle**

33. **Q:** Name the three main states of an Android activity lifecycle.
**A:** Active, Paused, Stopped.
34. **Q:** What method is called when an activity is first created?
**A:** onCreate().
35. **Q:** What method is called when an activity becomes visible to the user?
**A:** onStart().
36. **Q:** What method is called when an activity is no longer visible?
**A:** onStop().
37. **Q:** What method is called before an activity is destroyed?
**A:** onDestroy().

---

## **Android Development Environment**

38. **Q:** What is the official IDE for Android development?
**A:** Android Studio.
39. **Q:** Android Studio is based on which IDE?
**A:** JetBrains IntelliJ IDEA.
40. **Q:** What is Gradle used for in Android development?
**A:** It is the build automation system for Android projects.
41. **Q:** What does the .idea directory contain?
**A:** IntelliJ IDEA settings.
42. **Q:** What file specifies untracked files for Git in an Android project?
**A:** .gitignore.
43. **Q:** What is the function of the AndroidManifest.xml file?
**A:** It describes the nature of the application and its components.
44. **Q:** Where are application resources like images and layouts stored?
**A:** In the main/res/ directory.
45. **Q:** What is the purpose of the build.gradle file?
**A:** To customize build settings for the application.
46. **Q:** What is the function of the local.properties file?
**A:** To store computer-specific properties, like the SDK path.
47. **Q:** What is the main/java/ directory used for?
**A:** Storing Java source code for app activities.
48. **Q:** What is the main/assets/ directory used for?
**A:** Storing raw asset files compiled into the APK as-is.
49. **Q:** What is the main/res/layout/ directory used for?
**A:** XML files for screen layouts.
50. **Q:** What is the main/res/values/ directory used for?
**A:** XML files that define resources by XML element type.

---

## **Mobile Hardware**

51. **Q:** What is a System on a Chip (SoC)?
**A:** An integrated circuit that combines all components of a computer or other system into a single chip.
52. **Q:** Name the three primary components of a smartphone SoC.
**A:** Application processor, baseband processor, peripheral devices.
53. **Q:** What are common smartphone connectivity features?
**A:** WiFi, Bluetooth, 4G/5G connectivity.
54. **Q:** What is the function of the baseband processor?
**A:** Handles radio transmission and reception of audio, video, and data.
55. **Q:** What is the function of the application processor?
**A:** Executes user application software and OS instructions.

---

## **Android Display**

56. **Q:** What does display resolution refer to?
**A:** The number of pixels present in a display or screen.
57. **Q:** What is the resolution of an HD display?
**A:** 720 x 1280 pixels.
58. **Q:** What is the resolution of a FullHD (FHD) display?
**A:** 1080 x 1920 pixels.
59. **Q:** What is the resolution of a QuadHD (QHD) display?
**A:** 1440 x 2560 pixels.
60. **Q:** What is the effect of higher display resolution on battery life?
**A:** Higher resolution consumes more battery.

---

## **Smartphone Battery**

61. **Q:** What is the typical battery capacity for modern smartphones?
**A:** 3500-4000 mAh.
62. **Q:** How long does a 1500-2000 mAh battery typically last?
**A:** About 0.5 day.
63. **Q:** What Android OS feature helps manage battery life?
**A:** Power saving mode and deep sleeping unused apps.

---

## **Smartphone Camera**

64. **Q:** What does camera resolution mean?
**A:** The number of pixels the camera sensor can capture.
65. **Q:** What is the typical resolution for high-end smartphone cameras?
**A:** Up to 100 MP.
66. **Q:** What is the function of the lens in a smartphone camera?
**A:** To focus light and produce sharp images.
67. **Q:** What is the advantage of AI in smartphone cameras?
**A:** Enhances photo quality by adjusting settings automatically.
68. **Q:** What is the maximum video recording resolution in modern smartphones?
**A:** Up to 4K.
69. **Q:** What is the function of the front camera?
**A:** Taking selfies and enabling face unlock.

---

## **Smartphone RAM**

70. **Q:** What is RAM used for in smartphones?
**A:** To store frequently used instructions for quick access.
71. **Q:** How much RAM is ideal for basic apps like WhatsApp and YouTube?
**A:** 1-3 GB.
72. **Q:** How much RAM is recommended for smooth gaming and multitasking?
**A:** 6 GB or more.

---

## **Smartphone SoC Components**

73. **Q:** What does CPU stand for?
**A:** Central Processing Unit.
74. **Q:** What is the role of the GPU in a smartphone?
**A:** Handles graphics rendering and multimedia support.
75. **Q:** What is the function of the Northbridge in an SoC?
**A:** Interface between CPU and the rest of the chipset.
76. **Q:** What does the Southbridge control?
**A:** Input and output functions, including audio and USB.

---

## **Smartphone GPS**

77. **Q:** What does GPS stand for?
**A:** Global Positioning System.
78. **Q:** Name a use case for GPS in mobile apps.
**A:** Navigation and location-based services.
79. **Q:** What is geofencing?
**A:** Creating virtual boundaries for location-based triggers.

---

## **Smartphone Sensors**

80. **Q:** What is a sensor in a smartphone?
**A:** A device that detects environmental data for various functions.
81. **Q:** Name three types of sensors commonly found in smartphones.
**A:** Motion sensors, environmental sensors, position sensors.
82. **Q:** What does an accelerometer do?
**A:** Detects device orientation and movement.
83. **Q:** What is the function of an ambient light sensor?
**A:** Adjusts screen brightness based on surrounding light.
84. **Q:** What is a proximity sensor used for?
**A:** Detects objects near the phone, such as during calls to turn off the display.
85. **Q:** What is the function of a gyroscope sensor?
**A:** Measures device rotation and supports VR/AR experiences.
86. **Q:** What does a barometer sensor measure?
**A:** Altitude (height).
87. **Q:** What is the function of a compass sensor?
**A:** Detects the direction the device is facing.
88. **Q:** What is a pedometer sensor?
**A:** Counts the number of steps taken by the user.
89. **Q:** What is a Hall sensor used for in tablets?
**A:** Detects the opening and closing of flip covers.

---

## **Android App Resources**

90. **Q:** What is stored in the anim/ directory?
**A:** XML files compiled into animation objects.
91. **Q:** What is the drawable/ directory used for?
**A:** Bitmap files and XML files for drawable shapes.
92. **Q:** What is the mipmap/ directory used for?
**A:** App launcher icons.
93. **Q:** What is the menu/ directory used for?
**A:** XML files that define application menus.
94. **Q:** What is the raw/ directory used for?
**A:** Arbitrary raw asset files like media.
95. **Q:** What is the values/ directory used for?
**A:** XML files that define resources by type, not by file name.

---

## **Android Studio Project Structure**

96. **Q:** What is the purpose of the build/ directory?
**A:** Stores build output for all project modules.
97. **Q:** Where are private libraries stored in an Android project?
**A:** libs/ directory.
98. **Q:** What is the function of the proguard-rules.pro file?
**A:** Stores ProGuard settings for code obfuscation and optimization.
99. **Q:** What is the gradle.properties file used for?
**A:** Project-wide Gradle settings.
100. **Q:** What is the settings.gradle file used for?
**A:** Specifies the sub-projects to build in a Gradle project.

---
update log
2025-04-27