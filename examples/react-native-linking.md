# Linking in React Native

in AndroidManifest.xml made the following changes

```java
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
  package="com.deep_linking">

    <uses-permission android:name="android.permission.INTERNET" />
    
    // Add the below lines starting from here
    <queries>
      <intent>
        <action android:name="android.intent.action.VIEW" />
        <data android:scheme="http"/>
      </intent>
      <intent>
        <action android:name="android.intent.action.VIEW" />
        <data android:scheme="https"/>
      </intent>
      <intent>
        <action android:name="android.intent.action.VIEW" />
        <data android:scheme="geo" />
      </intent>
      <intent>
        <action android:name="android.intent.action.VIEW" />
        <data android:scheme="google.navigation" />
      </intent>
    </queries>
    // Upto here
    
    <application
      android:name=".MainApplication"
      android:label="@string/app_name"
      android:icon="@mipmap/ic_launcher"
      android:roundIcon="@mipmap/ic_launcher_round"
      android:allowBackup="false"
      android:theme="@style/AppTheme">
      <activity
        android:name=".MainActivity"
        android:label="@string/app_name"
        android:configChanges="keyboard|keyboardHidden|orientation|screenLayout|screenSize|smallestScreenSize|uiMode"
        android:launchMode="singleTask" // check for this line also
        android:windowSoftInputMode="adjustResize"
        android:exported="true">
        <intent-filter>
            <action android:name="android.intent.action.MAIN" />
            <category android:name="android.intent.category.LAUNCHER" />
        </intent-filter>
      </activity>
    </application>
</manifest>
```


```js
import React, { useCallback } from "react";
import { Alert, Button, Linking, StyleSheet, View } from "react-native";

const supportedURL = "https://google.com";

const unsupportedURL = "slack://open?team=123456";

const OpenURLButton = ({ url, children }) => {
  const handlePress = useCallback(async () => {
    // Checking if the link is supported for links with custom URL scheme.
    const supported = await Linking.canOpenURL(url);

    if (supported) {
      // Opening the link with some app, if the URL scheme is "http" the web link should be opened
      // by some browser in the mobile
      await Linking.openURL(url);
    } else {
      Alert.alert(`Don't know how to open this URL: ${url}`);
    }
  }, [url]);

  return <Button title={children} onPress={handlePress} />;
};

const App = () => {
  return (
    <View style={styles.container}>
      <OpenURLButton url={supportedURL}>Open Supported URL</OpenURLButton>
      <OpenURLButton url={unsupportedURL}>Open Unsupported URL</OpenURLButton>
    </View>
  );
};

const styles = StyleSheet.create({
  container: { flex: 1, justifyContent: "center", alignItems: "center" },
});

export default App;
```
source : https://reactnative.dev/docs/linking
