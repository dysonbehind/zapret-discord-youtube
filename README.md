<div align="center">

# <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height=28 /> Zapret Dyson <img src="https://cdn-icons-png.flaticon.com/128/1384/1384060.png" height=28 />

<img src="https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-blue?style=for-the-badge&logo=windows" alt="Windows">
<img src="https://img.shields.io/badge/Language-C%2B%2B%20%7C%20DirectX%2011-purple?style=for-the-badge&logo=c%2B%2B" alt="C++">
<img src="https://img.shields.io/badge/UI-ImGui-darkred?style=for-the-badge" alt="ImGui">
<img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge" alt="Status">

<br>

**An alternative to console utilities. Hardware-accelerated GUI for bypassing DPI restrictions.**

Telegram Desktop, YouTube, Discord acceleration, and full customization.

</div>

> **Zapret Dyson** is a hardware-accelerated Graphical User Interface (GUI) and orchestration system for locally bypassing Deep Packet Inspection (DPI) systems.
> 
> Unlike classic VPN networks, this utility does not route traffic through third-party remote servers. Packet injection, fragmentation, and modification occur locally at the OS kernel level. This approach allows bypassing ISP restrictions while maintaining 100% channel bandwidth and original network ping.

<div align="center">
  <img width="1400" alt="image" src="https://github.com/user-attachments/assets/9b86098c-e7d2-4186-9624-ec83b148d4e0" />
  <img width="1400" alt="image" src="https://github.com/user-attachments/assets/d51828ff-dbed-4fc6-9e4f-614ba6218dad" />
  <img width="1400" alt="image" src="https://github.com/user-attachments/assets/b35b6feb-d53f-4d49-a49d-4653be120d13" />
  <img width="1400" alt="image" src="https://github.com/user-attachments/assets/c0052c7b-c00f-4ef2-b998-fdd162b49519" />
</div>

<br>

> [!CAUTION]
> ### FAKES
> If you come across anything outside of this GitHub page and my Telegram distributed on my behalf - it's a **FAKE**.

> [!WARNING]
> ### ANTIVIRUS AND SYSTEM REACTION
> The program uses the `WinDivert64.sys` driver to handle networking at the OS kernel level. Some antiviruses tend to classify WinDivert files as high-risk. The detection will always be named `WinDivert` or `Not-a-virus:RiskTool.Multi.WinDivert`.
> 
> This is absolutely normal behavior. WinDivert is a legitimate traffic interception tool. Add the utility folder to your antivirus exclusions for stable operation.

> [!IMPORTANT]
> ### BINARY FILE SECURITY
> Starting from version v1.9.0, all code is signed via `signtool` during the Post-Build Event, guaranteeing the authenticity and integrity of the executable. The number of false positive Windows Defender detections has been minimized (Stealth Mode).

---

## 🔥 What's new in v1.9.0 Update

- <ins>**UI & VISUAL REVOLUTION**</ins>
  - **Full Tray Control:** Minimize to the system tray with a functional context menu.
  - **Floating Settings Panel:** Summoned by clicking the gear icon in the header, without overlapping the main interface.
  - **Global Redesign:** Smooth animations (`Slide-In / Slide-Out`), Typewriter effect in the ABOUT section, RGB sliders for accent color.
  - **Particle System:** 4 background animation modes (`Off`, `Snow`, `Matrix`, `FCK RKN`) with instant switching.

- <ins>**TELEGRAM ACCELERATION & CRYPTOGRAPHY**</ins>
  - **Native Telegram SOCKS5:** Built-in server in pure C++ (WinHTTP API) with zero CPU load.
  - **AES-CTR Decryption (MTProto):** Hardware key decryption via Windows BCrypt for error-free routing.
  - **Instant TCP-Fallback:** Automatic switch to a Raw TCP bridge when WebSocket is blocked. No more "infinite connecting" statuses.
  - **One-Click Setup:** Auto-apply proxy button directly to Telegram Desktop.

