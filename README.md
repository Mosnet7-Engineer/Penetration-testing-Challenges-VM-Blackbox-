# Challenge VM #1 – Exploitation Walkthrough

**Author:** Moses Kunfah  
**Target:** Ubuntu 12.04 vulnerable machine (10.0.0.8)  
**Objective:** Gain root access and capture the flag from `/root/root.txt`  

## 🔍 Overview
This lab exercise demonstrates a real-world exploitation scenario using:
- Shellshock (CVE-2014-6271)
- Privilege escalation via Dirty COW (CVE-2016-5195)

## 🧭 Attack Flow
1. Reconnaissance (Netdiscover, Nmap)
2. Enumeration (Gobuster, Nikto)
3. Shellshock Exploitation for reverse shell
4. Dirty COW privilege escalation
5. Root access and flag retrieval

## 📸 Screenshots
See `/screenshots` folder.

## 🧪 Tools Used
- Nmap
- Gobuster
- Nikto
- Python, Netcat
- Dirty COW exploit

## 📄 References
- [CVE-2014-6271](https://nvd.nist.gov/vuln/detail/CVE-2014-6271)
- [CVE-2016-5195](https://www.exploit-db.com/exploits/40839)
- [Nmap Documentation](https://nmap.org/book/man.html)
- [Nikto Web Scanner](https://github.com/sullo/nikto)
