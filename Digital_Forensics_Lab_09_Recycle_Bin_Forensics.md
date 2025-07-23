# CPS403 Lab 09 – Recycle Bin Forensics

**Author:** Ian Sweet  
**Course:** CPS 403 – Recovery and Forensics  
**University:** Boise State University  
**Email:** iansweet315@u.boisestate.edu

## Examination Task

This lab explored the forensic artifacts left behind by the Windows Recycle Bin. The goal was to extract and interpret `$I` and `$R` files to reconstruct original filenames, deletion times, and file paths. Autopsy and FTK Imager were used to examine an `.E01` image and perform detailed artifact recovery.

## Steps Taken

- Opened Autopsy and started a new case with the challenge `.E01` image.
- Navigated to `$Recycle.Bin` and sorted files by extension and name.
- Identified `$I` files to extract deletion timestamp and original metadata.
- Matched each `$I` file with corresponding `$R` file.
- Documented original file paths and confirmed deletion dates.
- Cross-referenced user folder to assess context of file deletion.
- Opened image in FTK Imager to view file paths and timestamp formats.
