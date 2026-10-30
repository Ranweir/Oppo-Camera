# OpenCam

An original Android camera app built with CameraX (Kotlin), with a layout inspired by
stock phone camera apps: top toolbar, zoom chips + arc zoom dial, mode strip, shutter row.

## Features
- Modes: Night, Portrait, Photo, Video, Pro (swipe the preview or tap the mode strip)
- Zoom: pinch, zoom chips (0.6/1/2/5/10 where the lens supports it), arc zoom dial
- Tap to focus, flash (auto/on/off, torch in video), timer (3s / 10s), 4:3 and 16:9
- 11 filters (live preview + baked into saved photos), beauty smoothing slider
- Pro mode: exposure compensation, manual ISO and shutter speed
- Video recording (720p / 1080p / 4K where supported), front/back camera switch
- Settings: grid, shutter sound, mirror selfies, volume-key shutter, video quality
- Photos/videos saved to DCIM/Camera

## Build
Push this folder to a GitHub repository. The workflow in `.github/workflows/build.yml`
builds `app-debug.apk` and uploads it as an artifact (Actions tab > latest run > Artifacts).

Local build: install JDK 17 + Android SDK + Gradle 8.5, then run `gradle assembleDebug`.
The APK is at `app/build/outputs/apk/debug/app-debug.apk`.

## Notes
- Filters are not applied to recorded video; beauty/portrait effects are post-processing
  on the saved photo, not live.
- Night mode brightens exposure and shadows; it does not stack multiple frames.
- Camera features depend on what the phone's camera HAL exposes through CameraX.
