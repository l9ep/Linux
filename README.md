<div align="center">

```
██╗     ██╗   ██╗███╗   ██╗██╗██╗  ██╗
██║     ██║   ██║████╗  ██║██║╚██╗██╔╝
██║     ██║   ██║██╔██╗ ██║██║ ╚███╔╝ 
██║     ██║   ██║██║╚██╗██║██║ ██╔██╗ 
███████╗╚██████╔╝██║ ╚████║██║██╔╝ ██╗
╚══════╝ ╚═════╝ ╚═╝  ╚═══╝╚═╝╚═╝  ╚═╝
```

**Script hosting hub for Roblox executors**  
*Built by xyth — currently in testing phase*

![Status](https://img.shields.io/badge/status-testing-yellow?style=flat-square&labelColor=0d1117)
![Version](https://img.shields.io/badge/version-1.0-blue?style=flat-square&labelColor=0d1117)
![Platform](https://img.shields.io/badge/platform-GitHub%20Pages-brightgreen?style=flat-square&labelColor=0d1117)

**[→ Open Lunix](https://l9ep.github.io/Linux.obfuscator/)**

</div>

---

## What is Lunix?

Lunix is a dark-themed script hub built for Roblox exploiting. It lets you host Lua scripts, generate loadstring commands for Delta executor, obfuscate your code, and manage everything from a clean web UI — all from a single HTML file deployable on GitHub Pages.

---

## Features

### 🔐 Sign In / Register
- Create an account with username, email and password
- Accounts are stored locally in the browser (localStorage) during testing
- No real backend needed to test — everything works out of the box
- Firebase backend planned for v2 for persistent cloud storage

### 📜 Script Hosting
- Upload Lua scripts with name, game tag and description
- Auto-generates a **loadstring command** for Delta executor
- Copy raw script code instantly
- Scripts persist across sessions via localStorage

### ☠ Lua Obfuscator
Three levels of obfuscation, all running client-side:

| Level | What it does |
|-------|-------------|
| ⚡ **Light** | Renames local variables to unreadable names |
| 🔥 **Medium** | XOR encrypts the entire script, wrapped in a `load()` call |
| ☠ **Max** | Double XOR pass + garbage comment injection + obfuscated variable names |

All levels produce valid Lua that executes normally.

### ⬡ Owner Panel
- Protected by a password (set in the source code)
- Upload and delete scripts
- Separate from regular user accounts — only the hub owner can manage scripts

---

## Current Status

> **Testing Phase** — everything runs on `localStorage` right now.

| Feature | Status |
|---------|--------|
| Sign in / Register | ✅ Working |
| Script upload & hosting | ✅ Working |
| Loadstring generation | ✅ Working |
| Lua Obfuscator (3 levels) | ✅ Working |
| Owner panel | ✅ Working |
| Firebase cloud storage | 🔜 Coming in v2 |
| Script load counter | 🔜 Coming in v2 |
| Public script sharing links | 🔜 Coming in v2 |
| Anti-cheat bypass tools | 🔜 Planned |

---

## Setup

### Deploy to GitHub Pages
1. Fork or clone this repo
2. Make sure `index.html` is in the root
3. Go to **Settings → Pages → Source → main branch**
4. Your site goes live at `https://USERNAME.github.io/REPO/`

### Change Owner Password
Open `index.html` and find this line near the top of the script section:
```js
const OWNER_PASS = 'xyth2024';
```
Change it to your own password before deploying.

### Upgrading to Firebase (v2)
When you're ready to go live with cloud storage:
1. Create a project at [console.firebase.google.com](https://console.firebase.google.com)
2. Enable **Firestore** and **Email/Password Auth**
3. Replace the Firebase config block in `index.html`
4. Apply the Firestore security rules shown in the Owner tab
5. Scripts will then persist across all devices and users

---

## Loadstring Format

When Firebase is connected, loadstrings will point to your Firestore database. For now during testing, you can manually host scripts on GitHub and use:

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/YOUR_USER/YOUR_REPO/main/scripts/SCRIPT_NAME.lua", true))()
```

---

## Tech Stack

- Pure HTML/CSS/JS — zero dependencies, zero build tools
- localStorage for auth and script storage (testing phase)
- Firebase Firestore + Auth planned for v2
- Deployed via GitHub Pages

---

## Credits

Built by **xyth**  
Obfuscator, ESP scripts, silent aim and all tooling written from scratch.

---

<div align="center">
<sub>Lunix v1.0 — Testing Phase — Not for production use yet</sub>
</div>
