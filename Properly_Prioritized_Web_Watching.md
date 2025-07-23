# Challenge Report: Properly Prioritized Web Watching  
**Course:** CORe 463/563  
**Student:** Ian Sweet  
**Email:** iansweet315@u.boisestate.edu  

---

## Challenge Overview

This challenge focuses on monitoring and identifying suspicious internal web traffic to the Joomla server (`172.16.10.100`). The objective was to extract details about IP addresses, browsers, and operating systems that accessed the server.

---

## Systems Involved

- **Prod-Joomla**: `172.16.10.100` (Web server)
- **Security-Desk**: `172.16.20.55` (Used for capturing traffic)
- **Workstation-Desk**: `172.16.20.60` (Firefox, Edge)
- **Fileshare**: `172.16.30.100` (Firefox)
- **Domain Controller**: `172.16.30.55` (Internet Explorer 11)

---

## Configuration & Log Analysis

1. Logged into Joomla server.
2. Edited Apache log config using `nano`:
```bash
sudo nano /etc/apache2/sites-enabled/joomla.conf
```
3. Inserted custom LogFormat:
```apache
LogFormat "%h %l %u %t \"%r\" %>s %O \"%{Referer}i\" \"%{User-Agent}i\"" combined
```
4. Restarted Apache:
```bash
sudo systemctl restart apache2
sudo apachectl configtest
```
5. Tail logs to monitor:
```bash
tail -f /var/log/apache2/joomla-access_log
```

---

## Submissions Verified

| IP Address     | Browser        | Version      | OS       | OS Version |
|----------------|----------------|--------------|----------|-------------|
| 172.31.2.26    | QtWebEngine    | 5.12.2       | Linux    | N/A         |
| 172.31.2.27    | Safari         | 12.1         | MacOS    | 10.14.1     |
| 172.31.2.28    | Chrome         | 70.0.3538    | Windows  | 10          |
| 172.31.2.29    | Firefox        | 66.0         | SunOS    | N/A         |

---

## Reflection

The most challenging part was interpreting User-Agent strings, especially those like QtWebEngine. It took trial and error to align correct format and values. Restarting Apache and validating log entries was essential for ensuring accurate capture.

The lab reinforced hands-on skills in:
- Web server logging
- Custom Apache configuration
- Manual log analysis and user-agent parsing
