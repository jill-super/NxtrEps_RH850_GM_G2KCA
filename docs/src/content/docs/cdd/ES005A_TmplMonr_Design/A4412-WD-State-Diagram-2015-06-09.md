---
title: "Temperature Monitoring — A4412 WD State Diagram 2015 06 09"
description: "Converted Portable Document (vendor or generated report) from A4412 WD State Diagram 2015_06_09.pdf (PDF, 12 KB)."
---

:::note
Converted from `ES005A_TmplMonr_Design/Doc/A4412 WD State Diagram 2015_06_09.pdf` (Portable Document (vendor or generated report); original PDF, about 12 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES005A_TmplMonr_Design](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Off Idle Test Hunt Test Lock Running Hunt
Reflash Running
Watchdog
Power On One Clock 
Cycle
POE Low
POE High
Bad Pulses not 
Recieved
Test 
Complete
POE High
WD_F = 0
POE High
WD_F = 1
POE Low
No WD_RESTART
 WD_RESTART
 WD_RESTART
FLASH_MODE
No WD_RESTART
FLASH_MODE
FLASH_MODE
 WD_RESTART
tPS_DISABLE = 0
WD_F = 1
POE Low
tPS_DISABLE = 0
WD_F = 1
POE Low
 WD_RESTART
 WD_RESTART
FLASH_MODE
FLASH_MODE
 WD_RESTART
