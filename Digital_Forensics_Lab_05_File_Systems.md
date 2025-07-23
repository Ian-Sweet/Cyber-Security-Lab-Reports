# CPS403 Lab 05 – File Systems

**Author:** Ian Sweet  
**Course:** CPS 403 – Recovery and Forensics  
**University:** Boise State University  
**Email:** iansweet315@u.boisestate.edu

## Examination Task

This lab focused on examining and comparing Volume Boot Records (VBRs) of FAT, NTFS, and exFAT file systems using HxD Hex Editor. The objective was to interpret sector sizes, cluster sizes, volume identifiers, and file system types. This exercise aimed to build low-level forensic skills and reinforce the importance of maintaining evidence integrity.

## Steps Taken

- Launched HxD and enabled the Data Inspector panel.
- Loaded the FAT-formatted image (NDG FAT Lab5.001) and navigated to Sector 63 to inspect OEM ID and metadata.
- Summarized FAT metadata including volume size, cluster size, and filesystem type.
- Analyzed NTFS-formatted evidence (NDG NTFS Lab5.001), verified OEM ID, and extracted key values.
- Opened exFAT image (NDG exFAT Lab5.001) and decoded exponential encodings.
- Compared how FAT, NTFS, and exFAT store metadata.
- Ensured read-only mode in HxD to preserve forensic soundness.
