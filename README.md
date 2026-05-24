# Media Renamer for Jellyfin

**Free and open source** (MIT). Rename movies and TV shows using [TMDB](https://www.themoviedb.org/) into paths and filenames Jellyfin understands.

**Version:** 1.7.4

![Main window](docs/screenshot-main.png)

## Open source â€” what you may do

This project is released under the **[MIT License](LICENSE)**. That means you are free to:

- Use it for any purpose (personal, homelab, commercial tooling you operate yourself)
- Study and modify the source code
- Fork the repo and publish your own version
- Include it in other projects (keep the MIT copyright notice)

**Please use it responsibly.** This tool is meant to **organize your own media library** with files you have the right to use. Do **not** bundle, modify, or distribute this softwareâ€”or derivatives of itâ€”as **malware, spyware, ransomware**, or anything designed to harm users, steal data, or run without informed consent. The authors do not support or endorse malicious use.

If you redistribute a modified build, we ask that you:

- Keep the MIT license and credit
- Use a **different project name** if your fork behaves substantially differently
- Be honest that your build is a fork (not the official â€œMedia Renamerâ€)

## Download

| What | Where |
|------|--------|
| **Latest release** | [GitHub Releases](https://github.com/Manza22/Media-Renamer-for-Jellyfin/releases) |
| **Source code** | This repository â€” run `python media_renamer.py` |

Pre-built `.exe` files are optional conveniences built from this source with PyInstaller. If you do not trust binaries, **run from source**.

## Features

- **Scan & preview** â€” dry run by default; nothing moves until you apply
- **Movies** â€” `Title (Year).mp4`; optional copy into genre subfolders
- **TV shows** â€” `Show - S##E## - Episode Title.mp4` under `Show Name/Season XX/`
- **Flat-season remap** â€” when a download site labels everything `S01`, map episodes to the correct TMDB seasons
- **Episode Browser** â€” batch-rename a full folder
- **Undo**, manual TMDB picker, ID cache, export unmatched CSV
- Optional **Jellyfin** library scan after apply
- **Windows/macOS-safe filenames** â€” e.g. `Avengers: Endgame` â†’ `Avengers - Endgame` (see [Filename fix](#filename-fix-v174) below)

## Filename fix (v1.7.4)

TMDB titles often include colons (e.g. `Avengers: Endgame`). Colons are **not allowed** in file names on Windows or macOS.

The `sanitize()` function in `media_renamer.py` replaces `:` with ` -` and strips other illegal characters (`<>"/\|?*`):

| TMDB title | Output filename |
|------------|-----------------|
| `Avengers: Endgame` | `Avengers - Endgame (2019).mkv` |
| `Dragon Ball Super: Broly` | `Dragon Ball Super - Broly (2018).mkv` |

Reported via [r/jellyfin community feedback](https://www.reddit.com/r/jellyfin/comments/1tlp5vf/).

## Requirements

- **Windows 10/11** for the packaged `.exe`, or **Python 3.10+** from source
- Free [TMDB API key](https://www.themoviedb.org/settings/api)
- Media files you are allowed to possess and organize

## Run from source

```powershell
git clone https://github.com/Manza22/Media-Renamer-for-Jellyfin.git
cd Media-Renamer-for-Jellyfin
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python media_renamer.py
```

Or double-click **`run.bat`** (Windows).

## Project layout

| File | Purpose |
|------|---------|
| `media_renamer.py` | Main application |
| `friendly_errors.py` | User-facing errors |
| `requirements.txt` | Python dependencies |
| `LICENSE` | MIT â€” open source terms |
| `PRIVACY.md` | What stays on your PC |
| `DISCLAIMER.md` | Intended use & liability |

## Configuration (local only)

| File | Purpose |
|------|---------|
| `~/.media_renamer_config.json` | API key, folders, options |
| `~/.media_renamer_id_cache.json` | TMDB ID cache |
| `~/.media_renamer_history.json` | Undo history |
| `~/.media_renamer.log` | Local diagnostic log |

No analytics or telemetry are built into this app. See [PRIVACY.md](PRIVACY.md).

## Antivirus / PyInstaller

Windows Defender sometimes flags PyInstaller executables as suspicious. That is a known false-positive pattern. Verify the [source](https://github.com/Manza22/Media-Renamer-for-Jellyfin) or scan the file on [VirusTotal](https://www.virustotal.com/).

## Contributing

Issues and pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Third-party notices

- [The Movie Database (TMDB)](https://www.themoviedb.org/) â€” metadata. This product uses the TMDB API but is **not endorsed or certified by TMDB**.
- [Jellyfin](https://jellyfin.org/) â€” **not affiliated**. Naming conventions target Jellyfin-style libraries.

## Disclaimer

This software renames and moves files on your computer. **Always use dry run first** and keep backups. The authors are not liable for lost or misnamed files. You must comply with TMDBâ€™s terms and your local laws regarding your media.

Full text: [DISCLAIMER.md](DISCLAIMER.md)
