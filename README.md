# MA-Win-Ignition

This script is designed to automate the configuration of a clean Windows 11 installation into a malware analysis environment. It streamlines the removal of security features and the installation of essential tooling.

## PREREQUISITE
**You MUST manually disable Tamper Protection before running this script.** Windows prevents scripts and registry changes from disabling Defender if Tamper Protection is active.

1.  Open **Windows Security**.
2.  Go to **Virus & threat protection** > **Manage settings**.
3.  Switch **Tamper Protection** to **Off**.

---

## Requirements

### 1. System Requirements
* **Operating System:** Windows 10 or 11 (Clean installation preferred).
* **Environment:** **Virtual Machine ONLY.** Do not run this on your host machine.
* **Network:** Active Internet connection is required during execution to download Scoop and the analysis tools.

### 2. Execution Requirements
* **Administrator Privileges:** The script must be executed in a PowerShell terminal with "Run as Administrator" rights.
* **Execution Policy:** You must allow the execution of unsigned scripts for the duration of the setup.

---

## Installation & Usage

1.  **Open PowerShell as Administrator.**
2.  **Bypass Execution Policy** to allow the script to run:
    ```powershell
    Set-ExecutionPolicy Bypass -Scope Process -Force
    ```
3.  **Run the Ignition Script:**
    ```powershell
    .\MalwareLab_Ignition.ps1
    ```
4.  **Reboot the System:** After the script completes, a reboot is mandatory to fully disable the Windows Defender services and finalise the configuration.

---

## Toolset Summary
The script utilises **Scoop** to install portable versions of the following:

| Category | Tools Included |
| :--- | :--- |
| **Static Analysis** | PEStudio, Capa, Detect It Easy (DIE), Ghidra, Floss |
| **Dynamic Analysis** | x64dbg, Wireshark, Process Hacker, Sysinternals Suite |
| **Utilities** | CyberChef, HxD, HashMyFiles, 7-Zip |

All tools are linked in a **MalwareTools** folder created automatically on your Desktop.
