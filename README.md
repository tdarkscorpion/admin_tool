# Talisman Control Panel (Server Admin Tool)

![Status](https://img.shields.io/badge/Status-Production-success?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-Compiled_C-purple?style=for-the-badge)
![UI](https://img.shields.io/badge/UI-Acrylic_Glass-blue?style=for-the-badge)

A premium, high-performance desktop administration panel designed specifically for managing remote **Talisman Online** game servers. Built with a fully modern **Acrylic Glass/Glassmorphism** interface and compiled into a secure native Windows executable.

---

## ⬇️ Download

<div align="center">

[![Download Admin Tool](https://img.shields.io/badge/⬇%20DOWNLOAD%20ADMIN%20TOOL-v1.0.2-brightgreen?style=for-the-badge&logo=windows&logoColor=white&labelColor=1a1a2e&color=27ae60)](https://github.com/tdarkscorpion/admin_tool/raw/main/Admin%20Tool.exe)

**Windows 10 / 11 &nbsp;•&nbsp; 64-bit &nbsp;•&nbsp; No Installation Required &nbsp;•&nbsp; Auto-Updating**

</div>

> [!IMPORTANT]
> Click the green button above to download the latest `Admin Tool.exe` directly. Just run it — no installation needed.

---

## 🌟 Key Features

### 🖥️ 1. Real-Time Server Dashboard
*   **Live Status Monitoring**: Monitors active processes (`db_server`, `login_server`, and `game_server`) on the remote VPS.
*   **Active Port Scanning**: Automatically scans listening network ports for each service in real-time.
*   **1-Click Process Control**: Gracefully **START** or **STOP** servers.
*   **Live Console View**: Watch live, scrolling server terminal output directly inside the tool to monitor errors or start sequences.
*   **Safe Shutdown Controls**: Injects standard `Ctrl+C` interrupt signals to running screen sessions, allowing the servers to save character database states before stopping.

### 📜 2. Fast Trade Log Viewer
*   **Remote Monthly Aggregation**: Queries and parses server-side transaction files located in `/root/game/anti/` on the fly.
*   **Instant Filtering**: Scan logs by **Player Name** (highlighted as Sender/Receiver) and specific **Date/Time Ranges** using calendar selection.
*   **Quick Presets**: Fast-click presets for `Today`, `Yesterday`, `Last 7 Days`, and `Last 30 Days` (defaults to Today to prevent excessive bandwidth usage).
*   **Fast CSV Item Translation**: Loads `/root/game/admin/item_desc.csv` to translate raw game item codes into bold, clear, readable names instantly.
*   **Gold/Silver/Copper Formatting**: Automatically parses database copper coin integers into high-visibility Gold, Silver, and Copper display tokens.
*   **Smooth client-side Pagination**: Displays only 10 entries per page to eliminate lag, with fast Previous/Next controls and a scrolling reset.

### 🛡️ 3. Advanced Administrative Tools
*   **Safe VPS Reboot Sequence**:
    1. Triggers safe game server shutdown routines (`Ctrl+C` key injection).
    2. Runs a visible **60-second countdown timer** to allow database files to write securely to disk.
    3. Issues the reboot command and cleanly disconnects the SSH stream.
    4. Enters an auto-reconnect loop in the background and notifies you with a popup as soon as the VPS is back online.

### 🔒 4. Security & Architecture
*   **Zero Source Footprint**: Compiled directly to a native Windows machine code executable (.exe) using Nuitka. Contains no Python code or bytecode, preventing decompilation and protecting database keys.
*   **Secure Profiles**: Automatically encrypts and saves server logins inside custom `.dark` files using Fernet AES-256 encryption.
*   **Host Key Protection**: Automatic validation of remote host key signatures against safe local AppData hosts store.
*   **Automatic Upgrades**: Checks for new versions at startup directly against the GitHub repository and auto-updates the executable cleanly via a detached batch script handler.

---

## 🚀 Getting Started

### Installation
1. Download the latest `Admin Tool.exe` from this repository.
2. Run the application on Windows.
3. Enter your server's SSH IP, Port, Username, and Password.
4. Click **LOGIN TO SERVER**.

> [!IMPORTANT]
> The admin tool encrypts your login details and stores them in your Windows local AppData configuration folder (`%APPDATA%/TalismanAdmin/`). You can save or load profiles using the **Save Profile** / **Load Profile** buttons.

---

## 🛠️ Requirements & Dependencies
*   **Client OS**: Windows 10 / 11 (64-bit).
*   **Server Environment**: Linux VPS hosting Talisman Online server processes running inside `screen` sessions.
*   **Server Paths**:
    *   Item CSV: `/root/game/admin/item_desc.csv`
    *   Trade Logs: `/root/game/anti/`
