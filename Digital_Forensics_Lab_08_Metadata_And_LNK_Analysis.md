# CPS403 Lab 08 – Metadata and LNK File Analysis

**Author:** Ian Sweet  
**Course:** CPS 403 – Recovery and Forensics  
**University:** Boise State University  
**Email:** iansweet315@u.boisestate.edu

## Examination Task

This lab focused on analyzing file metadata and LNK shortcut artifacts using Autopsy and FTK Imager. The objective was to examine how user interaction with files is recorded through metadata timestamps and Windows shortcut files. This information aids in building timelines and understanding file access behavior.

## Steps Taken

- Launched CSI-Linux and opened Autopsy.
- Created new case and loaded provided `.E01` image.
- Used File Metadata module to explore document creation, access, and modification times.
- Identified relevant files in the user Downloads directory.
- Opened LNK shortcut directory in Autopsy and examined target file metadata.
- Compared timestamps to determine user interaction history.
- Used FTK Imager to verify evidence file contents and cross-check file structures.
