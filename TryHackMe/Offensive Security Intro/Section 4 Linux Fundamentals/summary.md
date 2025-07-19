# 🐧 TryHackMe: Linux Fundamentals - Summary

This section covers the foundational aspects of the Linux operating system including terminal commands, file systems, user management, processes, automation, and system maintenance.

---

## 📘 Linux Fundamentals Part 1

### 🔹 Introduction
- Linux is a powerful, open-source operating system used in smart devices, servers, appliances, and more.

### 🧠 A Bit of Background on Linux
- Powers websites, car systems, PoS terminals, industrial sensors, and more.
- Common distributions: Ubuntu, Debian.

### 🖥️ Running Your First Few Commands
- Linux is lightweight but often lacks a GUI.
- Key terminal commands:
  - `echo`: Outputs user-provided text.
  - `whoami`: Displays current user.

### 📁 Interacting With the Filesystem
- Key commands:
  - `ls`: List files/folders in current directory.
  - `cd`: Change directory.
  - `cat`: View file contents.
  - `pwd`: Print current directory path.

### 🔍 Searching for Files
- `find`: Search for files/folders with criteria.
- `*`: Wildcard for any characters.
- `wc`: Count lines, words, etc.
- `grep`: Search for text patterns.

### 🧪 An Introduction to Shell Operations
- `&`: Run in background.
- `&&`: Run second command only if first is successful.
- `>`: Redirect output.
- `>>`: Append output.

---

## 📗 Linux Fundamentals Part 2

### 🔐 Accessing Your Linux Machine Using SSH
- SSH (Secure Shell) connects to remote systems securely over encrypted connections.

### 🎛️ Introduction to Flags and Switches
- Flags (e.g., `-a`, `--help`, `-h`) modify command behavior.
- Use `man` for detailed command help.

### 🧱 Filesystem Interaction Continued
- File management commands:
  - `touch`: Create file.
  - `mkdir`: Create directory.
  - `cp`: Copy file/folder.
  - `mv`: Move/rename file or folder.
  - `rm`: Remove file (`-R` to remove directory).
  - `file`: Identify file type.

### 🔐 Permissions 101
- Read/Write/Execute permissions determine access.
- `su`: Switch user (requires password).
- `su -l`: Start shell with new user’s environment.

### 📂 Common Directories
- `/etc`: System config files.
- `/var`: Frequently written data.
- `/root`: Root user's home.
- `/tmp`: Temporary files accessible to all users.

---

## 📙 Linux Fundamentals Part 3

### 📝 Terminal Text Editors
- `nano`: Basic editor with features like search, copy/paste, and line navigation.
- `vim`: Advanced, customizable, and widely supported editor.

### 🌐 General/Useful Utilities
- `wget`: Download files via HTTP.
- `scp`: Securely copy files between computers via SSH.

### ⚙️ Processes 101
- View processes:
  - `ps`, `ps aux`, `top`
- Manage processes:
  - `kill <PID>`: Kill by process ID.
  - `SIGTERM`, `SIGKILL`, `SIGSTOP`: Types of termination signals.
- `systemd` and `systemctl`: Manage services (start, stop, enable, disable).
- Foreground/Background:
  - `&`, `Ctrl + Z` to background, `fg` to bring to foreground.

### ⏰ Maintaining Your System: Automation
- `crontab`: Schedule tasks.
- Format:
- Example (backup every 12 hours):  
- Edit with `crontab -e`.

### 📦 Maintaining Your System: Package Management
- Use `apt` to install from repos.
- Add repos:
- `add-apt-repository`
- Example: Add Sublime Text repo:
- 'add-apt-repository --remove ppa:PPA_Name/ppa'
