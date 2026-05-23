# 🎬 Media Renamer for Jellyfin

> Automatically rename your movies, TV shows, and anime — perfectly formatted for Jellyfin — powered by TMDB.

## What it does

Media Renamer scans a folder of video files, looks them up on [The Movie Database (TMDB)](https://www.themoviedb.org/), and renames them into the exact format Jellyfin expects — including genre routing, TV season folders, and episode titles.

**Before:**

```
dragon.ball.super.broly.2018.1080p.bluray.x264.mkv
The.Office.S03\\\_E19\\\_HDTV.avi
\\\\\_123\\\_xyz\\\_Inception\\\_2010\\\_WEBRip.mp4
```

**After:**

```
Movies/Action/Dragon Ball Super: Broly (2018).mkv
TV Shows/The Office/Season 03/The Office - S03E19 - Stress Relief.avi
Movies/Sci-Fi/Inception (2010).mp4
```

\---

## Features

* 🔍 **Auto-match** movies and TV shows via TMDB with confidence scoring
* 📺 **Full TV support** — season folders, episode titles, season remapping for bad scene releases
* 🗂️ **Genre routing** — automatically sorts movies into your genre subfolders (Action, Sci-Fi, Romance…)
* 📋 **Manual picker** — low-confidence matches show a dialog with poster images so you can verify
* 🔎 **Search panel** — click any row and instantly search TMDB to override the match
* 📡 **Jellyfin integration** — triggers a library scan automatically after renaming
* ↩️ **Undo system** — full rename history, batch undo at any time
* 📂 **Episode Browser** — drag-and-drop style TV episode assignment with flat-season remapping
* 💾 **ID cache** — files you've matched before are instant on next scan
* 🖼️ **Poster previews** — TMDB poster thumbnails in both the search and scan list
* 📄 **Export unmatched** — save a CSV of anything that didn't match for manual review
* 🗑️ **Dry run mode** — preview every change before anything moves

\---

## Download

## USE THE SETUP EXE OR PORTABLE---

## Getting Started

### 1\. Get a free TMDB API key

1. Create a free account at [themoviedb.org](https://www.themoviedb.org/)
2. Go to **Settings → API → Request an API key** (choose Developer / Personal)
3. Copy the **API Key (v3 auth)**

The app will walk you through this on first launch.

### 2\. Set your folders

|Field|What to put here|
|-|-|
|**Media Folder**|The folder with your unorganized video files|
|**Server**|Your media library root (e.g. `\\\\\\\\192.168.1.10\\\\Media`)|
|**Movies Folder**|Where renamed movies should go|
|**TV Shows Folder**|Where renamed TV episodes should go|

Genre subfolders (e.g. `Action`, `Sci-Fi`, `Romance`) inside your Movies folder are detected automatically.

### 3\. Scan \& Apply

1. Click **🔍 Scan \& Preview** — all files are matched and listed
2. Review the results. Click any row to search TMDB and override if needed
3. When happy, uncheck **Preview only** and click **✅ Apply Renames**

\---

## Jellyfin Integration (optional)

Enter your Jellyfin server URL and API key in the settings panel. After applying renames, Media Renamer will automatically notify Jellyfin to scan the updated paths.

* **Server URL:** `http://192.168.1.10:8096` or `https://your-domain.com/jellyfin`
* **API key:** Jellyfin Dashboard → API Keys → create a key with admin access

\---

## Antivirus Warning

Windows Defender and other antivirus tools sometimes flag `.exe` files built with PyInstaller as suspicious — **this is a false positive.** The source code is fully available in this repo for review.

If you're unsure, you can scan the exe at [VirusTotal](https://www.virustotal.com/) before running.

\---

## Known Limitations

* Windows only (for now)
* Requires an internet connection for TMDB lookups
* Very large libraries (1000+ files) may take a few minutes to scan

\---

## Changelog

### v1.7.4

* Flat-season remapping: files labeled S01E19 correctly route to the right TMDB season
* UI search panel: Load more / pagination for deep TMDB results
* Jellyfin path notify (targeted scan instead of full library refresh)
* Picker timeout with auto-fallback to best guess
* Genre routing priority (Spider-Man goes to Action, not Sci-Fi)
* Improved title scoring: token overlap + sequence ratio combined
* ID cache now uses full normalized paths (no more stale basename collisions)
* Dry run mode with full op plan preview
* Export unmatched files to CSV

\---

## License

© 2024 Manza. All rights reserved.

This software is provided as-is for personal use. You may not redistribute, sell, modify, or use this software as the basis for another product without explicit written permission from the author.

\---

*This product uses the TMDB API but is not endorsed or certified by TMDB.*

