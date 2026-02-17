# EGSwitcher

A lightweight, defensive Bash utility for managing multiple Epic Games Launcher accounts on Linux/Wine. Swap accounts instantly without losing your login session or game settings.

## 🚀 Features

* **Session Persistence:** Save and load full launcher states (authentication tokens, launcher settings).
* **Defensive Design:** Automated checks for running Wine processes to prevent data corruption.
* **Wine Native Integration:** Uses `taskkill` and `wineserver -k` for session-safe termination.
* **Smart Directory Detection:** Heuristic scanning to find the Wine user and AppData paths.

## 🛠️ Installation

1. **Move to Path:**
   Make sure the script is executable:
   `chmod +x ./epic-switcher`

2. **Configure Prefix:**
   Open the script with a text editor and ensure the `EGS_PFX` variable points to your Epic Games Launcher Wine/Proton prefix.

## 📖 Usage

### Create a New Account
1. Run: `epic-switcher new my-main-account`
2. Log into the Epic Launcher
3. Type `y` into the prompt

### Save an Active Account
Run:`epic-switcher save`

### Switch Accounts
Run:`epic-switcher load my-alt-account`

### List Saved Accounts
Run:`epic-switcher list`

### Rename an Account
Run:`epic-switcher rename my-old-name my-new-name`

### Delete an Account
Run:`epic-switcher delete my-crap-account`

### See a List of Commands
Run:`epic-switcher --help` or `epic-switcher -h`

## 🏗️ Roadmap
- Transition to **Registry-driven detection** (`HKCU\Volatile Environment`).
- Implement `winepath -u` for dynamic Linux/Windows path translation.
- Implement `debug` flag to assist with bug reports.
- Transition to user-friendly config using CLI commands.

## 🛡️ Dependencies
- **Wine** or **Proton**
- **rsync**
- **coreutils**

---
Copyright © 2025 doccy-doc
**License:** GPL-3.0-only [See License](./LICENSE)

SPDX-License-Identifier: GPL-3.0-only
