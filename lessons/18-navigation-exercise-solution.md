---
path: '/navigation-exercise-solution'
title: 'Navigation Exercise Solution 👀'
order: 18
section: 'Navigation'
description: 'Navigation exercise solution'
---

## Navigation Exercise Solution - Part 1

_Update the app so that the colors and name are being passed into the ColorPalette component, making it reusable._



For this we need to move the `COLORS` constant from `ColorPalette` to `Home` and pass in both the paletteName and colors as a second argument to `navigation.navigate`.

Then in `ColorPalette`, use the `route` prop, specifically `route.params.paletteName` and `route.params.colors` to replace the previously hardcoded values.

Finally, if you haven't done so already, add `backgroundColor: 'white'` to the `container` style in `ColorPalette`. React Navigation adds a greyish background to pages by default.

## Navigation Exercise Solution - Part 2

_Make sure the page title will be the name of the color palette instead of the name of the page._


As in the [docs](https://reactnavigation.org/docs/headers#using-params-in-the-title), open `App.js` and add an extra prop to the ColorPalette screen:

```js
options={({ route }) => ({ title: route.params.paletteName })}
```

You can also delete the `ListHeaderComponent` prop from `ColorPalette`, since the palette name is already displayed as the page title.

## Navigation Exercise Solution - Part 3

_Add a the new color schemes._



Fist off we'll want to create a new array for `COLOR_PALETTES`:

```js
// screens/Home.js

const COLOR_PALETTES = [
  { paletteName: 'Solarized', colors: SOLARIZED },
  { paletteName: 'Frontend Masters', colors: FRONTEND_MASTERS },
  { paletteName: 'Rainbow', colors: RAINBOW },
];
```

Next up we can replace our existing code in the render with a single FlatList:

```js
// screens/Home.js

<FlatList
  data={COLOR_PALETTES}
  keyExtractor={item => item.paletteName}
  renderItem={({ item }) => (
    <TouchableOpacity onPress={() => navigation.navigate('ColorPalette', item)}>
      <Text>{item.paletteName}</Text>
    </TouchableOpacity>
  )}
/>
```

Make sure you've replaced the hardcoded values in renderItem with the dynamic ones we're done!

## Navigation Exercise Solution - Part 4

Update the Home page to display the first 5 colors of the color scheme as preview



Create a new component in out components directory and let's call it `PalettePreview`. Before you start adding styling and colors to it, make sure the existing functionality remains unbroken.

In the Home component, update the `renderItem` to use `PalettePreview` instead:

```js
// screens/Home.js

<PalettePreview
  onPress={() => navigation.navigate('ColorPalette', item)}
  palette={item}
/>
```

And in PalettePreview, copy the code that used to be in renderItem and use the passed in props to display the component name and handle onPress:

```js
// components/PalettePreview.js

import React from 'react';
import { TouchableOpacity, Text, View } from 'react-native';

const PalettePreview = ({ palette, onPress }) => {
  return (
    <TouchableOpacity onPress={onPress}>
      <Text>{palette.paletteName}</Text>
    </TouchableOpacity>
  );
};

export default PalettePreview;
```

Now, add a FlatList under the `<Text>` in `PalettePreview` to render the three preview colors. Technically you could get away with not using `FlatList` here, since we know we'll only ever have 3 items to display, but using FlatList it's a good habit to get into and there's no harm, so I'd recommend always using a `FlatList` for 3+ items.

Note, you can use `palette.colors.slice(0, 3)` to get the first 3 items of your color array (never splice, as it mutates the array).

You'll have to pass in an array of styles to the little color square in order to set the background dynamically, like so:

```js
// components/PalettePreview.js

renderItem={({ item }) => (
    <View style={[styles.color, { backgroundColor: item.hexCode }]} />
)}
```

Finally, in order to ensure that the white palette colors still show up on the white background, add a shadow:

```js
shadowColor: '#000',
shadowOffset: { width: 0, height: 1 },
shadowOpacity: 0.3,
shadowRadius: 1,
elevation: 2,
```

`elevation: 2` is Android only and the rest is iOS only.
