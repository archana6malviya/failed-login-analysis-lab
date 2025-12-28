# Failed Login Attempts & Security Event Analysis Lab

## 📌 Project Overview
This project demonstrates hands-on practice in identifying failed login attempts
and basic security events using Windows and Linux virtual machines.

The goal of this lab is to understand how security logs help detect
unauthorized access attempts and potential brute-force attacks.

---

## 🛠 Tools & Technologies Used
- VirtualBox
- Windows 10
- Linux (Ubuntu)
- Event Viewer
- Linux auth logs
- Basic command-line tools
- Wireshark (optional)

---

## 🔍 Scenarios Covered
- Failed user login attempts
- Account authentication failures
- Suspicious login behavior
- Log analysis and correlation

---

## 🪟 Windows Log Analysis
- Analyzed **Event ID 4625** (Failed Logon)
- Identified:
  - Username
  - Logon type
  - Source IP address
- Used Event Viewer for investigation


📸 Screenshots available in: screenshots/windows/

---

## 🐧 Linux Log Analysis
- Analyzed authentication logs:

- Failed SSH login attempts were filtered from auth.log using tail and grep
to identify authentication failures.

```bash
sudo tail -n 50 /var/log/auth.log | grep -i "failed password"

📸 Screenshots available in: screenshots/linux/

🚨 Key Learnings
Understanding authentication logs
Identifying brute-force indicators
Importance of log monitoring in SOC operations
Hands-on exposure to real security events


📈 Future Improvements
Integrate SIEM (Splunk / Elastic)
Create alert rules
Automate detection using Python

---
### Event ID 4625 – Windows Failed Login Investigation
Event ID 4625 details were captured using the Details tab (Friendly and XML views).
Multiple screenshots were taken to document account, failure, and network information.
The following screenshots document the investigation workflow:

1. Security log overview
2. Filtered failed login events (Event ID 4625)
3. Account and failure details
4. Network and logon type analysis
5. Raw XML event data

-----
### Linux Investigation- Failed login
1️⃣ Environment Preparation

Deployed an Ubuntu Linux virtual machine using VirtualBox / VMware

Ensured SSH service was running to generate authentication events

Confirmed logging via /var/log/auth.log
2️⃣ Incident Simulation

Generated multiple failed SSH login attempts by:

Attempting SSH access with incorrect passwords

Using invalid and valid usernames

This activity simulated potential brute-force behavior
3️⃣ Log Identification
Verified log updates using:

sudo tail -n 20 /var/log/auth.log

4️⃣ Log Filtering & Analysis
sudo tail -n 50 /var/log/auth.log | grep -i "failed password"

Real-Time Monitoring (Optional)
Monitored authentication logs live using:

sudo tail -f /var/log/auth.log

Observed logs updating during additional failed login attempts
Evidence Collection

Captured screenshots of:

Terminal overview

Filtered failed login output
