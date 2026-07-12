<div align="center">
  <img src="assets/eclipxse_music_hero.png" alt="Eclipxse Music gothic angel artwork" width="100%">

  <h1>Eclipxse Music for Windows</h1>
  <p><strong>A smooth personal music client with a gothic angelic identity.</strong></p>

  <p>
    <a href="https://github.com/Eclipxse/Eclipxse_music_exe/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/Eclipxse/Eclipxse_music_exe?style=flat-square&color=9CC4FF"></a>
    <img alt="Windows x64" src="https://img.shields.io/badge/Windows-x64-0078D4?style=flat-square&logo=windows11&logoColor=white">
    <img alt="Flutter" src="https://img.shields.io/badge/Flutter-3.44.5-02569B?style=flat-square&logo=flutter&logoColor=white">
    <a href="LICENSE"><img alt="GPL v3 license" src="https://img.shields.io/badge/license-GPLv3-4C8CBF?style=flat-square"></a>
  </p>

  <p>
    <a href="https://github.com/Eclipxse/Eclipxse_music_exe/releases/latest"><strong>Download Eclipxse Music 10.2.0</strong></a>
  </p>
</div>

## Download

Open the [latest release](https://github.com/Eclipxse/Eclipxse_music_exe/releases/latest) and choose one package:

| Package | Best for |
| --- | --- |
| `Eclipxse-Music-Setup-10.2.0.exe` | Recommended. Installs per-user, adds Start menu and uninstall entries, and supports automatic upgrades. |
| `Eclipxse-Music-Windows-x64-10.2.0.zip` | Portable use. Extract the complete archive and keep every file together. |

The app is not code-signed, so Microsoft Defender SmartScreen may show **Windows protected your PC**. Verify the SHA-256 checksum, choose **More info**, and then choose **Run anyway**.

## What Is New In 10.2

- Rebuilt Windows playback path with fresh stream resolution and automatic alternate-codec recovery
- Native MediaKit/libmpv output-device selection, eight-band equalizer, presets, and loudness normalization
- Playback watchdog and visible retry state instead of an endless loading spinner
- Compact always-on-top mini player with smooth track transitions
- System tray controls, close/minimize-to-tray settings, saved window bounds, and optional startup launch
- Native global play/pause, previous, and next hardware media keys
- Drag-and-drop and file-picker support for local audio
- Right-click song actions and desktop keyboard shortcuts
- Optional Discord Rich Presence
- Windows diagnostics, persistent logs, output inspection, and offline-library repair
- GitHub release updater with installer handoff

## Core Features

- Online catalogue browsing and search suggestions
- Queue, shuffle, repeat, favorites, playlists, and listening history
- Lyrics, sleep timer, playback speed, and listening recaps
- Offline downloads with partial-file validation
- Custom Eclipxse artwork, application icon, and dark visual identity
- Background playback through MediaKit and libmpv

## Desktop Shortcuts

| Action | Shortcut |
| --- | --- |
| Open local music | `Ctrl+O` |
| Toggle mini player | `Ctrl+Shift+M` |
| Play or pause | `Ctrl+Space` |
| Previous track | `Ctrl+Alt+Left` |
| Next track | `Ctrl+Alt+Right` |

Hardware media keys can be enabled or disabled under **Settings > Windows desktop**.

## Portable Package

1. Download `Eclipxse-Music-Windows-x64-10.2.0.zip`.
2. Extract the whole archive to a normal folder.
3. Run `Eclipxse Music.exe`.

> [!IMPORTANT]
> The EXE is not standalone. Keep `Eclipxse Music.exe`, every DLL, and the `data` directory together.

No Flutter SDK or Visual Studio installation is required to run a packaged release.

## Build Information

| Item | Value |
| --- | --- |
| App version | `10.2.0+187` |
| Target | Windows 10/11 x64 |
| Flutter | `3.44.5` stable |
| Audio backend | MediaKit / libmpv |
| Installer | Inno Setup 6.7.3, per-user |
| Tested | Clean build, portable launch, installer launch, and uninstall on Windows 11 |

## Verify Downloads

```text
F60ADA9CD4D7DF95BE0D935378F7D81A6F2DD611C8FF9E7D731DE0B08739742D  Eclipxse-Music-Setup-10.2.0.exe
2930769B815E959AEFC7ED39E03867128865D9FC286774E3914E00AD0126BC14  Eclipxse-Music-Windows-x64-10.2.0.zip
1F81AF773D46A4361C1340477FD85C6E10768446D3E08D528D5D539000CB4C84  Eclipxse-Music-Source-10.2.0.zip
```

Verify a file in PowerShell:

```powershell
Get-FileHash ".\Eclipxse-Music-Setup-10.2.0.exe" -Algorithm SHA256
```

## Package Layout

```text
Eclipxse Music.exe
flutter_windows.dll
libmpv-2.dll
media_kit_libs_windows_audio_plugin.dll
desktop_drop_plugin.dll
screen_retriever_windows_plugin.dll
tray_manager_plugin.dll
window_manager_plugin.dll
data/
```

The `data` directory contains the compiled Dart application, artwork, fonts, shaders, and third-party notices required at runtime.

## Troubleshooting

### A song keeps loading

Open **Settings > Windows desktop > Diagnostics**, then use **Retry playback** or **Repair offline library**. Confirm that the computer is online and that a firewall is not blocking the application.

Persistent playback logs are stored at:

```text
%LOCALAPPDATA%\Eclipxse Music\playback.log
```

### A DLL is missing

For the portable build, extract the entire ZIP again. Do not launch the EXE from inside the archive preview or move only the EXE to the desktop.

### Playback uses the wrong speakers

Open **Settings > Audio > Windows audio**, refresh devices, and select the intended output.

## Source, Credits, And License

Eclipxse Music is a modified build of [gokadzev/Musify](https://github.com/gokadzev/Musify), created by Valeri Gokadze and its contributors. The customized development repository is maintained at `Eclipxse/Eclipxse_music`; each binary release also includes its corresponding source archive.

The project remains free software under the [GNU General Public License v3.0](LICENSE). Third-party notices bundled by Flutter are available at `data/flutter_assets/NOTICES.Z`.

## Disclaimer

Eclipxse Music does not host or own third-party music. Search results, metadata, artwork, and audio availability depend on external services, local files, network conditions, and regional access. Users are responsible for complying with applicable law and service terms.

---

<div align="center">
  <img src="assets/eclipxse_music_emblem.png" alt="Eclipxse Music emblem" width="220">
  <p><strong>Eclipxse Music</strong><br>Windows archive 10.2.0</p>
</div>
