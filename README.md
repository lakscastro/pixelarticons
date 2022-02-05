## How to use

Same as `IconsData`, just rename to `PixelArtIcons`

You can import the icon data by importing:

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

## Breaking Change Exception

This means that this tool can't find the latest release of the [pixelarticons](https://github.com/halfmage/pixelarticons) repository

**But this can have several causes**, so the best way to fix that is to first figure out where the icons are located in the original repository and then update the `~/download/download.py` script to fix/cover the breaking changes **if they exists** (this error can also be caused by a simple python exception)

Please fill a issue to see what is going wrong and do not worry: all current releases and versions will be available
