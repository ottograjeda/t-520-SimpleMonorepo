React-Native SimpleMonorepo
=================
This is a simple, basic monorepo for frontend development using React-Native & React-Native-Web. It is a template or starter kit to share code between different platforms (Web, Android, & iOS).

The repo creates a generic app called "tenta" (Latin for try or test) from shared code. The key to code sharing is React-Native's [Platform-specific extensions](https://facebook.github.io/react-native/docs/platform-specific-code.html#platform-specific-extensions). The extensions are ```.native.js``` , ```.ios.js``` or ```.android.js``` and when used, the relevant platform file is compiled.

The main benefit of any monorepo is to share application logic. Another benefit is the rendering of individual components unique to each platform. Development is mobile-first AND then webapp.

Installation
============
* Get the repo
* From the root directory, do ```yarn```
* Change root/android/local.properties as needed

Required: React-Native working per [Getting Started](https://facebook.github.io/react-native/docs/getting-started)

Run
===

For each platform, from the root directory, do

### Web
* ```node_modules/.bin/webpack -p --progress```
* ```node_modules/.bin/webpack-dev-server --content-base public/ --config ./webpack.config.js --port 3001 --inline --hot --colors```
* Manually open a browser to localhost:3001 to see webapp 
* Inspect browser window = open console to see shared code working on button click

### Android
* ```react-native run-android```

### iOS
* ```react-native run-ios``` or open ```ios/tenta.xcodeproj``` with Xcode

Screenshots
===========

![Screenshot 1 - all](https://github.com/og-pr/public_ticket.520/blob/master/tenta/_docs/monorepo_all.png)
![Screenshot 2 - ios](https://github.com/og-pr/public_ticket.520/blob/master/tenta/_docs/monorepo_ios.png)
![Screenshot 3 - android](https://github.com/og-pr/public_ticket.520/blob/master/tenta/_docs/monorepo_android.png)

Notes - Development 
===========
* Due to platform specific UI rendering, CSS & App code are not shared.
* 1 element (a button), native to each platform, is used ; it is attached to 1 function.  
* 1 component (title) & 1 function (just logs console message) is shared for all 3 platforms.  

Notes - Miscellaneous 
=====
* Lerna or Yarn Workspaces is not used ; there is only 1 ```node_modules``` folder
* State / Props / Redux are not used. You can add them or any other package, as needed
* Examples of Shared Code = a) ```app/component/App``` , b) ```app/component/Title``` , c) ```common/example.js``` , + d) ```common/nativeStyles.js``` . If you want to create a NEW monorepo from scratch, start with React Native and use this repo as a model for all files & folders

Inspiration
===========
* [Sharing code btwn React Web and Native Apps](http://jkaufman.io/react-web-native-codesharing/)
* [Code sharing btwn React & React Native applications](http://ihor.burlachenko.com/code-sharing-between-react-and-react-native-applications/)
