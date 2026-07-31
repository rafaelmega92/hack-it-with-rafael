# 🪟 TryHackMe: Windows Fundamentals - Summary
Authored by Rafael Mejia Galvan

This summary includes notes from the **Windows Fundamentals** module from [TryHackMe](https://tryhackme.com/). The module provides essential knowledge about using and managing Windows operating systems, from basic navigation to system administration tools.

---

## 🧩 Windows Fundamentals 1

### 🖥️ Windows Editions
- Windows has been around since 1985 and is dominant in both home and corporate environments.
- Windows XP was highly popular and long-running.
- The latest server version is **Windows Server 2025**.

### 🧑‍💻 The Desktop (GUI)
- Components include: Desktop, Start Menu, Search Box, Task View, Taskbar, Toolbar, Notification Area.
- GUI customization includes icon size, screen resolution, themes, and wallpaper.
- Taskbar shows open programs; Notification Area shows time, volume, network icons.

### 🗂️ The File System
- Windows uses **NTFS** (New Technology File System), supporting features like:
  - Files >4GB, permissions, compression, encryption (EFS), alternate data streams (ADS).
- File/folder permissions include: Full Control, Modify, Read & Execute, etc.
- View permissions: Right-click → Properties → Security tab.

### 📁 Windows\\System32 Folder
- `C:\Windows` contains the OS files; `%windir%` is the system variable for it.
- `System32` holds critical OS files and utilities.

### 👥 User Accounts & Permissions
- Two main types: **Administrator** and **Standard User**.
- Admins can change system settings; Standard Users have limited access.
- Use `lusrmgr.msc` for managing local users and groups.

### 🔐 User Account Control (UAC)
- Adds security to admin accounts by requiring confirmation for elevated actions.

### ⚙️ Settings & Control Panel
- **Settings** = user-friendly; **Control Panel** = complex and detailed controls.

### 🧠 Task Manager
- View CPU, RAM usage, and manage running processes.

---

## 🧰 Windows Fundamentals 2

### 🧾 System Configuration (MSConfig)
- Used for diagnosing startup issues.
- Tabs include: General, Boot, Services, Startup, Tools.

### 📉 Change UAC Settings
- Change or disable UAC via `useraccountcontrolsettings.exe` (not recommended).

### 🧑‍🔧 Computer Management (`compmgmt.msc`)
- Key utilities include:
  - **Task Scheduler**, **Event Viewer**, **Shared Folders**, **Local Users and Groups**.
  - **Device Manager**, **Disk Management**, **Performance Monitor**, **WMI Control**.

### 💻 System Information (`msinfo32`)
- View system specs, hardware, environment variables, and network info.

### 📊 Resource Monitor (`resmon`)
- Detailed breakdown of CPU, memory, disk, and network usage.

### 💬 Command Prompt (`cmd.exe`)
- Useful commands:
  - `hostname`, `whoami`, `ipconfig`, `netstat`, `net`, `/?`

### 🧱 Registry Editor (`regedit`)
- Stores user settings, hardware configs, installed applications, and OS operations.

---

## 🔒 Windows Fundamentals 3

### 🔄 Windows Updates
- Released monthly (Patch Tuesday).
- Updates eventually install automatically, even if postponed.

### 🛡️ Windows Security
- Protection areas:
  - Virus & threat protection
  - Firewall & network protection
  - App & browser control
  - Device security

### 🦠 Virus & Threat Protection
- Scan types: Quick, Full, Custom.
- Real-time protection, cloud protection, sample submission, controlled folder access.

### 🔥 Firewall & Network Protection
- Windows Firewall Profiles: **Domain**, **Private**, **Public**.

### 🌐 App & Browser Control
- Defender SmartScreen guards against phishing/malware and unrecognized apps.

### 💽 Device Security
- Core Isolation & Memory Integrity for protection.
- TPM chip enables encryption, secure boot, and platform integrity.

### 🛡️ BitLocker
- Encrypts entire drives, especially effective with TPM support.

### 🕒 Volume Shadow Copy Service (VSS)
- Enables restore points and backup snapshots.
- Tasks: create restore point, restore system, manage restore settings.

---

🎉 **Module Complete!**
