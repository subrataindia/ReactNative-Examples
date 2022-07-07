# How to run on react-native app on physical device through wifi ?

- Open Android Studio
- From a list of devices choose "Pair device using wifi"
- Run the app. It will install app through wifi on your physical device. But will display error because unable to access metro bundler.

run the command on mac `ifconfig | grep "inet "`

```
        inet 127.0.0.1 netmask 0xff000000 
        inet 192.168.29.186 netmask 0xffffff00 broadcast 192.168.29.255
```

in the above 192.168.29.186 is the ip address.

run the command on windows `ipconfig` : It will display IPV4 address

- On android, you should be able to open the dev menu by "Long" pressing the 'Overview' button (the square). or the back button or by shaking.
- choose settings from dev menu.
- Click on device server host and port for device and enter the ip address and port

```
  192.168.29.186:8081
```

port number 8081 is the default port for react native development server.

