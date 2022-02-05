<samp>
  
<p align="center">
  <img src="https://user-images.githubusercontent.com/51419598/152648731-567997ec-ac1c-4a9c-a816-a1fb1882abbe.png" width="150">
</p>
  
<samp><h6 align="center">#dart, #flutter, #package, #icons</h6></samp>
<samp><h1 align="center">Pixel Art Icons</h1></samp>

<h6 align="center"><samp>Dart package to use <a href="https://pixelarticons.com/"><code>pixelarticons</code></a> in Flutter</samp></h6>

<p align="center">
  <img src="https://img.shields.io/badge/Dart-22272E?&style=for-the-badge&logo=dart&logoColor=48C1BB">
  <img src="https://img.shields.io/badge/Flutter-22272E?style=for-the-badge&logo=flutter&logoColor=54C2F6">
  <img src="https://img.shields.io/badge/Python-22272E?style=for-the-badge&logo=python&logoColor=326EA0">
</p>
  
<p align="center">
  <a href="https://pub.dartlang.org/packages/pixelarticons"><img src="https://img.shields.io/pub/v/pixelarticons.svg" /></a>
</p>

<kbd><img src="https://user-images.githubusercontent.com/51419598/152649069-fa447289-0e7f-4c5e-af4d-bef4c62c71ce.png"></kbd>

</samp>

<br />

## ⚠️ Original author

**I'm neither the creator or the author** of these icons, **the original author is [@halfmage](https://github.com/halfmage)** on the [pixelarticons](https://github.com/halfmage/pixelarticons)

So, please if you like these icons, **thanks to [@halfmage](https://github.com/halfmage)!** and show support on the original repository!

> ### This package is just an automated tool to generate the font from the svg icons created by [@halfmage](https://github.com/halfmage)

## How to use

### 1. Install the package

You can also check the on [pub.dev](https://pub.dartlang.org/packages/pixelarticons)

```shell
flutter pub add pixelarticons
```

### 2. Import in to the project

Import wherever you want

```dart
import 'package:pixelarticons/pixelarticons.dart';
```

### 3. Use as `IconData`

`pixelarticons` is the same of `Icons` class but renamed to `Pixel`

Be aware:

- **Lower-case for all icons and no separators**, for example `card-plus` is written as `Pixel.cardplus`
- Icons that **starts with non-alpha characters**, like `4k`, `4k-box`, `4g` are prefixed with `k`
- Icons that are Dart keywords, like `switch` are prefix with `k` as well

So use `k4k`, `k4kbox`, `kswitch` instead

```dart
/// 4k icon:
Icon(Pixel.k4k)

/// switch icon:
Icon(Pixel.kswitch)

/// align-left icon:
Icon(Pixel.alignleft);
```

## Why

You can download directly from the source, but you'll need convert all the svgs to font and generate the Dart classes... and you'll repeat the process if you want to include a new released icon in the future

So this library was made to fix this gap. Lets allow the machine do the hard work for us and we focus on the human and important part of using the icons to improve the UX and UI of the app

## Contribute

As you can see, **I'm not native English speaker**, so this library certainly has many gramatical errors, typo, and wrong words. So if you have a proficient English you can contribute by fixing all these documentation errors!

If you can **improve the tool**, please, feel free to open a issue to discuss, I'll appreciate it!

> Also, if you miss any icon, please ping me on the repository issues or Discord `laks#1712`, I'll take care to verify and trigger the update, thanks!

## Flow

This library works automatically:

- `/download` contains a python script that downloads svg from all icons of `pixelarticons`
- `/lib` contains an entry point that exports the generated icon classes (generated by [fontify](https://github.com/westracer/fontify))

This flow is powered by GitHub actions, and the triggers are:

- scheduled: once a month we'll check if new icons are available, if so we'll update the `pub.dev` library otherwise we'll just ignore the possible update
- manually: if we go to `actions` tab, we can trigger the `flow.yaml` action clicking `run` over the action card (need repo write access)

### How to generate the icons

Environment

```
Dart SDK version: 2.14.4 (stable)
Python 3.9.9
```

Working dir: `~/`

**1. Download icons using Python**

```
py download/download.py
```

**2. Generate classes with `fontify`**

Add `fontify` as global dependency

```
dart pub global activate fontify
```

Run `fontify`

```
dart pub global run fontify
```

**Done**, you'll see a folder called `~/release` and a font `~/fonts/pixelarticons.otf`

What you want is the font inside the `~/fonts` folder, the `~/release` folder should be ignored. Now you can publish or do whatever you want!

## Breaking Change Exception

This means that this tool can't find the latest release of the [pixelarticons](https://github.com/halfmage/pixelarticons) repository

**But this can have several causes**, so the best way to fix that is to first figure out where the icons are located in the original repository and then update the `~/download/download.py` script to fix/cover the breaking changes **if they exists** (this error can also be caused by a simple python exception)

Please fill a issue to see what is going wrong and do not worry: all current releases and versions will be available

<br>

<h2 align="center">
  Open Source
</h2>
<p align="center">
  <sub>Copyright © 2022-present, Laks Castro.</sub>
</p>
<p align="center">Pixel Art Icons Dart Wrapper <a href="https://github.com/LaksCastro/pixelarticons/blob/master/LICENSE">is MIT licensed 💖</a></p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/51419598/152648448-82403d04-c90a-44e7-ae9c-797228864985.png" width="35" />
</p>
