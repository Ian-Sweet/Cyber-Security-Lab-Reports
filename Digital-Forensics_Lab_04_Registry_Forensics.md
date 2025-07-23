# Lab 04: Registry Forensics

**Course:** CPS 403 – Recovery and Forensics  
**University:** Boise State University  
**Student:** Ian Sweet  
**Location:** Boise, Idaho USA  
**Email:** iansweet315@u.boisestate.edu  

## Examination Task

The goal of this lab was to extract and analyze Windows registry hives from a disk image to identify user activity and system configuration data. This included use of FTK Imager and RegRipper to parse hives like NTUSER.DAT, SYSTEM, and SOFTWARE.

## Steps Taken

1. Loaded forensic disk image `C Drive.E01` in FTK Imager.
2. Verified hash values for image integrity.
3. Located NTUSER.DAT and exported it with .LOG file.
4. Exported SYSTEM, SOFTWARE, SAM, and SECURITY hives.
5. Parsed hives with RegRipper using matching profiles.
6. Generated text reports for analysis of artifacts.
7. Reviewed output for user actions, USB history, and config data.

## Forensic Analysis

- NTUSER.DAT revealed documents, UserAssist and TypedURLs data.
- SYSTEM hive included hostname, shutdown times, USB history.
- SOFTWARE confirmed default browser and System Restore state.
- SAM displayed login history and password reset info.

## Results

Registry data established a credible timeline, confirmed user activity, and documented USB device usage. These findings reinforced the importance of registry analysis in forensic investigations.

## Exhibits

- Evidence verification.
- Registry file extraction screenshots.
- RegRipper output showing parsed artifacts.
