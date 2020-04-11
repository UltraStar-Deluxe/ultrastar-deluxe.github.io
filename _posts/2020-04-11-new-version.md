---
layout: post
title:  "New Version 2020.4.0"
date:   2020-04-11 20:09:00 +0200
categories: news
---
After years of development, we are proud to present the new stable version 2020.4.0 of UltraStar Deluxe.
The changes in this version are:

* support for recent FFmpeg and OpenCV versions
* new pitch detection algorithm
* new shortcuts (f.ex. Tab for help, Ctrl+R to shuffle players in party mode)
* new default font (Noto), which supports more languages
* configurable audio/video delay correction (Tools -> Options -> Game)
* improvements to the built-in editor, which is now also available on all platforms by playing notes through PortMidi
* improved microphone support (more than two channels and macOS fixes)
* improvements and fixes to webcam integration
* lots of other fixes (race conditions, memory leaks, kerning across syllables, sorting of songs, OpenGL library loading, Lua 5.3 support, video borders, colors on big endian, ...)
* a few translation updates, especially for Slovak, Hungarian, Greek, and German
* dropped dependency on libGLU and PCRE

You can download the release in the [download section](/downloads/) and on our [Github releases page](https://github.com/UltraStar-Deluxe/USDX/releases).

Note that there are a few known problems that have to be fixed outside of USDX and might bite you regardless of the UltraStar Deluxe version:

* BASS on Windows causes crashes when devices are set to high sample rates ([USDX Issue #330](https://github.com/UltraStar-Deluxe/USDX/issues/330))
* macOS Catalina has graphics issues with SDL < 2.0.12 ([SDL Bug #4822](https://bugzilla.libsdl.org/show_bug.cgi?id=4822))
* The current Free Pascal release causes crashes in used libraries on 32 bit x86 Linux due to insufficient stack alignment ([FPC Bug #15582](https://bugs.freepascal.org/view.php?id=15582))
