# 🏐 DV Live Video

**DV Live Video** is a professional desktop application for real‑time volleyball rally analysis. It combines live video capture (partial MP4 or HTTP stream) with DataVolley scout files (`.dvw`) to provide an interactive web interface with powerful filters, statistics, and HLS streaming to any device on your local network.

**Documents**: 

- README [Português Brasileiro](readme.ptbr.md)

**Manual**: 

- [English (US)](manual.md)
- [Português Brasileiro (PT-BR)](manual.ptbr.md)

---

## Screenshots

### Desktop Interface
![Desktop App](./docs/images/screenshot1.png)

### Web Interface (Mobile)
![Web Player](./docs/images/screenshot2.jpg)


---

## Features

- **Real‑time rally list** – Updated automatically when the scout file changes.
- **Powerful filters** – By set, home/away rotation, favorites, and wildcard search (`_`).
- **Interactive statistics** – Detailed tables with counts by skill (Serve, Reception, Attack, Block, Dig, Set) and evaluation codes (`# + ! - / =`). 
- **Desktop + Web** – Choose to run only the desktop interface, only the web server, or both.
- **Keyboard shortcuts** – Space (play/pause), arrows (±2s), F (favorite), Enter (jump to selected rally), and more.
- **Last serves shortcut** – Dynamic buttons showing the most recent serves with score and short code.

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