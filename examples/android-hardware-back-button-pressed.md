# Task to be performed when back button pressed on android

```js
const backAction = () => {
  ...
}
export const createHardwareBackButtonPressedHandler = () => {
  const backHandler = BackHandler.addEventListener(
    'hardwareBackPress',
    backAction
  );
  return () => backHandler.remove();
};
```
