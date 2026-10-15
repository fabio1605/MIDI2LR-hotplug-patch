# MIDI2LR 6.3.1.0 + hot-plug reconnect (unofficial patch)

This is an **unofficial** build of [MIDI2LR](https://github.com/rsjaffe/MIDI2LR) 6.3.1.0 with one fix added. Use it until the fix ships in an official release. It's proposed upstream in [rsjaffe/MIDI2LR#877](https://github.com/rsjaffe/MIDI2LR/pull/877).

## What it fixes

In the official 6.3.1.0, if you unplug your USB MIDI controller and plug it back in, MIDI2LR doesn't reconnect. You have to restart it or click **Rescan MIDI devices**, often several times.

With this build, MIDI2LR notices when MIDI devices change. Once Windows has finished setting up the device, it reconnects your controller (input and output, including LEDs and motor faders) automatically, usually within about 2 seconds. Nothing else is changed from 6.3.1.0.

Tested on Windows 11 with a Behringer X-Touch Mini and Lightroom Classic 15.6. **Windows x64 only.**

## Install

1. Install the official **MIDI2LR 6.3.1.0** from <https://github.com/rsjaffe/MIDI2LR/releases/tag/v6.3.1.0> and run it with Lightroom once.
2. **Close Lightroom.** MIDI2LR closes with it.
3. Open `%APPDATA%\Adobe\Lightroom\Modules\MIDI2LR.lrplugin\` (paste it into the Explorer address bar).
4. Rename `MIDI2LR.exe` to `MIDI2LR.exe.orig`.
5. Download [`MIDI2LR.exe`](https://github.com/fabio1605/MIDI2LR-hotplug-patch/raw/main/MIDI2LR.exe) from this repo and copy it into that folder.
6. Start Lightroom.

Windows SmartScreen may warn you because the exe isn't signed. Click **More info → Run anyway**.

## Undo

Close Lightroom, delete `MIDI2LR.exe`, and rename `MIDI2LR.exe.orig` back to `MIDI2LR.exe`.

An official MIDI2LR update replaces this exe automatically.

## Checksum

```
SHA-256  efa2fcb9b5403f6fa5b6e7273281499634d5a19be5099d92f21abf708893dde9  MIDI2LR.exe
```

## Source and licence

MIDI2LR is © Rory Jaffe and licensed under GPLv3. This build is made from the [`hotplug-reconnect` branch](https://github.com/fabio1605/MIDI2LR/tree/hotplug-reconnect) of my MIDI2LR fork (commit `2aced9bac`), built as Release x64 with Visual Studio 2026 Build Tools. It is not an official build and is not supported by the MIDI2LR project. Please don't report problems with it on the upstream issue tracker.
