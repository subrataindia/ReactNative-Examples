# cannot find symbol ViewManagerResolver

[ViewManagerResolver Error](https://github.com/software-mansion/react-native-reanimated/issues/3161)


```
Okay, seems like doing the following fix the problem.

Apply this patch manually ( https://github.com/software-mansion/react-native-reanimated/search?q=ViewManagerResolver )
In \node_modules\react-native-reanimated\android\src\main\java\com\swmansion\reanimated\layoutReanimation\ReanimatedUIImplementation.java
Modify the following:

In line 13 inside ReanimatedUIImplementation:

ViewManagerResolver viewManagerResolver
To:

UIManagerModule.ViewManagerResolver viewManagerResolver
```
