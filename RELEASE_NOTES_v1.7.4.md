# Media Renamer v1.7.4

**Open source (MIT):** https://github.com/Manza22/Media-Renamer-for-Jellyfin

Anyone may use, modify, and redistribute this software under the MIT License. Please do not repackage it as malware or deceptive installers—the authors only endorse builds from this repository or clearly labeled forks.

## Download

| Asset | Description |
|-------|-------------|
| `MediaRenamer_Portable_*.zip` | Extract and run `MediaRenamer.exe` |
| `MediaRenamer_Setup_*.zip` | Optional Windows installer |
| `media_renamer.py` | Run from source with Python 3.10+ |

## Requirements

- Windows 10/11 (for `.exe`) or Python from source
- Free TMDB API key: https://www.themoviedb.org/settings/api

## Highlights

- Flat-season remapping for “everything is S01” download packs
- Dry run, undo, genre folders, Episode Browser
- Windows-safe filenames (`:` in TMDB titles → ` -`)
- Jellyfin path notify, ID cache fixes, export unmatched CSV

## Trust

- Full source in the repo; no telemetry
- PyInstaller exes may trigger Defender false positives—run from source or use VirusTotal if unsure

## Docs

- [README](https://github.com/Manza22/Media-Renamer-for-Jellyfin/blob/main/README.md)
- [DISCLAIMER](https://github.com/Manza22/Media-Renamer-for-Jellyfin/blob/main/DISCLAIMER.md)
- [PRIVACY](https://github.com/Manza22/Media-Renamer-for-Jellyfin/blob/main/PRIVACY.md)

This product uses the TMDB API but is not endorsed or certified by TMDB.
