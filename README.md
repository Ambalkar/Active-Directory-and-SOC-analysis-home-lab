# 🛡️ Active Directory & SOC Analysis Home Lab

A fully functional **Active Directory (AD) and Security Operations Center (SOC) Home Lab** built on **Oracle VirtualBox**.  
This project simulates a real-world enterprise environment, integrating **Active Directory, Splunk SIEM, Windows Clients, and Kali Linux** for **blue team defense, red team attacks, and SOC monitoring practice**.

---

## 📌 Project Overview

This lab mirrors enterprise networks to provide hands-on experience in:

- **Active Directory Administration** (Users, Groups, GPOs, DNS, DHCP)  
- **Security Monitoring & Analysis** using **Splunk SIEM**  
- **Endpoint Logging** with Sysmon + Splunk Universal Forwarder  
- **Red Team Attacks** with **Kali Linux** (enumeration, privilege escalation, lateral movement)  
- **Blue Team Defense** with Splunk dashboards and alerts  

It’s ideal for:
- SOC Analyst Training  
- Incident Response Practice  
- Cybersecurity Research & Penetration Testing  

---

## 🖥️ Network Topology

                            DEV-Lab-Network
                         (192.168.10.0 / 24)
  ┌────────────────────────────────────────────────────────────┐
  │                                                            │
  │   ┌───────────────┐            ┌───────────────┐           │
  │   │   DEV-DC01    │  <------>  │   SPLUNK-01   │           │
  │   │  (Win Server) │            │   (Ubuntu)    │           │
  │   │  DEV.local    │            │  Splunk SIEM  │           │
  │   │  192.168.10.7 │            │  192.168.10.10│           │
  │   └───────▲───────┘            └───────▲───────┘           │
  │           │                            │                   │
  │           │                            │                   │
  │   ┌───────┴───────┐            ┌───────┴──────────┐        │
  │   │  TARGET-PC    │            │   ATTACKER-PC    │        │
  │   │ (Windows 10)  │            │   (Kali Linux)   │        │
  │   │ Domain Joined │            │   Red Team Ops   │        │
  │   │ DHCP IP ~ .100│            │  192.168.10.250  │        │
  │   └───────────────┘            └──────────────────┘        │
  │                                                            │
  └────────────────────────────────────────────────────────────┘



**Domain Name:** `DEV.local`  
**Network CIDR:** `192.168.10.0/24`  

---

## ⚙️ System Requirements

- **Host Machine:**  
  - RAM: 20GB minimum (24GB recommended)  
  - CPU: Quad-core with virtualization support (Intel VT-x/AMD-V)  
  - Storage: 250GB SSD recommended  
- **Virtual Machines:**  
  - **Domain Controller (Win Server 2019):** 4GB RAM, 100GB disk  
  - **Splunk Server (Ubuntu 22.04):** 8GB RAM, 100GB disk  
  - **Windows 10 Client:** 4GB RAM, 80GB disk  
  - **Kali Linux Attacker:** 4GB RAM, 50GB disk  

---

## 📦 Software Stack

- **Virtualization:** Oracle VirtualBox + Extension Pack  
- **Operating Systems:**  
  - Windows Server 2019 (AD, DNS, DHCP)  
  - Windows 10 Enterprise (Client)  
  - Ubuntu Server 22.04 (Splunk SIEM)  
  - Kali Linux (Attack Platform)  
- **Security Tools:**  
  - Splunk Enterprise (SIEM)  
  - Splunk Universal Forwarder  
  - Sysmon + SwiftOnSecurity Config  
  - BloodHound, nmap, crackmapexec, Responder, etc.  

---

## 🚀 Lab Setup Phases

1. **VirtualBox Environment Configuration**  
   - Create NAT network (`192.168.10.0/24`)  
   - Install VirtualBox & Extension Pack  

2. **Active Directory Setup (Win Server 2019)**  
   - Configure `DEV.local` domain  
   - Install AD DS, DNS, DHCP  
   - Promote server as Domain Controller  

3. **Splunk SIEM Setup (Ubuntu 22.04)**  
   - Install Splunk Enterprise  
   - Configure Universal Forwarder ingestion  
   - Enable Sysmon + Event Logs monitoring  

4. **Windows 10 Client**  
   - Join `DEV.local` domain  
   - Install Sysmon + Splunk Forwarder  
   - Enable logging  

5. **Kali Linux Attacker**  
   - Install penetration testing tools  
   - Configure static IP (`192.168.10.250`)  
   - Run AD enumeration & attack simulations  

---

## 📊 Security Monitoring Scenarios

✅ Detect **failed login attempts**  
✅ Monitor **process creation events**  
✅ Track **network connections**  
✅ Analyze **DNS queries**  
✅ Detect **red team attacks** in Splunk dashboards  

---

## 🧪 Testing & Validation

- **Connectivity Checks:** `ping`, `nslookup`, `nmap`  
- **AD Validation:** `dcdiag`, `repadmin`, GPO checks  
- **Splunk Data Validation:** search Windows Event Logs, Sysmon, Authentication events  

---

## 🔒 Example Use Cases

- SOC Analyst hands-on training  
- Incident Response simulations  
- Threat detection & hunting practice  
- Red vs Blue Team exercises  

---

## 📚 Resources

- [VirtualBox](https://www.virtualbox.org/)  
- [Microsoft Evaluation Center](https://www.microsoft.com/en-us/evalcenter)  
- [Splunk Free Trial](https://www.splunk.com/en_us/download/splunk-enterprise.html)  
- [Sysinternals Sysmon](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)  
- [SwiftOnSecurity Sysmon Config](https://github.com/SwiftOnSecurity/sysmon-config)  
- [Kali Linux](https://www.kali.org/)  

---

## 🏆 Final Notes

This **Active Directory + SOC Home Lab** provides a complete, isolated environment to **learn enterprise security monitoring, practice cyberattacks, and build SOC defense skills**.  

Snapshots are recommended before major changes so you can **rollback quickly** and **repeat attack/defense cycles**.  

---

### 🤝 Contributing
Pull requests are welcome! If you have additional security monitoring dashboards, AD attack scenarios, or SIEM integrations, feel free to share.  

---

### 📜 License
This project is for **educational purposes only**. Use responsibly.  
