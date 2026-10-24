# SBT-DF204: Case Study 3 - Memory Forensics Investigation

## Overview
This repository contains the complete documentation, evidence logs, reconstructed timelines, and final academic report for **Case Study 3** (`memdumpWin7.mem`). The investigation focuses on volatile memory artifact analysis to uncover unauthorized data exfiltration.

## Case Assets & Environment
* **Memory Image:** `memdumpWin7.mem` (1.0 GB)
* **SHA-256 Hash:** `500bc1ba8b5ffa8053b6213d7e7aae0c84c18cce541dc53a55887e6e5099495e`
* **OS Profile:** `Win7SP1x86`
* **Analysis Tool:** Volatility Framework 2.6.1

## Key Investigation Findings
* **Process Analysis:** Identified critical execution trails including Google Chrome (`chrome.exe`), SSH daemon (`sshd.exe`), and command shell usage (`cmd.exe`).
* **Device Artifacts:** Confirmed USB mass storage attachment via the `USBSTOR` registry key (`Disk&Ven_General&Prod_UDisk&Rev_5.00`) and drive mapping to volume `F:` via `MountPoints2`.
* **Exfiltration Proof:** Console logs (`cmdscan`/`consoles`) verified that the local user (`IEUser`) navigated into `Downloads` and executed `copy secret_file.docx F:` at 15:06:11 UTC, resulting in a successful file copy.

## Repository Structure
* `/evidence` - Working copies and raw command output records.
* `/report` - Final 8-part academic report structure, timeline tables, and evidence logs.
