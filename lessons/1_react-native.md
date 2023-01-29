---
path: '/react-native'
title: 'About React Native'
order: 1
section: 'Introduction'
description: 'Kadi talks about the history of React Native, why was it created and how it works on a high level'
---

<div style="width:500px;margin:0 auto;margin-bottom:20px;">
    <img alt="iOS and Android phone" src="./images/react-native.png" />
</div>

### What is React Native?

**React Native** is an open-source mobile application framework created by Facebook. It is used to develop applications for Android, iOS, Web and Windows providing native UI controls and full access to the native platform. Working with React Native requires an understanding of JavaScript fundamentals.

<div style="width:500px;margin:0 auto;margin-bottom:20px;">
    <img alt="iOS and Android phone" src="./images/rn-how-work-1.png" />
</div>

### React Native Features

Following are the features of React Native −

- **React** − This is a Framework for building web and mobile apps using JavaScript.
- **Native** − You can use native components controlled by JavaScript.
- **Platforms** − React Native supports IOS and Android platform.

### React Native Advantages

Follow are the advantages of React Native −

- **JavaScript** − You can use the existing JavaScript knowledge to build native mobile apps.
- **Code sharing** − You can share most of your code on different platforms.
- **Community** − The community around React and React Native is large, and you will be able to find any answer you need

### Why React Native?

Applications are designed to run on a particular _operating system_ so you can't just take an iOS app and run it on Android and vice versa. App Store vs Google Play Store aside, the underlying _architecture_ is incompatible.

<div style="width:600px;margin:0 auto;">
    <img alt="Mobile market share" src="./images/market-share.png" />
</div>

Now, as phones are just tiny computers, they have an operating system, the same way your computer does.

- **Some examples of computers:** MacBook, Dell, Lenovo
- **Some examples of operating systems:** macOS, Windows, Linux
- **Some examples of phones:** iPhone, Samsung Galaxy S20, Nexus 5X
- **Some examples of phone operating systems:** iOS, Android

So in order to target 99% of smartphone users, we'll have to build two apps: one for Android and one for iOS.

<div style="width:600px;margin:0 auto;margin-bottom:20px;">
    <img alt="Separate developer teams" src="./images/rn-how-work-2.png" />
</div>

It's easy to imagine the difficulties this can cause: you'll have to manage two of everything: language, codebases, developer teams, feature sets, release schedules etc. Hiring two developer teams is expensive, and hiring a single team that has in depth knowledge of both Android and iOS is almost impossible.

React Native is a platform developed by Facebook for solving this problem. Their goal was to build a platform that enables you to have:

- fully native apps (not webviews/PWAs)
- one codebase
- one development team
- one language
- fully extensible (you should be anything that is possible without using React Native)

<div style="width:700px;margin:0 auto;margin-bottom:20px;">
    <img alt="One dream RN team" src="./images/rn-how-work-3.png" />
</div>

Note: React Native is not the only such framework, and it's not even the first, but where it differs from others is that a built React Native app is indistinguishable from a "real" native app. Unlike most of the other frameworks, it is not just a webview that look like a real app. The other really standout feature is that React Native apps are infinitely extensible: you are not constrained by the framework and you can always pure native code in your app if you want to do something the framework doesn't already enabled. Finally, if you're already familiar to React and web development, then the learning curve for React Native is really not that steep.

## How does it work?

<div style="width:700px;margin:0 auto;margin-bottom:20px;">
    <img alt="RN targets existing compilers" src="./images/rn-how-work-4.png" />
</div>

**React Native Bridge**: React Native bridge is a C++/Java bridge which is responsible for communication between the native and Javascript thread.

React Native is built in such a way that it targets existing compilers. For example, we have compilers that accept Java / Kotlin code and target Android platform, or Objective C / Swift targeting iOS platform. This is really powerful, because

1. Native compilers are _designed_ for this, so we'll be no worse than non-React Native apps, and
2. This makes the React Native framework extensible to other native platforms. React Native Windows? VR? Web? It could all be available from our one unified JavaScript API.
