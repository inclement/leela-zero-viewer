
# Lazy Baduk

A Go game analysis tool for Android, providing the power of Leela Zero
on your smartphone.

[Leela Zero](https://zero.sjeng.org/) is a strong Go bot, created as
an independent implementation of the Alphago Zero deep learning
algorithms. It's now so strong that even on a phone, with relatively
few playouts, it can achieve a high dan level.

Note that Leela Zero's analysis uses as much CPU power as it can, and
will rapidly burn through battery power if not charging.

<p align="center">
  <img src="screenshots/example_screenshot_small.png">
</p>

# Download

Lazy Baduk is available [on Google
Play](https://play.google.com/store/apps/details?id=net.inclem.lazybaduk). This
version currently uses the last 15x192 network, from July 2018, in
order to try to be as fast as practical on a phone. Larger networks
take longer to initialise and to generate playouts.

Versions incorporating other networks are available for direct download:
- (v0.7) [15b network trained on 40b games](https://github.com/inclement/LazyBaduk/releases/download/0.7/lazybaduk-0.7-release-signed.apk): the same as version 0.7 on Google Play. This network was released [here](https://github.com/leela-zero/leela-zero/issues/2192), it is chosen as a small but strong network is ideal for maximum playouts on mobile devices. Note: the app name for this APK is simply "Lazy Baduk".
- (v0.6) [Latest 15x192 network d351f06e](https://github.com/inclement/LazyBaduk/releases/download/0.6/lzviewer15x192-0.6-release-signed.apk): the same as version 0.5 on Google Play
- (v0.6) [Latest 20x256 network 33986b7f](https://github.com/inclement/LazyBaduk/releases/download/0.6/lzviewer20x256-0.6-release-signed.apk)
- (v0.6) [Latest 40x256 network 85a93684](https://github.com/inclement/LazyBaduk/releases/download/0.6/lzviewer40x256-0.6-release-signed.apk): this one especially is much larger and slower to load than the 15x192 version
- (v0.6) [Elfv2](https://github.com/inclement/LazyBaduk/releases/download/0.6/lzviewerElfv2-0.6-release-signed.apk): the [ELF OpenGo version 2](https://github.com/pytorch/elf) weights converted for use with Leela Zero. ELF is Facebook's own implementation of a zero knowledge algorithm, and is very strong (network size 20x256).
- (v0.6) [9x9](https://github.com/inclement/LazyBaduk/releases/download/0.6/lzviewer9x9-0.6-release-signed.apk): uses the 9x9 weights generated by @sbf2000 [here](https://github.com/leela-zero/leela-zero/issues/1291) (these may not be the strongest 9x9 weights available)
- (v0.6) [13x13](https://github.com/inclement/LazyBaduk/releases/download/0.6/lazybaduk13x13-0.6-release-signed.apk): uses the 13x13 weights generated [by @alreadydone](https://github.com/leela-zero/leela-zero/issues/2240#issuecomment-466476336) from the 19x19 weights #205 (the linked issue describes this conversion process), apparently this network is quite strong

# Changelog

## Version 0.7

Updated Leela Zero to version 0.17 in precompiled versions.

Added region select option (newly supported in Leela Zero 0.17). Pondering will only suggest sequences that start in the selected region.

Added pass button and coordinates toggle.

## Version 0.6

First announced release.

## Version 0.5 (untagged)

Original release on Google Play.

# Technical details

Lazy Baduk is written in Python using [Kivy](https://kivy.org/). This
means that it can also run on the desktop.

The app includes a Leela Zero binary compiled for Android, so all
analysis is run on your device. It does not currently use the GPU,
although it might be possible to compile a version supporting OpenCL
for devices that support it.
