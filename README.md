# 🏐 DV Live Video

**DV Live Video** is a professional desktop application for real‑time volleyball rally analysis. It combines live video capture (partial MP4 or HTTP stream) with DataVolley scout files (`.dvw`) to provide an interactive web interface with powerful filters, statistics, and HLS streaming to any device on your local network.

- **Other Languages**: README [Português Brasileiro](readme.ptbr.md)

- **Manual**: EN [English](manual.md)
- **Manual**: PT-BR [Português Brasileiro](manual.ptbr.md)

---

## Features

- **Real‑time rally list** – Updated automatically when the scout file changes.
- **Powerful filters** – By set, home/away rotation, attack phase, evaluation code, favorites, and wildcard search (`_`).
- **Interactive statistics** – Detailed tables with counts by skill (Serve, Reception, Attack, Block, Dig, Set) and evaluation codes (`# + ! - / =`). Player names are shown alongside numbers.
- **Live HLS streaming** – The video is converted to HLS and served to any browser on the network. Supports seeking back (DVR) when using a compatible source.
- **Desktop + Web** – Choose to run only the desktop interface, only the web server, or both.
- **Remote scout file** – Read `.dvw` directly from an HTTP URL (e.g., DataVolley’s built‑in server on port 7474).
- **Firewall auto‑configuration** – On first run, the app can ask to open port 5000 in Windows Firewall.
- **Keyboard shortcuts** – Space (play/pause), arrows (±2s), F (favorite), Enter (jump to selected rally), and more.
- **Theme** – Light/dark mode for the web interface (persistent).
- **Last 6 serves** – Dynamic buttons showing the most recent serves with score and short code.

---

## Download

Go to the **[Releases](../../releases)** page and download the latest `DVLiveVideo.exe`.

> **Note:** The release package also includes `ffmpeg.exe` and the required `templates` folder. Extract everything to the same directory.

---

## Requirements

- **Windows 10 / 11** (64‑bit)
- **VLC Media Player** installed ([download here](https://www.videolan.org/vlc/))
- The provided `ffmpeg.exe` (included in the release)

---

## Quick Start

1. **Extract** the release archive to a folder (e.g., `C:\DVLiveVideo`).
2. **Install VLC** if you haven’t already.
3. **Run** `DVLiveVideo.exe`.
4. Choose your execution mode.
5. Select your video source.
6. Start scouting! The web interface will be available at `http://localhost:5000` (or your computer’s IP address).

> **Testing without a match?** Use any `.mp4` + `.dvw`.

---

##  Built With

- **Python 3.14** – Core logic
- **PyQt5** – Desktop interface
- **VLC (python‑vlc)** – Video playback
- **FFmpeg** – HLS streaming generation
- **Flask + Socket.IO** – Web server and real‑time updates
- **pandas** – Data manipulation
- [**openvolley/py-datavolley**](https://github.com/openvolley/py-datavolley) – DataVolley `.dvw` parser

---

## Documentation

The web interface includes:
- **User Manual** – `http://localhost:5000/manual`
- **Changelog** – `http://localhost:5000/changelog`
- **Resources & Credits** – `http://localhost:5000/resources`

---

## Contributing

This project is distributed as a compiled executable. If you are a developer and wish to contribute to the source code, please contact the author.

---

## Contact

Developed by **Felipe Lima (Ori)** – [@felipeaplima]

---

## License

All rights reserved. This software is provided “as is” without warranty. Redistribution is not permitted without explicit permission from the author.
