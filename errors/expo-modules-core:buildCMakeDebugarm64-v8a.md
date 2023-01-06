# Task :expo-modules-core:buildCMakeDebug[arm64-v8a] FAILED


Fix when not using Android Studio:

- On android/gradle/wrapper/gradle-wrapper.properties, set `distributionUrl=https\://services.gradle.org/distributions/gradle-7.5-all.zip`
- On android/build.gradle, set `classpath("com.android.tools.build:gradle:7.2.1")`
- Rebuild
