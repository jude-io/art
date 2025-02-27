# `@react-native-community/art`

[![CircleCI](https://img.shields.io/circleci/project/github/react-native-community/art/master.svg?style=flat-square)](https://circleci.com/gh/react-native-community/art) ![MIT License](https://img.shields.io/npm/l/@react-native-community/slider.svg) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com) ![Supports Android and iOS](https://img.shields.io/badge/platforms-android%20|%20ios-lightgrey.svg)

> _NOTE: ART was extracted from core `react-native` as a part of "[Lean Core](https://github.com/facebook/react-native/issues/23313)" effort._

React Native module that allows you to draw vector graphics

# Getting started

## Installing module

```sh
yarn add @react-native-community/art
```

or

```sh
npm install @react-native-community/art --save
```

## Linking module

### Mostly automatic linking

```js
react-native link @react-native-community/art
```

### Manual linking

<details>
<summary>Manually linking the library for iOS</summary>

#### `Open project.xcodeproj in Xcode`

Drag `RNCSlider.xcodeproj` to your project on Xcode (usually under the Libraries group on Xcode):
![xcode-add](https://facebook.github.io/react-native/docs/assets/AddToLibraries.png)

#### Link `libART.a` binary with libraries

Click on your main project file (the one that represents the `.xcodeproj`) select `Build Phases` and drag the static library from the `Products` folder inside the Library you are importing to `Link Binary With Libraries` (or use the `+` sign and choose library from the list):

![xcode-link](https://facebook.github.io/react-native/docs/assets/AddToBuildPhases.png)

</details>

<details>
<summary>Manually linking the library for Android</summary>

#### `android/settings.gradle`

```groovy
include ':react-native-art'
project(':react-native-art').projectDir = new File(rootProject.projectDir, '../node_modules/@react-native-community/art/android')
```

#### `android/app/build.gradle`

```groovy
dependencies {
   ...
   implementation project(':react-native-art')
}
```

#### `android/app/src/main/.../MainApplication.java`

On top, where imports are:

```java
import com.reactnativecommunity.art.ARTPackage;
```

Add the `ARTPackage` class to your list of exported packages.

```java
@Override
protected List<ReactPackage> getPackages() {
    return Arrays.asList(
            new MainReactPackage(),
            new ARTPackage()
    );
}
```

</details>

# Migrating from the core `react-native` module

To migrate to this module you need to follow all the installation instructions above and change your imports from:

```js
import {ART} from 'react-native';
const {Surface, Shape} = ART;
```

to:

```js
import {Surface, Shape} from '@react-native-community/art';
```

# Documentation

You can find API reference [here](https://github.com/react-native-community/art/tree/master/docs/api.md).

## License

The library is released under the MIT licence. For more information see `LICENSE`.
