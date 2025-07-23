# Lab 02: Live Acquisition

**Course:** CPS 403 – Recovery and Forensics  
**University:** Boise State University  
**Student:** Ian Sweet  
**Location:** Boise, Idaho USA  
**Email:** iansweet315@u.boisestate.edu  

## Examination Task

The objective of this lab is to perform a live acquisition of volatile memory and system processes using Magnet Process Capture and Magnet RAM Capture. The goal is to isolate and preserve volatile data that could be lost upon shutdown, identify critical processes running in memory, and extract meaningful artifacts for analysis. This process supports real-world incident response scenarios where live memory acquisition is required.

## Steps Taken

1. Logged into WinOS and launched Magnet Process Capture.
2. Selected all `svchost.exe` processes for targeted capture.
3. Created an external output folder on the E: drive for process dumps.
4. Captured selected processes and verified export completion.
5. Opened Magnet RAM Capture and selected destination for output.
6. Completed a full RAM dump with 500MB segment size.
7. Used FTK Imager to carve a JPEG from a memory dump.
8. Analyzed memory artifacts using Redline (processes, drivers, timeline).

## Exhibits

- Magnet Process Capture screenshot.
- Process exports saved to external drive.
- RAM Capture segments.
- JPEG carved with FTK Imager.
- Redline memory analysis view.
