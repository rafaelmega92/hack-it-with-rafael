# 🖥️ Section 3: Command Line  
Authored by Rafael Mejia Galvan

## 🪟 Windows Command Line  

### 🔹 Task 1: Introduction  
- Many prefer GUI until mastering CLI.  
- **Advantages of CLI**:  
  - ⚡ Lower resource usage  
  - 🔁 Easier automation with batch files/scripts  
  - 🌐 Convenient for remote management (via SSH)  
- Default Windows CLI: `cmd.exe`  

### 🔹 Task 2: Basic System Information  
- `set` → view system path  
- `ver` → check OS version  
- `systeminfo` → list OS/system details (CPU, memory, etc.)  
- `help` → info about specific commands  
- `cls` → clear screen  
- `CTRL + C` → exit  

### 🔹 Task 3: Network Troubleshooting  
- `ipconfig` / `ipconfig /all` → show network config  
- `ping target_name` → test connectivity  
- `tracert target_name` → trace route hops to destination  
- `nslookup domain.com` → resolve domain to IP  
- `netstat` → show network connections & ports  
  - `-a` all connections/ports  
  - `-b` program using port  
  - `-o` process ID (PID)  
  - `-n` numeric display  

### 🔹 Task 4: File & Disk Management  
- `cd` → show current directory  
- `dir` → list files/dirs  
  - `/a` → show hidden/system files  
  - `/s` → recursive listing  
- `tree` → show directory structure visually  
- `cd ..` → move up one level  
- `mkdir` / `rmdir` → create/remove directory  
- `type` → read text files  
- `copy` / `move` → copy/move files  
- `del` / `erase` → delete files  
- `*` → wildcard for multiple files  

### 🔹 Task 5: Task & Process Management  
- `tasklist` → list running processes  
- `tasklist /FI "imagename eq sshd.exe"` → filter by process name  
- `taskkill /PID target_pid` → terminate process  

### 🔹 Task 6: Conclusion Commands  
- `chkdsk` → check disk for errors  
- `driverquery` → list installed drivers  
- `sfc /scannow` → scan & repair system files  
- `-/?` → help for most commands  

---

## ⚡ Windows PowerShell  

### 🔹 Task 1: What is PowerShell?  
- Cross-platform CLI + scripting + config management tool  
- Object-oriented (works with properties & methods, not just text)  
- Cmdlets (command-lets) return objects with rich data  

### 🔹 Task 2: Basics  
- **Launch**: Start Menu, Run (`Win+R`), File Explorer, Task Manager  
- Cmdlets use **verb-noun** convention  
- `Get-Command` → list all cmdlets  
- `Get-Help` → details on cmdlets (`-examples` for usage examples)  
- `Get-Alias` → show cmdlet aliases  
- Extend functionality: `Find-Module` / `Install-Module`  

### 🔹 Task 3: Files & Directories  
- `Get-ChildItem` → list directory contents  
- `Set-Location` → change directory  
- `New-Item` → create file/dir  
- `Remove-Item` → delete file/dir  
- `Copy-Item` / `Move-Item` → copy/move files  
- `Get-Content` → read files  

### 🔹 Task 4: Piping, Filtering, Sorting  
- `|` pipe output to next command  
- `Sort-Object` → sort data  
- `Where-Object` → filter by conditions  
  - `-eq`, `-ne`, `-gt`, `-ge`, `-lt`, `-le`  
- `Select-Object` → show only specific properties  
- `Select-String` → search text inside files/logs  

### 🔹 Task 5: System & Network Info  
- `Get-ComputerInfo` → system/OS/BIOS details  
- `Get-LocalUser` → list local accounts  
- `Get-NetIPConfiguration` → network settings  
- `Get-NetIPAddress` → list all IPs  

### 🔹 Task 6: Real-Time System Analysis  
- `Get-Process` → active processes (CPU/memory usage)  
- `Get-Service` → service states (running/stopped)  
- `Get-NetTCPConnection` → active TCP sessions (useful in IR/malware analysis)  
- `Get-FileHash` → file integrity verification  

### 🔹 Task 7: Scripting  
- Automates repetitive tasks via `.ps1` scripts  
- Uses in:  
  - 🔵 Blue team: log analysis, IOC detection  
  - 🔴 Red team: system enumeration, obfuscation, remote execution  
  - 👨‍💻 Sysadmins: config enforcement, automation  
- `Invoke-Command` → execute remotely (key for scale & pentesting)  

---

## 🐧 Linux Shells  

### 🔹 Task 1: Basics  
- `pwd` → print working directory  
- `cd` → change directory  
- `ls` → list contents  
- `grep` → search inside files  

### 🔹 Task 2: Shell Types  
- `echo $SHELL` → current shell  
- `cat /etc/shells` → available shells  
- `chsh -s /usr/bin/<shell>` → change default shell  

**Bash (default)**  
- Tab completion, command history, scripting  

**Fish (user-friendly)**  
- Simple syntax, spell correction, colorful syntax highlighting, themes  

**Zsh (customizable)**  
- Advanced tab completion, scripting, spell correction, heavy customization  

### 🔹 Task 3: Shell Scripting  
- Scripts saved as `.sh`, start with `#!` shebang  
- Variables, loops, and conditionals supported  
- `chmod +x script.sh` → grant execution rights  
- `./script.sh` → run script  
- `# comment` → explain code  

**Practice:** Built small scripts with loops, conditionals, and a **locker script** requiring username + company + pin for access.  

---

## 📝 What I Learned  
- I strengthened my ability to **navigate both Windows and Linux command-line tools**.  
- I gained practical skills in **system diagnostics, process management, and troubleshooting network issues**.  
- I learned the **differences between cmd.exe, PowerShell, and Linux shells**, as well as when each is most effective.  
- PowerShell introduced me to **object-based commands and automation**, which is a major step up from traditional CLI.  
- I practiced writing **shell scripts and automation tasks**, including creating a locker script — giving me hands-on experience with real-world security scenarios.  
- Overall, I now feel more confident using the CLI for **administration, troubleshooting, and cybersecurity analysis**.  

---
