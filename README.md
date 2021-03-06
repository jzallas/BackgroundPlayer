#  BackDrop
[![Actions Status](https://github.com/jzallas/BackDrop/workflows/android-release/badge.svg)](https://github.com/jzallas/BackDrop/actions)
[![license](https://img.shields.io/github/license/jzallas/BackDrop)](https://github.com/jzallas/BackDrop/blob/master/LICENSE)
[![releases](https://img.shields.io/github/v/release/jzallas/backdrop)](https://github.com/jzallas/BackDrop/releases)

Plays youtube audio in the background.

![BackDrop animation GIF showing launching content via intent filter](preview_animation.gif)


### Prerequisites
1. [node 11](https://nodejs.org/en/)


### Build
Before building the application, the web resources need to be built. Run the following to build the web resources:

```bash
$ cd web
$ npm ci
$ npm run build
```
### Launching
This application cannot be launched from the launcher. It can only be launched via an intent filter. So, if you try to share a url from any other application, this application should capture the accept the intent and attempt to play it in a background service.

You can use adb to simulate an intent needed to launch this application:

```bash
$ export URL="url_goes_here"
$ adb shell am start -n "com.jzallas.backdrop/.MainActivity" --es "android.intent.extra.TEXT" $URL
```
