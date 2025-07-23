# Web Server Hardening - Pretty Safe Electronics  
**Course:** CORe 463/563  
**Student:** Ian Sweet  
**Email:** iansweet315@u.boisestate.edu  

---

## Overview  
This lab focused on securing remote web access to a production server. Hardened the Joomla web server (`172.16.10.100`) by deploying Fail2Ban and configuring Apache with OWASP CRS rules through ModSecurity.

---

## Hardening Steps  

1. SSH into Prod-Joomla from Security-Desk.
2. Updated and upgraded packages.
3. Installed and configured Fail2Ban:
   - Ignored Security-Desk IP
   - Enabled SSH brute-force protection
4. Installed and configured ModSecurity:
   - Enabled `SecRuleEngine`
   - Added OWASP CRS rules to Apache

---

## Apache Integration  

- Removed default ModSecurity rule includes.
- Included:
  - `crs-setup.conf`
  - All CRS rules in `rules/*.conf`

---

## Validation  

- Apache restarted successfully after changes.
- Confirmed rules loaded with `ls /etc/modsecurity/owasp-crs/rules | head`.

---

## Outcome  
Server hardened against web and SSH attacks while maintaining remote access. Successfully completed the challenge.
