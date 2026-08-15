# beam-player — release artifacts

Binary releases for the Beam media player. **Source is not here** — it lives in
the private [`Beam-Studio/beam-mediaplayer`](https://github.com/Beam-Studio/beam-mediaplayer)
repository. This repo only carries downloadable builds.

## Downloads

Grab the newest files from [**Releases**](../../releases).

### Android (`beam-player-android-*.apk`)

- Release build (not debuggable), `minSdk 24` / `targetSdk 35`, arm64-v8a
- Signed with our debug/distribution certificate — side-load install:
  `adb install -r beam-player-android-*.apk`, or open the APK on-device and
  allow "install unknown apps" for your file manager

### macOS (`BeamMacHost-macOS-arm64-*.zip`)

- Apple Silicon (arm64), macOS 13+
- Ad-hoc signed (no Developer ID). Browsers add quarantine on download, so on
  first launch: right-click the app → **Open** → **Open** (or
  `xattr -dr com.apple.quarantine BeamMacHost.app`)
- Contains the rust `beam-dsp` P3 chain (Mode A clear content only)

## What this player does

Mode A (clear HTTP/HLS progressive) playback with the Beam DSP chain, playlist
support, and visualization. DRM / protected streams use the platform stacks
with Beam chrome only — no DSP taps, per the Beam mode rules.
