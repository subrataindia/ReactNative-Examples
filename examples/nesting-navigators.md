# Nesting Navigators

For example you need an application having side drawer on all screens with bottom tab. In this case on main app include `DrawerNavigator`, With in this include `Bottom Tab Navigator`. If you have more screens, then with in bottom tab navigator include `Stack Navigator`.

- App.js

```js
import React from 'react';
import {
  SafeAreaView,
  useColorScheme,
} from 'react-native';
import {NavigationContainer} from '@react-navigation/native';
import MyDrawer from './mydrawer/MyDrawer';

const App = () => {

  return (
    <SafeAreaView style={{flex:1}}>
      <NavigationContainer>
        <MyDrawer />
      </NavigationContainer>
    </SafeAreaView>
  );
};

export default App;

```

- MyDrawer.js

```js
import React from 'react';
import { createDrawerNavigator } from '@react-navigation/drawer';
import About from '../screens/About';
import BottomTab from '../bottomtab/BottomTab';
import Screen4 from '../screens/Screen4';

const Drawer = createDrawerNavigator();

function MyDrawer() {
  return (
    <Drawer.Navigator>
      <Drawer.Screen name="Home" component={BottomTab} />
      <Drawer.Screen name="About" component={About} />
      <Drawer.Screen name="Screen4" component={Screen4} />
    </Drawer.Navigator>
  );
}

export default MyDrawer;
```

- BottomTab.js

```js
import React from 'react';
import {createBottomTabNavigator} from '@react-navigation/bottom-tabs';
import Feather from 'react-native-vector-icons/Feather';
import About from '../screens/About';
import Screen3 from '../screens/Screen3';
import HomeStack from '../homestack/HomeStack';

const Tab = createBottomTabNavigator();
const BottomTab = () => {
    return (
        <Tab.Navigator screenOptions={{ headerShown:false, tabBarShowLabel: false, tabBarStyle:{backgroundColor:'green'} }}>
            <Tab.Screen name="Home2" component={HomeStack} options={{ tabBarIcon : () => <Feather name="home" size={32} color={'white'}/>}} />
            <Tab.Screen name="About" component={About}  options={{ tabBarIcon : () => <Feather name="airplay" size={32} color={'white'}/>}} />
            <Tab.Screen name="Screen" component={Screen3}  options={{ tabBarIcon : () => <Feather name="heart" size={32} color={'white'}/>}} />
        </Tab.Navigator>
    );
};
export default BottomTab;
```

- HomeStack.js

```js
import React from 'react'
import {createStackNavigator} from '@react-navigation/stack';
import Screen3 from '../screens/Screen3';
import Home from '../screens/Home';

const Stack = createStackNavigator();
const HomeStack = () => {
  return (
    <Stack.Navigator screenOptions={{ headerShown: false}}>
      <Stack.Screen name="Home3" component={Home} />
      <Stack.Screen name="Screen3" component={Screen3} />
    </Stack.Navigator>
  );
};

export default HomeStack;
```
