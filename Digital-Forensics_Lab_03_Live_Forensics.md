# Lab 03: Live Forensics

**Course:** CPS 403 – Recovery and Forensics  
**University:** Boise State University  
**Student:** Ian Sweet  
**Location:** Boise, Idaho USA  
**Email:** iansweet315@u.boisestate.edu  

## Examination Task

The objective of this lab is to conduct a live forensic analysis of a running Windows system using DEFT's Digital Advanced Recovery Toolkit (DART). The goal is to capture volatile and semi-volatile data, system configuration, and user activity without modifying the original system.

## Steps Taken

1. Launched DEFT's DART tool and prepared evidence folder on E: drive.
2. Used Drive Manager to collect disk details.
3. Loaded PhysicalDrive0 in FTK Imager and navigated user directories.
4. Scanned with TreeSizeFree and identified large user files.
5. Ran WinAudit and saved HTML report to external storage.
6. Extracted browser history with BrowsingHistoryView.
7. Ensured all artifacts were saved externally.
8. Verified evidence integrity and closed tools cleanly.

## Exhibits

- DART interface and folder structure.
- Disk details from Drive Manager.
- User directory in FTK Imager.
- TreeSizeFree file scan results.
- WinAudit and browser history reports.
