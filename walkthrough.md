# Challenge VM #1 Walkthrough

## Author
Moses Kunfah

## Target
Ubuntu 12.04 vulnerable machine (10.0.0.8)

## Objective
Gain root access and capture the flag from `/root/root.txt`

---

## Step 1: Reconnaissance
Used `netdiscover` to identify target IP as `10.0.0.8`.  
Ran Nmap to scan for open ports:
- Port 22: SSH
- Port 80: Apache 2.2.22

## Step 2: Enumeration
- Ran Gobuster → discovered `/cgi-bin/`
- Ran Nikto → Shellshock found in `/cgi-bin/test`

## Step 3: Exploitation – Shellshock
- Crafted and sent reverse shell payload to `/cgi-bin/test`
- Python server hosted payload on port 8000
- Netcat listener received shell on port 4444
- Gained shell as `www-data`

## Step 4: Privilege Escalation – Dirty COW
- Used CVE-2016-5195 exploit (dirtycow.c)
- Compiled exploit, ran from target
- Escalated privileges to `root`

## Step 5: Root & Flag
- Upgraded shell using Python PTY
- Switched to user `firefart`
- Read `/root/root.txt`: `{Sum0-SunCSR-2020_r00t}`

---

## Conclusion
Successfully exploited Shellshock and escalated using Dirty COW to gain root access and retrieve the flag.

## References
- https://nvd.nist.gov/vuln/detail/CVE-2014-6271
- https://www.exploit-db.com/exploits/40839
- https://nmap.org/book/man.html
- https://github.com/sullo/nikto
- https://github.com/OJ/gobuster
