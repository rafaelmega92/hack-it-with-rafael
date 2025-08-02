# 🛡️ IBM SkillsBuild: Getting Started with Threat Intelligence and Hunting

This course explores the foundations of threat intelligence, proactive threat hunting, and global cyberattack monitoring. It covers cyber threats, enterprise vulnerabilities, hunting methodologies, and using IBM's X-Force Exchange to track real-time attacks.

---

## 📊 Module 1: Threat Intelligence

### 🔍 Reasons Behind Cyber Attacks
- Cyberattacks target systems for **data theft, fraud, sabotage**, or **political purposes**.
- Attack types include: 
  - Physical Access
  - Brute Force
  - Misconfiguration or Human Error
  - Phishing
  - Malvertising
  - Watering Hole Attacks
  - SQL Injection
  - Denial of Service
  - Malware (ransomware, zero-day, hybrids, etc.)
- Impacts:
  - Reputational damage, loss of IP, regulatory penalties, and complete business collapse.

### 🌐 Global Threat Trends
- Major attack trends:
  - Ransomware (23%)
  - Spear Phishing
  - Linux Malware
  - Data theft ↑ 160%, Server access ↑ 233%
- Ransomware-as-a-Service (RaaS) on the rise with double extortion tactics.
- Common vectors: scan-and-exploit (35%), phishing (33%), credential theft (18%)
- Common ransomware targets:
  - **USA** (58%), **UK** (8%)
  - Industries: Manufacturing, Professional Services, Wholesale

### 🔥 Top Vulnerabilities Exploited
- CVE-2019-19781 (Citrix ADC)
- CVE-2019-0708 (Bluekeep), Apache Struts CVEs, Fortinet exploits

### 🌍 Threat Assessment by Industry & Geography
- **Finance**: Mobile banking fraud, malware
- **Manufacturing**: Ransomware, BEC scams
- **Energy**: Server access, data leaks
- **Retail**: Credential theft, misconfigurations
- **Gov/Healthcare**: Ransomware (Sodinokibi, Ryuk), CVE exploitation
- **Top regions attacked**: Europe (31%), NA (27%), APAC (25%)

### 🏢 Enterprise Security Domains
- Domains: Network, Mobile, Endpoint, Applications, Data & Identity, SOAR, Threat Hunting, Cloud, AI Security Intelligence
- Collaboration and intelligence-sharing are key to identifying and mitigating threats.

---

## 🧠 Module 2: Threat Hunting

### 💪 Cyber Resilience
- A resilient org can **continue operations despite attacks**.
- 68% of execs admit they’re **unprepared** for modern cyber threats.
- Root causes of breaches: Malicious attacks (48%), Human error (27%), System glitches (25%)
- IBM Cyber Resilience Lifecycle (based on NIST):
  - **Identify, Protect, Detect, Respond, Recover**
  - Goal: Zero downtime, always-on operations

### 🎯 Why Threat Hunting?
- Proactive hunting reduces attacker dwell time (avg. 191 days).
- Human-led + automated analysis provides deep insights.
- Threat hunters think like adversaries using frameworks like:
  - **MITRE ATT&CK**
  - **IBM X-Force IRIS**

### 🎮 Interactive Activity #1: Know Your Enemy
- 4 Phases of an Attack:
  1. Preparation
  2. Initial Compromise
  3. Lateral Movement
  4. Persistence and Evading Defense

### 🛡️ Interactive Activity #2: Defense Tips
- Techniques:
  - Harden attack surfaces
  - Use MFA
  - Deploy centralized logging
  - Monitor traffic anomalies
  - Set up honeypots and alerts

### 🧪 Threat Hunting Methodology
- Sqrrl Threat Hunting Loop:
  1. Hypothesize
  2. Investigate
  3. Discover TTPs
  4. Improve analytics
- Essential tools/data:
  - Internal systems, HR data
  - External threat intel (e.g. dark web)
  - Behavioral analytics (UEBA)
  - Visualization & intelligence tools

---

## 🌍 Module 3: Threat Map Worldwide View with IBM X-Force Exchange

### 🧭 Milestone 1: Analyzing Botnet Global Threat Reports
**Objective**: Use IBM X-Force Exchange to locate active ransomware and analyze recent botnet threats.

**What I Did**:
- Navigated the IBM X-Force portal to locate live threat intelligence reports.
- Focused on ransomware groups and recent attacks.

**What I Learned**:
- The exchange provides **real-time insight** into emerging threats.
- You can access detailed IOCs (Indicators of Compromise) and link them to MITRE ATT&CK tactics.
- It’s a crucial platform for **cyber situational awareness**.

### 🌐 Milestone 2: Visualizing the Cyber Threat Activity Map
**Objective**: Use the X-Force Threat Map to visualize cyberattacks in real time and set up alerts.

**What I Did**:
- Observed live attacks across different regions.
- Set up notifications for threat categories.

**What I Learned**:
- The map gives a powerful **visual snapshot** of global cyber activity.
- Alerts can help you track **specific threat actors** or malware campaigns.
- Ideal tool for SOC analysts and cyber threat hunters to stay informed.

---

📝 **Final Thoughts**
This course gave me a powerful overview of **how modern organizations defend themselves against real-world cyber threats** — through threat intelligence, threat hunting, and cyber resilience strategies. The real-time tools like **IBM X-Force Exchange** offer hands-on experience for tracking and preparing for attacks.

