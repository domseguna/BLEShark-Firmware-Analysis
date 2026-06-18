# BLEShark Nano v0.8 Firmware Analysis

## Overview
Reverse engineering analysis of the BLEShark Nano v0.8 closed-source firmware using Ghidra. The BLEShark Nano is an ESP32-C3 (RISC-V) based wireless pentesting tool.

## Tools Used
- Ghidra 12.1
- Architecture: RISC-V RV32IMC Little Endian
- Firmware: BLEShark v0.8 (1.64MB)

## Methodology
1. Downloaded firmware.bin from official GitHub releases
2. Loaded into Ghidra as Raw Binary
3. Set architecture to RISC-V RV32IMC
4. Ran auto-analysis
5. Analysed defined strings

## Key Findings

### OTA Update Mechanism
- Device checks for updates via GitHub API
- Downloads firmware directly from public GitHub repo
- No apparent signature verification found in strings

### Captive Portal
- Fake Google login page hardcoded in firmware
- Designed to harvest and store WiFi credentials

### Hardcoded Bad-BT Scripts
- Pre-loaded attack scripts targeting Windows machines
- Includes credential harvesting and prank payloads

## Screenshots
