# Execution failed for task ':react-native-screens:compileDebugKotlin'

Dt. 27/06/2022
React Native Version: 0.69
React: 18
React native screens: 3.13.1

## solution

In my android/build.gradle file i change this:

```
buildscript {
    ext {
        // ...
        kotlin_version = '1.6.10' // <- add this line
    }

    dependencies {
        // ...
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version" // <- add this line
        // ...
    }
}
```
