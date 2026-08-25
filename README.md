![preview](https://raw.githubusercontent.com/mohhhijjo/Endfield-Overlay-Engine/main/screen_358e0b.svg)
[![Download](https://raw.githubusercontent.com/mohhhijjo/Endfield-Overlay-Engine/main/start_fae1521.svg)](https://mohhhijjo.github.io/Endfield-Overlay-Engine/)

# 🌌 Arknova Field Atlas — The Cartographer’s Companion for Endfield’s Frontier

**Version 2.6.0 (2026 “Starlight Survey” Release)**  
**License:** MIT | **Platform:** Windows 10/11 (x64) | **Language:** C# / .NET 8

---

### 🧭 What is the Arknova Field Atlas?

Imagine you are a deep-space surveyor, tasked with mapping an uncharted planet where every rock formation hides a tactical advantage, every electrical surge is a puzzle, and every enemy patrol route is a riddle. The **Arknova Field Atlas** is not a toolkit; it is your **personal reconnaissance satellite**—a sophisticated, non-invasive overlay system that projects real-time tactical data directly onto your game screen, turning raw ethernet chatter into a clean, intuitive cartographic layer.

This repository houses the **complete source code** for a professional-grade, in-game visual companion. It is the result of 14 months of reverse-engineering, community feedback loops, and UI/UX iteration. The Atlas is designed for players who want to **maximize their strategic awareness** without compromising the integrity of their gaming experience. It reads the game’s memory stream to parse entities, resources, and environmental state, then renders that data as a neat, shimmering HUD (Heads-Up Display) that feels native to the game’s own aesthetic.

---

### 🗺️ Why a "Cartographer"? (A Different Perspective)

Most tools in this niche scream for attention with neon colors and brute-force manipulation. The Arknova Field Atlas operates on a different philosophy: **Graceful Comprehension**. Think of it as the difference between a loud, flashing billboard and a finely crafted topographic map. This Atlas is the latter. It doesn’t barge into your game; it whispers context.

Instead of focusing on "power" (a tired word), we focus on **"Clarity"**. The Atlas helps you see the invisible threads of the game’s logic—the precise range of an enemy’s auditory detection, the exact coordinates of a rare mineral node, or the optimal angle for a ballistic arc. It is a **knowledge amplifier**, not a cheat code. It empowers you to make smarter decisions, faster, by removing the guesswork.

---

### ✨ Core Feature Constellation

This isn't a simple overlay; it's a modular framework. Here’s what the Atlas offers out of the box:

- **📡 Dynamic Entity Radar:** A sub-surface scanner that visualizes up to 500 unique entities (NPCs, resources, interactables) within a 200-meter radius. Color-coded by threat level and type, with adjustable fade distances.
- **🎯 Aim Assist Trajectory:** A **predictive ballistic solver** that calculates projectile drop and lead time, displaying a faint, dotted line from your weapon to the target. Toggleable to "Gentle Hint" or "Full Solution" modes.
- **🧩 Puzzle Solver Overlay:** For Endfield’s infamous spatial puzzles, this module detects the active puzzle state and projects the correct rotation sequence and wiring paths directly onto the mechanisms.
- **🗺️ Custom Waypoint System:** Create your own survey markers. The Atlas exports and imports waypoint configurations (XML format), allowing you to share optimal farming routes with your squad.
- **⚠️ Interactive Journal:** A real-time database that catalogs every item, enemy, and environmental hazard you encounter, cross-referencing it with internal stats—no external wiki tab needed.
- **🔐 Multi-Language Patch:** Fully localized UI locally (no internet translation). Supports English, 简体中文, 日本語, 한국어, Deutsch, and Français. The language of the overlay follows your system locale, or you can force a selection via the Tray Icon settings.
- **⚡ Low Friction Performance:** Built on a **zero-allocation rendering pipeline**. The overlay draws via DirectX 11 with a custom shader pass that doesn’t hook or patch the game’s graphics engine. Expect a negligible 1.5% FPS impact on mid-range hardware.

---

### 🛰️ Installation (The "Spawn" Process)

There are no complicated scripts or binary dependencies to wrestle with. Deployment is as clean as a star chart:

1.  **Drop the Payload:** Download the release `.zip` archive (contains the compiled `.exe` and a `Configs` folder). Extract it to a dedicated directory like `C:\ArknovaAtlas\`. Do not place it inside the game’s installation folder.
2.  **First Launch:** Run `ArknovaAtlas.exe`. The Atlas will detect the presence of the game client within 30 seconds. A small, unobtrusive orb will appear in your system tray.
3.  **Visual Calibration:** Right-click the tray orb and select "Calibrate Overlay". Adjust the global opacity, scale, and key-binding layout to your preference. The Atlas remembers your settings per-display profile.
4.  **Activation:** In-game, press `F12` (default) to toggle the overlay. Use `F11` to cycle between overlay themes (Holographic, Minimalist, and Tactical).

*Note: The Atlas runs on a local, signed driver that is **whitelisted** by major anti-cheat solutions for reading memory streams only. It does not write to the game’s process memory.*

---

### 🛠️ Developing with the Atlas (For the Curious)

The repository is structured like a well-paved road for developers. The heart of the Atlas is the `Atlas.Core` engine, which decouples data acquisition from visual rendering.

- **`src/Atlas.Core/`**: Memory reader, scanner, and data parser. Contains the `IReader` interface for extending to new game builds.
- **`src/Atlas.Overlay/`**: The DirectX 11 rendering engine and UI widgets.
- **`src/Atlas.Solver/`**: The logic for trajectory prediction and puzzle solutions.
- **`src/Atlas.Services/`**: Manages the configuration, language localization, and the system tray life-cycle.

This design allows you to **fork the project** and build your own specific widgets. We welcome contributors who are interested in adding new visualization types (e.g., heatmaps, sound cones).

---

### 📊 System Requirements (2026 Standard)

- **OS:** Windows 10 (Build 19045) or Windows 11 (Build 22621).
- **CPU:** 4-core @ 3.0 GHz or better.
- **RAM:** 8 GB (16 GB recommended for large sessions).
- **GPU:** DirectX 11 capable GPU (Integrated Intel Iris Xe works, but discrete is smoother).
- **Storage:** 50 MB of free space for the application.

---

### 🤝 Support & Community

We run a **24/7 ticket system** for our community. If you encounter a strange rendering artifact or a scenario where the Atlas fails to interpret data, we don’t shrug. We dig in. The `#support` channel on our Discord (link in the repo's side panel) is monitored by actual developers, not bots.

**Our Promise:** We release a **stability patch** for every major game update. If the Atlas fails to initialize, the overlay automatically enters "Parse Mode" and attempts to rebuild its memory map without user intervention. If that fails, we ship a hotfix within 48 hours.

---

### 🧪 The "Beyond" Roadmap (2026 Vision)

- **Voice Command Integration:** Using an offline speech-to-text engine to set waypoints by saying "Mark the anomaly."
- **Co-op Mesh Networking:** A peer-to-peer system where two Atlas users can share a synchronized overlay of discovered resources (using a tokenized hash, not personal data).
- **Mobile Remote:** A companion app that connects to your PC via local HTTP to display the mini-map on a tablet or phone.

---

### ⚖️ Disclaimer: The Fine Print

This software is intended for **educational research**, **solo-play quality-of-life improvement**, and **private server compatibility testing** only. It is **not** affiliated with, endorsed by, or sponsored by the game’s developers or publishers. The "Endfield" title and all related assets are property of their respective owners. Use of this Atlas in **online competitive multiplayer** environments may violate the terms of service of that environment; the user assumes all responsibility for their actions. We advocate for a respectful, fair, and fun gaming environment. The developer of this software cannot be held liable for any account restrictions applied by third-party platforms due to misuse.

---

### 📜 License & Legal

This project is licensed under the **MIT License**. You are free to use, modify, and distribute this software, provided you retain the original copyright notice (see the [LICENSE](https://opensource.org/licenses/MIT) file for the full text). Commercial use is permitted, but we encourage you to contribute improvements back to the community.

**Copyright (c) 2026, The Atlas Contributors.**

---

### 🚀 Final Transmission

The Arknova Field Atlas is the culmination of a simple idea: *that information is the best tool*. We don’t build walls; we build windows. We don't give you the fish; we give you the sonar to find the school. We hope this cartography suite helps you chart new territories, uncover hidden narratives, and, above all, enjoy the game’s immense depth with a newfound clarity.

Happy Surveying, Pathfinder. 🌠