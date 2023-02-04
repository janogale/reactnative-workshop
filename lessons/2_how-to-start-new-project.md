---
path: '/the-expo-debate'
title: 'Should you use Expo or plain React Native?'
order: 2
section: 'Introduction'
description: 'We discuss the benefits and drawback of using Expo'
---

There are two popular ways to create a React Native app — you can use the **Expo CLI** or you can use the **React Native CLI**. Planning to build a cross-platform app, you may get confused between React Native or Expo.

##### So which one is better for the development of your app?

## Expo

- If you are new to mobile development, the easiest way to get started is with Expo Go. Expo is a set of tools and services built around React Native and, while it has many features, the most relevant feature for us right now is that it can get you writing a React Native app within minutes.

Expo is a framework to build React Native apps. It is a set with tools and services built for React Native. It will help you begin with building React Native apps with ease.

- If you are already familiar with mobile development, you may want to use React Native CLI. It requires **Xcode** or **Android Studio** to get started. If you already have one of these tools installed, you should be able to get up and running within a few minutes. If they are not installed, you should expect to spend about an hour installing and configuring them.

#### macOS

- Expo on physical device: ~10 minutes (Android or iOS)
- Expo on iOS simulator: ~1 hour
- Expo on Android emulator: ~1.5 hours
- Plain React Native on physical device: ~2 hours (Android or iOS)
- Plain React Native on iOS simulator: ~2 hours
- Plain React Native on Android emulator: ~2 hours

#### Windows or Linux

- Expo on physical device: ~20 minutes (Android or iOS)
- Expo on iOS simulator: ❌
- Expo on Android emulator: ~2 hours
- Plain React Native on physical device: ~2.5 hours (Android only)
- Plain React Native on iOS simulator: ❌
- Plain React Native on Android emulator: ~3 hours

## Expo Limitations

Expo restrictions only really come to play when you're doing advanced things with React Native. In particular, if you need to make any _native_ changes to your code. Basically if you need to install any libraries or add anything that changes any of the non-JavaScript code or configurations. You'll have to eject from the Expo safe space and start managing all your native code yourself as you would with plain React Native.
