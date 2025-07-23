# CPS403 Lab 06 – Keyword Search and Analysis

**Author:** Ian Sweet  
**Course:** CPS 403 – Recovery and Forensics  
**University:** Boise State University  
**Email:** iansweet315@u.boisestate.edu

## Examination Task

This lab involved conducting a forensic keyword search using Autopsy on a provided E01 disk image. Three types of keyword searches were performed: exact match, substring, and regular expression. The goal was to assess keyword effectiveness in identifying digital artifacts while maintaining forensic soundness.

## Steps Taken

- Launched CSI-Linux VM and opened Autopsy.
- Created a new case named `FOR_LAB_006_KWS`.
- Added the `FOR_LAB_006.E01` image for analysis.
- Enabled the Keyword Search Ingest Module and configured it with custom keywords.
- Used exact, substring, and regex match types for comparison.
- Stopped indexing at 30% to analyze intermediate results.
- Located keyword "hackersteam" in `channels.txt`.
- Used regex `hackerst.*` to capture variants.
- Documented and preserved findings with screen captures.

## Forensic Analysis

Autopsy’s keyword search module provided a powerful way to identify targeted data. Regular expressions enabled flexible matching, which can reduce time spent on variant searches. Keyword tuning was critical for reducing noise. Chain of custody was preserved using isolated environments and documented case handling.
