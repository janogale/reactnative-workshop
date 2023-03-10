---
path: '/platform-specific-code'
title: 'Platform Specific Code'
order: 26
section: 'Extra Credit'
description: 'Platform specific code: how to write code that targets a specific platform'
---

Although most of the time one codebase for two apps works like a charm, there can be times when you'll want to show something in a way on Android and in another on iOS. This usually happens when some native library is only available on one of the platforms, e.g. [DatePickeriOS](https://reactnative.dev/docs/datepickerios) or [DrawerLayoutAndroid](https://reactnative.dev/docs/drawerlayoutandroid), or some minor updates like colors or fonts need to be consistent with the OS. You may have noticed that colors can look a bit duller on Android screens and sometimes you may want to adjust for that.

## Platform option

Suppose you wanted to prompt the user to go to the App Store / Google Play Store for something. This is an example of something that would need to be displayed conditionally based on the platform. For this, you can use the [Platform module](https://reactnative.dev/docs/platform-specific-code#platform-module) built into React Native:

```js
import { Platform } from 'react-native';
const store = Platform.OS === 'ios' ? 'App Store' : 'Google Play Store';
```

The `Platform.OS` will be `android` or `iOS` depending on the platform.

If you wanted to apply conditional _styles_ based on the platform, you might want to use `Platform.select`:

```js
import { Platform, StyleSheet } from 'react-native';

const styles = StyleSheet.create({
  container: {
    flex: 1,
    ...Platform.select({
      ios: {
        backgroundColor: 'red',
      },
      android: {
        backgroundColor: 'blue',
      },
    }),
  },
});
```

## Platform specific extensions

Sometimes you might want to have a a whole component be custom to the platform. We usually avoid this when possible (since maintaining 2 versions of the same code is what we are trying to avoid with React Native!), but sometimes it is necessary and there is a very handy way to do this using [file extensions](https://reactnative.dev/docs/platform-specific-code#platform-specific-extensions).

Suppose you had to build a custom `AwesomeButton` component for Android and iOS. Then instead of one `AwesomeButton.js` file, you should have two and place them next to each other in the same directory:

```sh
AwesomeButton.ios.js
AwesomeButton.android.js
```

Now if from another file you import `AwesomeButton` as you would normally:

```js
import AwesomeButton from './AwesomeButton';
```

Then React Native will autimatically import the `.android.js` one on Android and `.ios.js` one on iOS.
