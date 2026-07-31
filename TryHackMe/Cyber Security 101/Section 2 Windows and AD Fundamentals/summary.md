# 🪟 Section 2: Windows and AD Fundamentals  
Authored by Rafael Mejia Galvan

This section introduces **Microsoft Active Directory (AD)** and its role in managing devices, users, policies, and authentication within corporate environments. AD is the backbone of Windows-based enterprise networks, enabling centralized management and enhanced security.  

---

## 📖 Active Directory Basics  
- **Active Directory (AD)** simplifies management of devices and users in corporate environments.  
- It is widely used as the **backbone of enterprise IT systems**.  

---

## 🏢 Windows Domains  
- A **domain** is a group of users and computers managed under a business.  
- Domains are centralized in **Active Directory**.  
- **Domain Controller (DC):** Server running AD services.  
- Advantages:  
  - 🔑 **Centralized identity management** – Manage all users from one place.  
  - 🛡️ **Security policies** – Apply and enforce security rules across the network.  

---

## 📂 Active Directory Structure  
- **AD DS (Active Directory Domain Service):** Core service that stores all network “objects.”  
- **Objects include:**  
  - 👤 **Users** – Represent people or services; security principals with privileges.  
  - 💻 **Machines** – Created for every computer in the domain; accounts are auto-rotated with strong random passwords.  
  - 👥 **Security Groups** – Define permissions for sets of users (e.g., Domain Admins, Backup Operators, Account Operators).  

- **Organizational Units (OUs):** Containers that group users/machines. Handy for applying policies to specific roles.  
- **Default Containers:** Builtin, Computers, Domain Controllers, Users, Managed Service Accounts.  

---

## 👤 Managing Users in AD  
- OUs are protected from accidental deletion.  
- **Delegation** allows assigning privileges to non-admins (e.g., IT support can reset passwords).  

---

## 💻 Managing Computers in AD  
- Default container: **Computers**.  
- Devices are divided into:  
  - **Workstations** – User login devices; should not host privileged users.  
  - **Servers** – Provide services to users and systems.  
  - **Domain Controllers** – Sensitive devices managing the AD Domain and storing hashed passwords.  

---

## 📜 Group Policies (GPOs)  
- **GPOs** = collections of settings applied to OUs.  
- Types: user-based or computer-based policies.  
- Distributed through **SYSVOL share** on DCs.  
- Commands: `gpupdate /force` to sync immediately.  
- Scope and security filtering allow targeted policy application.  

---

## 🔑 Authentication Methods  
- All credentials stored on Domain Controllers.  
- Two authentication protocols:  
  - **Kerberos (Default)** – Secure ticket-based system using TGT (Ticket Granting Ticket) and TGS (Ticket Granting Service).
  <img width="1047" height="416" alt="Image" src="https://github.com/user-attachments/assets/a92fe224-982b-49cf-a86a-5e431b75ea88" />
  <img width="1049" height="486" alt="Image" src="https://github.com/user-attachments/assets/d555a98f-2d78-4846-9d34-d5a9b9e39abb" />
  <img width="1029" height="362" alt="Image" src="https://github.com/user-attachments/assets/85271cb9-5bd8-4602-acc1-c71dc1d2dd56" />
  
  - **NetNTLM (Legacy)** – Challenge-response protocol for compatibility.
  <img width="1051" height="605" alt="Image" src="https://github.com/user-attachments/assets/2eb3cdd8-c6db-4f8d-b351-dfd3ea076cde" />

---

## 🌳 Trees, Forests & Trusts  
- **Trees** – Multiple domains sharing the same namespace.  
- **Forests** – Several trees with different namespaces.  
- **Trust Relationships** – Allow users across domains to access resources.  
  - One-way trust: one domain trusts another.  
  - Two-way trust: mutual trust, default when domains join trees/forests.  

---

## 🧠 What I Learned  
- AD is essential for **centralized user, device, and policy management**.  
- OUs and Security Groups are powerful for organizing and controlling access.  
- **Delegation** helps offload tasks like password resets without giving full admin rights.  
- Group Policies allow **fine-grained control** of security and user settings.  
- **Kerberos** is the modern, secure authentication method, while **NetNTLM** lingers for legacy reasons.  
- Trees, forests, and trusts allow enterprises to **scale securely** across multiple domains.  

**🛠️ Simulation Practice:**  
- Delegated IT privileges to reset passwords using PowerShell:  
  'Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose'
- Edited GPOs to enforce:
  - Minimum password length
  - Restrict Control Panel access (applied to Management, Marketing, and Sales)
  - Auto-lock screen after 300 seconds of inactivity (applied to all computers)
