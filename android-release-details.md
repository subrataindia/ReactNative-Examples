

# How to upgrade to targetSdkVersion 31

Starting from November 2022 google made it compulsory to target API level 31 (Android 12).

### Behavior Changes: Apps Targeting Android 12

1)

Android 12 changes the appearance and behavior of fully custom notifications. Previously, custom notifications were able to use the entire notification area and provide their own layouts and styles. This resulted in anti-patterns that could confuse users or cause layout compatibility issues on different devices.

Android 12 makes all notifications visually consistent and easy to scan, with a discoverable, familiar notification expansion for users.

2)

Approximate location : On devices that run Android 12 or higher, users can request approximate location accuracy for your app.

3)

Modern SameSite cookies in WebView: Android’s WebView component is based on Chromium, the open source project that powers Google’s Chrome browser. Chromium introduced changes to the handling of third-party cookies to provide more security and privacy and offer users more transparency and control. Starting in Android 12, these changes are also included in WebView when apps target Android 12 (API level 31) or higher.

4)

Motion sensors are rate-limited: To protect potentially sensitive information about users, if your app targets Android 12 or higher, the system places a limit on the refresh rate of data from certain motion sensors and position sensors.

5)

App hibernation: Android 12 expands upon the permissions auto-reset behavior that was introduced in Android 11 (API level 30). If your app targets Android 12 and the user doesn't interact with your app for a few months, the system auto-resets any granted permissions and places your app in a hibernation state.

6)

Attribution declaration in data access auditing:

The data access auditing API, introduced in Android 11 (API level 30), allows you to create attribution tags based on your app's use cases. These tags make it easier for you to determine which part of your app performs a specific type of data access.

If your app targets Android 12 or higher, you must declare these attribution tags in your app's manifest file.

[Read this for detailed documentation](https://developer.android.com/about/versions/12/behavior-changes-12#foreground-service-launch-restrictions)


## Update Android 12 SDK 

To using and testing Android 12 API, developer must update app's Android SDK. If you are using Android Studio (or other IDE) please set your Target API 31.

### SDK install

- Go to the menu on Tools > SDK Manager on Android Studio.
- On SDK Platforms  select Android 12.
- On SDK Tools tap select Android SDK Build-Tools 31.
- Click the OK button to install the SDK.
- Go to the build.gradle on Apps folder and update following script.

```
android {
    compileSdkVersion 31

    defaultConfig {
        targetSdkVersion 31
    }
}
```