- <ins>**SYSTEM CORE**</ins>
  - **Smart Persistence:** Auto-save configurations upon closing or minimizing.
  - **Real TCP Ping:** Asynchronous ping without UI freezes.
  - **Built-in List Editor:** A **LISTS** tab for managing domains directly in the GUI.

## 🚀 Architecture & Optimization

The project completely eliminates the need for command shells (CMD/PowerShell) in daily use.

* **Tech Stack:** Developed in pure C++ (DirectX 11 + ImGui). The executable requires Administrator privileges (`requireAdministrator` manifest) to interact with the WinDivert API.
* **Smart UI Synchronization:** The interface communicates with the Windows kernel. Upon launch, it scans active services and automatically restores statuses and checkboxes.
* **Zero-Delay & High-Priority:** The process initializes with the `HIGH_PRIORITY_CLASS` flag. Idle CPU usage is **0%**. Implemented the `ReadExactly` algorithm to protect against TCP fragmentation.

## 🛠️ Technical Features

* **Adaptive Filtering (Smart Profiles):** 7 pre-configured DPI attack vectors (Classic, Aggressive, Mobile, Failsafe) for different ISPs.
* **Background Integration (Windows Services):** Seamless installation into system services. The bypass and Telegram Proxy run invisibly at the OS level.
* **VoIP & Game Mode:** Dedicated routing rule for ports **1024-65535 (TCP/UDP)**. Prevents Packet Loss in games and fixes <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height="14" /> Discord.
* **DNS Block Bypass:** Dynamic spoofing of `Host` and `Origin` headers (SNI Spoofing).

## ⚙️ Usage: Telegram Acceleration

**Option 1. Local execution (Runs while the application is open):**
1. Go to the **SETTINGS** tab.
2. Check **Enable TG Bypass** (launches on port 1080).
3. Click **Apply proxy to Telegram**. Confirm the prompt in the opened Telegram app.
4. Click **Initialise Local Bypass**, you can now minimize the app and enjoy.

**Option 2. Autorun and Background mode (Recommended):**
1. Check **Enable TG Bypass**.
2. Click **Apply proxy to Telegram**. Confirm the prompt in the opened Telegram app.
3. Click **Install Native Service**.
4. The program will install system services. You can now close the window with the 'X' button — the proxy works autonomously!

## 🗒️ Managing Domain Lists

You can now manage routing lists directly from the **LISTS** tab in the program interface.
Physically, the text files are located in the `lists/` folder:
- **`list-general.txt`** — for domains (subdomains are included automatically).
- **`list-google.txt`** — for specific services and exceptions.
- **`list-exclude-user.txt`** / **`ipset-exclude-user.txt`** — to exclude domains/IPs from filtering.

## 📌 Product Principles

1. **Performance:** Zero impact on baseline network latency.
2. **Isolation:** Header modification (SNI, TLS) is performed exclusively on the local PC without third-party servers.
3. **One-Click Deployment:** Transforming complex console parameters into an intuitive graphical interface.

## ⭐ Support the Project

You can support the project by leaving a :star: on this repository (top right of this page).

<a href="https://star-history.com/#dysonbehind/zapret-discord-youtube&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=dysonbehind/zapret-discord-youtube&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=dysonbehind/zapret-discord-youtube&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=dysonbehind/zapret-discord-youtube&type=Date" />
 </picture>
</a>

## ⚖️ Licensing & Source Code Note

The project is distributed under the [MIT](https://github.com/dysonbehind/zapret-discord-youtube/blob/main/LICENSE.txt) license.

> [!NOTE]
> ### 🔒 Source Code Availability
> Please note that the source code for the GUI application and the orchestration wrapper is **not provided**. I highly value the time, effort, and resources invested in developing this software, therefore it remains closed-source. Only the compiled executables are available in the releases.

## 🩷 Acknowledgements

[![Contributors](https://contrib.rocks/image?repo=dysonbehind/zapret-discord-youtube)](https://github.com/dysonbehind/zapret-discord-youtube/graphs/contributors)

💖 Special thanks to the developers of [zapret](https://github.com/bol-van) and [tg](https://github.com/Flowseal).
