---
title: "Handwheel Ag0 Measurement — HwAg0Meas MDD"
description: "Converted Design / Integration Document from HwAg0Meas_MDD.docx (DOCX, 207 KB)."
---

:::note
Converted from `CM690A_HwAg0Meas_Impl/doc/HwAg0Meas_MDD.docx` (Design / Integration Document; original DOCX, about 207 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM690A_HwAg0Meas_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

HwAg0Meas

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Change History

Table of Contents

Introduction

Purpose

Scope

HwAg0Meas High-Level Description

Refer to FDD

Design details of software module

Graphical representation of HwAg0Meas

Data Flow Diagram

Component level DFD

Refer FDD

Function level DFD

Refer FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Initialization sub-module {_Init()}

 HwAg0MeasInit1  (Refer FDD for details)

Periodic sub-module {_Per()}

HwAg0MeasPer1  (Refer FDD for details)

Periodic sub-module {_Per()}

HwAg0MeasPer2  (Refer FDD for details)

Periodic sub-module {_Per()}

HwAg0MeasPer3  (Refer FDD for details)

Periodic sub-module {_Per()}

HwAg0MeasPer4  (Refer FDD for details)

Periodic sub-module {_Per()}

HwAg0MeasPer5  (Refer FDD for details)

Design Rationale:

The implementation brings in the block “HwAg0Final” inside the  True Condition of the “finalAbsAg”  as the other error condition will just retain the previous value and rolling counter will not change. It saves extra instructions in the implementation to the match the FDD. Final Functionality is still the same.

Interrupt Service Routines

None

Server Runnable Functions

Server Runnable: HwAg0MeasHwAg0AutTrim

Refer FDD for details

Server Runnable: HwAg0MeasHwAg0ClrTrim

Refer FDD for details

Server Runnable: HwAg0MeasHwAg0ReadTrim

Refer FDD for details

Server Runnable: HwAg0MeasHwAg0TrimPrfmdSts

Refer FDD for details

Server Runnable: HwAg0MeasHwAg0WrTrim

Refer FDD for details

Module Internal (Local) Functions

Local Function #1

Description

The implementation deviates from the FDD block “Intpn” block.   The implementation finds the minimum of  absolute values of the difference between HwAg0Step with all the values from the Calibration table and find the index  associated with minimum value of the difference in the calibration table. 

Transition Functions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

Roll Over is intentional for 

(*Rte_Pim_HwAg0PrevRollCnt). 

Thus counter acts in circular

Abbreviations and Acronyms

Glossary

Note: Terms and definitions from the source “Nexteer Automotive” take precedence over all other definitions of the same term.  Terms and definitions from the source “Nexteer Automotive” are formulated from multiple sources, including the following:

ISO 9000

ISO/IEC 12207

ISO/IEC 15504

Automotive SPICE® Process Reference Model (PRM)

Automotive SPICE® Process Assessment Model (PAM)

ISO/IEC 15288

ISO 26262

IEEE Standards

SWEBOK

PMBOK

Existing Nexteer Automotive documentation

References

Description | Author | Version | Date
Initial Version | Selva Sengottaiyan | 1.0 | 21-July-2015
Updated for V1.5.0 | Selva Sengottaiyan | 2.0 | 9-Sep-2015
 |  |  | 
 |  |  | 
Constant Name | Value
MAXWAITININ_MICROSEC_U32 | ((uint32)2U)
DATAAVLMAXWAIT_MICROSEC_U32 | ((uint32)300U)
COMSTSMAXWAIT_MICROSEC_U32 | ((uint32)5U)
PRTCLFLTMASK_CNT_U32 | 0xFEU
SNSRIDMASK_CNT_U08 | 0x00FU
MSGSTSMASK_CNT_U08 | 0x01U
COMSTSMASK_CNT_U32 | 0x30000000UL
DATAMASK_CNT_U16 | 0xFFF0U
Function Name | CalcHwAgIdx | Type | Min | Max
Arguments Passed | HwAgStep_HwDeg_T_f32 | float32 | -900 | 900
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
Return Value | Index_Cnt_T_u08 | uint16 | 0 | 22
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
