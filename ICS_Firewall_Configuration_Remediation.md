# Alarmingly Available ICS - Configuration Remediation  
**Course:** CORe 463/563  
**Student:** Ian Sweet  
**Email:** iansweet315@u.boisestate.edu  

---

## Overview  
Follow-up to the ICS exposure challenge. Tasked with remediating firewall configurations to prevent public access to the HMI (`192.168.30.16`).

---

## Actions Taken  

1. Logged into Workstation and attempted firewall access.
2. Verified need for VPN connection.
3. Accessed pfSense via `192.168.30.254`.
4. Reviewed and edited NAT port forwarding rules.
5. Created rule to redirect public port 8080 to internal host `192.168.30.24`.

---

## New Firewall Rule  

- **Interface:** WAN  
- **Protocol:** TCP  
- **Ports:** 8080 → 8080  
- **Target:** 192.168.30.24  
- **Label:** Web Forward  

---

## Outcome  
Configuration adjusted successfully. Lab verified desired state. Reinforced skills in NAT rule creation and pfSense interface navigation.
