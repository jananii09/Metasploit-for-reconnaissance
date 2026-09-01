# Metasploit for Reconnaissance in Pentesting

---
## NAME: JANANI SHREE A
## REG NO: 212224100023
---
# AIM

To get introduced to the Metasploit Framework and perform reconnaissance in penetration testing.

---

# DESIGN STEPS

### Step 1

Install Kali Linux either in partition, virtual machine, or live mode.

### Step 2

Investigate the various categories of penetration testing tools.

### Step 3

Open terminal and execute Kali Linux commands.

---

# EXECUTION STEPS AND OUTPUT

## 1. Finding the IP Address of the Attacker System

### Command

```bash
ifconfig
```

### Output

<img width="848" height="367" alt="5 -1" src="https://github.com/user-attachments/assets/145a5ac7-6b4b-4329-8664-f61af5b385d1" />


### Observation

* Shows network interfaces `eth0` and `lo`
* `eth0` contains IPv4 address `10.0.2.15`
* Loopback interface `lo` uses `127.0.0.1`
* No packet loss or collisions detected

---

# 2. Invoking Metasploit Console

### Command

```bash
msfconsole
```

### Output

<img width="883" height="351" alt="5-2" src="https://github.com/user-attachments/assets/e8db2f10-cc51-43c9-8beb-5db4f305bb71" />


### Observation

* Metasploit Framework launched successfully
* Exploits, payloads, and auxiliary modules loaded
* Framework maintained by Rapid7

---

# 3. Displaying Help Menu

### Command

```bash
help
```

### Output

<img width="1732" height="943" alt="5-3" src="https://github.com/user-attachments/assets/5c732c7d-04f4-4b19-9452-cf87c99d721b" />


### Observation

* Help menu displays available Metasploit commands
* Includes module handling, sessions, routing, and plugins
* Useful for framework navigation

---

# 4. Port Scanning

### Command

```bash
nmap -sT 10.0.2.0/24 -p1-1000
```

### Output

<img width="746" height="449" alt="5-4" src="https://github.com/user-attachments/assets/444015c9-ad8c-474a-a8f0-e9558f65231e" />


### Observation

* TCP scan checks systems in local network range
* Active hosts detected successfully
* Ports identified as open, filtered, or closed

---

# 5. Database Initialization

### Command

```bash
sudo msfdb reinit
```

### Output

<img width="1098" height="326" alt="5-5" src="https://github.com/user-attachments/assets/d52f7444-bd64-4b37-9c79-32f7a097c9d3" />


### Observation

* PostgreSQL database initialized successfully
* Metasploit database configuration completed
* Initial schema generated

---

# 6. Searching Microsoft Exploits

### Command

```bash
search name:Microsoft type:exploit
```

### Output

<img width="808" height="421" alt="5-6" src="https://github.com/user-attachments/assets/0f17832b-854d-43b2-b37e-ca889f868a38" />


### Observation

* Displays Microsoft exploit modules
* Includes IIS and SQL-related vulnerabilities
* Shows exploit rank and disclosure dates

---

# 7. Searching MySQL Auxiliary Modules

### Command

```bash
search type:auxiliary mysql
```

### Output

<img width="721" height="190" alt="5-7" src="https://github.com/user-attachments/assets/f6532272-45be-4b6a-bdcb-ff1590d5217b" />


### Observation

* Lists MySQL auxiliary modules
* Includes login scanners and version scanners
* Useful for enumeration and testing

---

# 8. Loading MySQL Version Scanner

### Command

```bash
use auxiliary/scanner/mysql/mysql_version
```

### Output

<img width="1909" height="901" alt="5-8" src="https://github.com/user-attachments/assets/d8e24827-7fa4-40c6-8ef1-cba245491f3a" />


### Observation

* MySQL version scanner module loaded successfully
* Targets remote MySQL services
* Uses default port 3306

---

# 9. Configuring Target Host

### Commands

```bash
set RHOSTS 10.0.2.15
run
```

### Output

<img width="1490" height="462" alt="5-9" src="https://github.com/user-attachments/assets/c2e9f4a8-cf17-4f10-81ce-3ab85aadc325" />


### Observation

* Target host configured successfully
* Module executed against specified host
* Scan completed without interruption

---

# 10. Loading MySQL Login Module

### Command

```bash
use auxiliary/scanner/mysql/mysql_login
```

### Output

<img width="1095" height="601" alt="5-10" src="https://github.com/user-attachments/assets/60dadd48-512d-4d6f-96fe-e6e3644c95b9" />


### Observation

* MySQL login module configured
* Supports brute-force login attempts
* Allows password wordlists and blank password testing

---

# 11. Configuring Wordlist and Running Module

### Commands

```bash
set PASS_FILE /usr/share/wordlists/rockyou.txt.gz
set RHOSTS 10.0.2.15
set BLANK_PASSWORDS true
run
```

### Output

<img width="1095" height="601" alt="5-10" src="https://github.com/user-attachments/assets/593d874f-42da-4685-9dc7-2d17ec8c0b87" />


### Observation

* Wordlist configured successfully
* Blank password checking enabled
* Authentication attempts performed against target host

---

# RESULT

Thus the Metasploit Framework for reconnaissance in penetration testing was studied and executed successfully.
