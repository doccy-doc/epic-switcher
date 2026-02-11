# EGS Swapper (Beta-1)

A lightweight, defensive Bash utility for managing multiple Epic Games Launcher accounts on Linux/Wine. Swap accounts instantly without losing your login session or game settings.

<!--
## 🚀 Features

* **Session Persistence:** Save and load full launcher states (authentication tokens, launcher settings).
* **Defensive Design:** Automated checks for running processes to prevent data corruption.
* **Wine Native Integration:** Uses `taskkill` and `wineserver -k` for session-safe termination.
* **Smart Directory Detection:** Heuristic scanning to find the Wine user and AppData paths.

-->
## 🛠️ Installation

1. **Move to Path:**
   Place the script in your local binaries folder:
   `cp egs_swapper ~/.local/bin/egs`
   `chmod +x ~/.local/bin/egs`

2. **Configure Prefix:**
   Open the script and ensure the `EGS_PFX` variable points to your Epic Games Launcher Wine prefix.

## 📖 Usage

### Save an Account
Log into the Epic Games Launcher, then run:
`egs save my-main-account`

### Switch Accounts
Ensure you are ready to swap, then run:
`egs load my-alt-account`

### List Saved Accounts
`egs list`

## 🏗️ Technical Implementation & Roadmap

### Termination Strategy
To ensure data integrity, the script employs a two-stage shutdown process:
1. **Stage 1 (Graceful):** Uses `wine taskkill` to request a clean exit.
2. **Stage 2 (Force):** Uses `wineserver -k` to terminate the specific prefix.

*Note: `pkill` was intentionally removed to ensure OS session stability.*

### Beta-2 Roadmap
- Transition to **Registry-driven detection** (`HKCU\Volatile Environment`).
- Implement `winepath -u` for dynamic Linux/Windows path translation.
- Refactor environment initialization with guard clauses for performance.

## 🛡️ Requirements
- **Wine / Proton**
- **rsync**
- **coreutils**

---
Copyright © 2026 doccy-doc
**License:** GPLv3 ([See License](./LICENSE))
