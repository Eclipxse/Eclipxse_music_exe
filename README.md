<div align="center">
  <img src="assets/eclipxse_music_hero.png" alt="Eclipxse Music artwork" width="100%">

  <br>
  <sub>THE WINDOWS ARCHIVE // RELEASE 10.2.0</sub>
  <h1>Eclipxse Music</h1>
  <p>A focused desktop music client for Windows.</p>

  <p>
    <a href="https://github.com/Eclipxse/Eclipxse_music_exe/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/Eclipxse/Eclipxse_music_exe?style=flat-square&label=release&color=18181b"></a>
    <img alt="Windows x64" src="https://img.shields.io/badge/Windows-x64-27272a?style=flat-square&logo=windows11&logoColor=white">
    <img alt="Flutter 3.44.5" src="https://img.shields.io/badge/Flutter-3.44.5-27272a?style=flat-square&logo=flutter&logoColor=white">
    <img alt="MediaKit and libmpv" src="https://img.shields.io/badge/audio-MediaKit%20%2F%20libmpv-7f1d1d?style=flat-square">
    <a href="LICENSE"><img alt="GPL v3" src="https://img.shields.io/badge/license-GPLv3-18181b?style=flat-square"></a>
  </p>

  <p>
    <a href="#download">Download</a>&nbsp;&nbsp;/&nbsp;&nbsp;
    <a href="#desktop-system">Desktop system</a>&nbsp;&nbsp;/&nbsp;&nbsp;
    <a href="#controls">Controls</a>&nbsp;&nbsp;/&nbsp;&nbsp;
    <a href="#diagnostics">Diagnostics</a>
  </p>
</div>

---

Eclipxse Music is a personal Windows build of the open-source Musify client. It pairs a quiet desktop workflow with a custom visual identity, resilient streaming, local audio support, and native Windows controls.

This repository contains the ready-to-run Windows x64 distribution. The corresponding source archive is attached to every release.

## Download

<table>
  <tr>
    <td width="50%">
      <strong>Windows installer</strong><br>
      Recommended for regular use.<br><br>
      Per-user installation, Start menu entry, clean uninstall, and support for automatic upgrades.<br><br>
      <a href="https://github.com/Eclipxse/Eclipxse_music_exe/releases/download/v10.2.0/Eclipxse-Music-Setup-10.2.0.exe"><strong>Download setup</strong></a>
    </td>
    <td width="50%">
      <strong>Portable archive</strong><br>
      No installation required.<br><br>
      Extract the complete ZIP and keep the executable, DLL files, and <code>data</code> directory together.<br><br>
      <a href="https://github.com/Eclipxse/Eclipxse_music_exe/releases/download/v10.2.0/Eclipxse-Music-Windows-x64-10.2.0.zip"><strong>Download portable ZIP</strong></a>
    </td>
  </tr>
</table>

> [!NOTE]
> The application is not code-signed. Microsoft Defender SmartScreen may display a warning on first launch. Verify the published SHA-256 checksum before choosing **More info > Run anyway**.

## Desktop System

| Playback | Windows integration | Library |
| --- | --- | --- |
| MediaKit and libmpv backend | Compact always-on-top player | Search and discovery |
| Fresh stream resolution | System tray controls | Favorites and playlists |
| Alternate-codec recovery | Hardware media keys | Queue and listening history |
| Eight-band equalizer | Close or minimize to tray | Lyrics and listening recap |
| Output-device selection | Optional launch at startup | Validated offline downloads |
| Loudness normalization | Optional Discord presence | Local audio files |

### Playback Reliability

The Windows playback path resolves a fresh audio stream for each session, prefers AAC where available, and retries with an alternate Opus stream when startup stalls. A playback watchdog exposes a clear retry action instead of leaving the player in an indefinite loading state.

Offline downloads are written to temporary partial files, validated, and moved into the library only after completion.

### Local Audio

Drop audio files anywhere on the app or use the file picker. Supported formats:

```text
AAC  FLAC  M4A  MP3  OGG  OPUS  WAV  WEBM
```

## Controls

| Action | Shortcut |
| --- | --- |
| Open local music | `Ctrl+O` |
| Toggle compact player | `Ctrl+Shift+M` |
| Play or pause | `Ctrl+Space` |
| Previous track | `Ctrl+Alt+Left` |
| Next track | `Ctrl+Alt+Right` |

Songs also expose their full action menu on right-click. Global hardware media keys can be enabled or disabled under **Settings > Windows desktop**.

## Audio Tools

Open **Settings > Audio > Windows audio** to access:

- Playback-device selection and refresh
- Eight independently adjustable frequency bands
- Flat, Bass, Vocal, Air, and Night presets
- Loudness normalization through native libmpv filters
- Configurable smooth track transitions

## Diagnostics

Open **Settings > Windows desktop > Diagnostics** to inspect the active track, processing state, timing, buffer, output device, and latest playback issue.

The diagnostics view can retry playback, refresh output devices, repair incomplete offline entries, copy a system report, and open or clear the persistent log.

```text
%LOCALAPPDATA%\Eclipxse Music\playback.log
```

## Release Record

| Field | Value |
| --- | --- |
| Application | `Eclipxse Music 10.2.0+187` |
| Platform | `Windows 10/11 x64` |
| Flutter | `3.44.5 stable` |
| Audio engine | `MediaKit / libmpv` |
| Installer | `Inno Setup 6.7.3` |
| Validation | Clean build, portable launch, install, launch, uninstall |

### SHA-256

```text
F60ADA9CD4D7DF95BE0D935378F7D81A6F2DD611C8FF9E7D731DE0B08739742D  Eclipxse-Music-Setup-10.2.0.exe
2930769B815E959AEFC7ED39E03867128865D9FC286774E3914E00AD0126BC14  Eclipxse-Music-Windows-x64-10.2.0.zip
1F81AF773D46A4361C1340477FD85C6E10768446D3E08D528D5D539000CB4C84  Eclipxse-Music-Source-10.2.0.zip
```

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

The executable is not standalone. The `data` directory and bundled DLL files are required at runtime.

## Source And License

Eclipxse Music is a modified build of [gokadzev/Musify](https://github.com/gokadzev/Musify), created by Valeri Gokadze and its contributors. The customized development repository is maintained at `Eclipxse/Eclipxse_music`, and a corresponding source ZIP is included with each public binary release.

The project remains free software under the [GNU General Public License v3.0](LICENSE). Flutter and package-specific notices are bundled at `data/flutter_assets/NOTICES.Z`.

The application does not host or own third-party music. Availability depends on external services, local files, network conditions, and regional access. Users are responsible for complying with applicable law and service terms.

---

<div align="center">
  <img src="assets/eclipxse_music_emblem.png" alt="Eclipxse Music emblem" width="190">
  <br>
  <sub>ECLIPXSE MUSIC // WINDOWS ARCHIVE 10.2.0</sub>
</div>
