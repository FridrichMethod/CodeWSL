# CodeWSL

Registry files to add "Open with VS Code (WSL)" and "Open with Cursor (WSL)" context menu options to Windows Explorer.

These scripts allow you to right-click a folder or file in Windows Explorer and open it directly inside your WSL instance using VS Code or Cursor.

## Contents

The repository is organized into two main directories:

- **`vscode/`**: Registry scripts for Visual Studio Code.
- **`cursor/`**: Registry scripts for Cursor AI Editor.

Each directory contains variations for different WSL configurations:

- `*WSL.reg`: Uses your **default** WSL distribution.
- `*WSLUbuntu.reg`: Targets the **Ubuntu** distribution specifically (`wsl -d Ubuntu`).
- `*WSLDebian.reg`: Targets the **Debian** distribution specifically (`wsl -d Debian`).

## Usage Instructions

1. **Download the files**: Clone this repository or download the specific `.reg` file you need.
2. **Choose your editor and distro**:
    - Navigate to `vscode` or `cursor`.
    - Select the file matching your target distribution (e.g., `VSCodeWSL.reg` for default WSL, or `CursorWSLUbuntu.reg` for Cursor on Ubuntu).
3. **Install**:
    - Double-click the `.reg` file.
    - Click **Yes** when prompted by User Account Control.
    - Click **Yes** to confirm adding the information to the registry.
    - Click **OK** to finish.
4. **Verify**:
    - Right-click on any folder or file in Windows Explorer.
    - You should see a new option: **"Open with Code (WSL)"** or **"Open with Cursor (WSL)"**.

## Prerequisites

- **WSL**: You must have Windows Subsystem for Linux installed and configured.
- **Editor in Path**: The `code` or `cursor` command must be available in your WSL shell's PATH.
  - For VS Code, this is usually automatic.
  - For Cursor, ensure the `cursor` CLI is working inside WSL.
- **Windows Paths**: The scripts assume default installation paths for icons:
  - VS Code: `%USERPROFILE%\AppData\Local\Programs\Microsoft VS Code\Code.exe`
  - Cursor: `C:\Program Files\cursor\Cursor.exe` or `%USERPROFILE%\AppData\Local\Programs\cursor\Cursor.exe` (check your specific script if icons don't appear).

## Customization

If your specific distribution name differs (e.g., "Ubuntu-20.04"), you can edit the `.reg` file in a text editor before running it:

1. Open the `.reg` file with Notepad.
2. Find the command sections (e.g., `wsl.exe -d Ubuntu ...`).
3. Change `Ubuntu` to your distribution name (check `wsl --list` in PowerShell).
4. Save and run the file.
