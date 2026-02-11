# epic-switcher

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
   Make sure the script is executable:
   `chmod +x ./epic-switcher`

2. **Configure Prefix:**
   Open the script and ensure the `EGS_PFX` variable points to your Epic Games Launcher Wine prefix.

## 📖 Usage

### Create a New Account
Log into the Epic Games Launcher, then run:
`epic-switcher new my-main-account`

### Save an Existing Account
Log into the Epic Games Launcher, then run:
`epic-switcher save`

### Switch Accounts
Ensure you are ready to swap, then run:
`epic-switcher load my-alt-account`

### List Saved Accounts
`epic-switcher list`

### Rename an Account
`epic-switcher rename my-old-name my-new-name`

### Delete an Account
`epic-switcher delete my-crap-account`

### See a List of Commands
`epic-switcher --help`

## 🏗️ Technical Implementation & Roadmap

### Termination Strategy
To ensure data integrity, the script employs a two-stage shutdown process:
1. **Stage 1 (Graceful):** Uses `wine taskkill` to request a clean exit.
2. **Stage 2 (Force):** Uses `wineserver -k` to terminate the specific prefix.

*Note: `pkill` was intentionally removed to ensure OS session stability.*

### Roadmap
- Transition to **Registry-driven detection** (`HKCU\Volatile Environment`).
- Implement `winepath -u` for dynamic Linux/Windows path translation.
- Refactor environment initialization with guard clauses for performance.

## 🛡️ Dependencies
- **Wine / Proton**
- **rsync**
- **coreutils**

---
Copyright © 2026 doccy-doc
**License:** GPLv3 [See License](./LICENSE)
