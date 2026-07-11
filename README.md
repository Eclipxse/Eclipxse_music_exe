<div align="center">
  <img src="assets/eclipxse_music_hero.png" alt="Eclipxse Music gothic angel artwork" width="100%">

  <h1>Eclipxse Music for Windows</h1>

  <p><strong>A personal desktop music experience with a dark angelic identity.</strong></p>

  <p>
    <a href="https://github.com/Eclipxse/Eclipxse_music_exe/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/Eclipxse/Eclipxse_music_exe?style=flat-square&color=8db7ff"></a>
    <img alt="Windows x64" src="https://img.shields.io/badge/Windows-x64-0078D4?style=flat-square&logo=windows11&logoColor=white">
    <img alt="Flutter 3.44.5" src="https://img.shields.io/badge/Flutter-3.44.5-02569B?style=flat-square&logo=flutter&logoColor=white">
    <a href="LICENSE"><img alt="GPL v3 license" src="https://img.shields.io/badge/License-GPLv3-4f67a1?style=flat-square"></a>
  </p>

  <p>
    <a href="https://github.com/Eclipxse/Eclipxse_music_exe/releases/latest"><strong>Download the latest Windows release</strong></a>
  </p>
</div>

---

## Overview

Eclipxse Music is a customized desktop music player for Windows. It combines online music discovery, queue and library management, background playback, lyrics, offline listening tools, and listening history inside a smooth gothic-inspired interface.

This repository is the ready-to-run **Windows x64 distribution**. It intentionally contains the compiled application rather than the Flutter development project.

## Features

- Online song search with suggestions
- Smooth background audio playback powered by MediaKit and libmpv
- Queue controls, shuffle, repeat, and playback history
- Favorites, playlists, and library management
- Lyrics and listening recap views
- Offline music support
- No in-app advertising interface
- Custom Eclipxse artwork, icon, and dark visual identity
- Persistent playback diagnostics for easier troubleshooting

## Install

1. Open the [latest release](https://github.com/Eclipxse/Eclipxse_music_exe/releases/latest).
2. Download `Eclipxse-Music-Windows-v10.1.11.zip`.
3. Extract the **entire** ZIP to a normal folder.
4. Run `Eclipxse Music.exe`.

> [!IMPORTANT]
> Keep the EXE, DLL files, and `data` folder together. The EXE is only the launcher and will not work by itself.

No Flutter SDK, Visual Studio, installer, or additional runtime setup is required to use the packaged application.

## Build Information

| Item | Value |
| --- | --- |
| App version | `10.1.11+186` |
| Target | Windows x64 release |
| Flutter | `3.44.5` stable |
| Audio backend | MediaKit / libmpv |
| Package type | Portable application |
| Tested environment | Windows 11 |

Version `10.1.11` includes the Windows playback correction that removes Android-only audio effects from the desktop player and starts streams without the invalid whole-track timeout used by the previous build.

## Package Layout

```text
Eclipxse Music.exe
flutter_windows.dll
libmpv-2.dll
media_kit_libs_windows_audio_plugin.dll
app_links_plugin.dll
dartjni.dll
dynamic_color_plugin.dll
share_plus_plugin.dll
url_launcher_windows_plugin.dll
data/
```

The `data` directory contains the compiled Dart application, Flutter assets, fonts, shaders, artwork, and third-party notices required at runtime.

## Verify the Download

Release archive SHA-256:

```text
CD4769AC46F9354F436373D8BD56118181B2294A5B9DAE481237529AE2DD468B
```

Verify it in PowerShell:

```powershell
Get-FileHash ".\Eclipxse-Music-Windows-v10.1.11.zip" -Algorithm SHA256
```

## Troubleshooting

### Windows protected your PC

This portable build is not code-signed, so Microsoft Defender SmartScreen may show a warning. Confirm that the archive came from this repository, choose **More info**, and then choose **Run anyway**.

### A DLL is missing

Extract the complete archive again. Do not copy only `Eclipxse Music.exe` to the desktop, and do not launch it from inside the ZIP preview.

### A song remains on loading

Close every older Eclipxse Music window before opening the latest build. Confirm that the computer is online and that a firewall is not blocking the application. Playback diagnostics are written to:

```text
%LOCALAPPDATA%\Eclipxse Music\playback.log
```

### The app does not open

Move the extracted folder to a writable location such as `Documents` or `Desktop`, then launch the EXE again. Avoid running it from a temporary archive folder.

## Source and Credits

The customized Flutter source is maintained in [Eclipxse/Eclipxse_music](https://github.com/Eclipxse/Eclipxse_music). This project is based on [Musify](https://github.com/gokadzev/Musify) by Valeri Gokadze and its contributors.

Eclipxse Music remains free software under the **GNU General Public License v3.0**. See [LICENSE](LICENSE). This binary repository does not replace the corresponding source-code distribution required by the GPL; anyone distributing the binaries is responsible for making the corresponding source available to recipients under the same license.

Third-party notices bundled by Flutter are included at `data/flutter_assets/NOTICES.Z`.

## Disclaimer

Eclipxse Music does not host or own music. Search results, metadata, artwork, and audio availability depend on external services. All music, trademarks, and related rights belong to their respective owners. Users are responsible for complying with applicable laws and the terms of the services they access.

---

<div align="center">
  <img src="assets/eclipxse_music_emblem.png" alt="Eclipxse Music emblem" width="220">
  <p><strong>Eclipxse Music</strong><br>Windows archive 10.1.11</p>
</div>
