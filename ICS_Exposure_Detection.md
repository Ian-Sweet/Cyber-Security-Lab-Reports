# Alarmingly Available ICS - Exposure Detection  
**Course:** CORe 463/563  
**Student:** Ian Sweet  
**Email:** iansweet315@u.boisestate.edu  

---

## Overview  
This lab involved investigating unauthorized remote access to Zapp Substation 434. Employees reported suspicious activity related to public camera feeds and potential firewall misconfiguration.

---

## Key Findings  

1. Identified firewall admin panel exposed to the public via `172.31.3.2:443` (HTTPS).
2. NAT rule forwarding port 8080 to internal IP camera `192.168.30.32:80`.
3. Verified:
   - Substation Firewall exposed
   - IP Camera publicly accessible

---

## Remediation Steps  

1. Accessed Workstation and verified no access to `192.168.30.16` (HMI) or `.32` (Cam).
2. Detected public availability of firewall login (expired self-signed cert).
3. Logged into pfSense and reviewed NAT rules.
4. Identified forwarding rule exposing internal camera.
5. Documented both exposures in challenge form.

---

## Outcome  
Challenge completed after identifying both misconfigured firewall exposures. Key lesson: internal ICS systems must not be accessible over public networks without controls.
