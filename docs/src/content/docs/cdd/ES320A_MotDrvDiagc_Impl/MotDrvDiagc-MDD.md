---
title: "Motor Driver Diagnostic — MotDrvDiagc MDD"
description: "Converted Design / Integration Document from MotDrvDiagc_MDD.docx (DOCX, 106 KB)."
---

:::note
Converted from `ES320A_MotDrvDiagc_Impl/doc/MotDrvDiagc_MDD.docx` (Design / Integration Document; original DOCX, about 106 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES320A_MotDrvDiagc_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

MotDrvDiagc

Apr 18, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Sankardu Varadapureddi,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	MotDrvDiagc High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of MotDrvDiagc	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: MotDrvDiagcInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: MotDrvDiagcPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	10

5.4.1	Local Function #1	10

5.4.1.1	Design Rationale	10

5.4.1.2	Processing	10

5.5	GLOBAL Function/Macro Definitions	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

Introduction

Purpose

Scope

MotDrvDiagc High-Level Description

Refer to FDD

Design details of software module

Graphical representation of MotDrvDiagc

Data Flow Diagram

Refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: MotDrvDiagcInit1

Design Rationale

Refer FDD for the functionality. 

Module Outputs

Refer FDD

Per: MotDrvDiagcPer1

Design Rationale

In blocks ‘MeasdPhaFltChkABC’ and ‘MeasdPhaFltChkDEF’, inputs to filters are in integer datatypes. They are converted to float type in order to be compatible with filter SW library functions.

As per discussion with FDD owner, ‘BitsetStsA’ block sets bit 0 of ‘NtcStInfoA’. ‘BitsetStsA1’ sets bit 1 of ‘NtcStInfoA’. ‘DetermineBitsetA1’ block resets both bit0 and bit1.  Same is applicable for phase B (bits 2 and 3) and phase C (bits 4 and 5). 

In SW implementation, since NTC state info (NtcStInfoABC_Uls_T_u08) is initialized to ‘0’, clearing of state bits logic (DetermineBitsetA1) is not implemented. It is redundant. 

Same logic repeated in case of phase D, E and F signals. 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

‘BitMask_Cnt_u08’ takes only 0x01, 0x04 and 0x10. 

Processing

Determines ‘NTC State Info’ for Phase on time signals.  Corresponds to implementation of 'MeasdPhaFltChkABC' and ‘MeasdPhaFltChkDEF’ functional blocks.

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

None

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
Initial Version | Sankardu Varadapureddi | 1 | 19-Aug-2015
‘MotDrvDiagcInit1’ design rational updated | Sankardu Varadapureddi | 2 | 21-Aug-2015
Updating MDD to incorporate the changes in FDD 1.4.0 | Basavaraja Ganeshappa | 3 | 18-Apr-2016
Constant Name | Resolution | Units | Value
BITMASK0_CNT_U08 | 1 | Cnt | 0x01
BITMASK2_CNT_U08 | 1 | Cnt | 0x04
BITMASK4_CNT_U08 | 1 | Cnt | 0x10
MOTDRVERRMIN_NANOSEC_F32 | 1 | NoanoSec | 0.0F
MOTDRVERRMAX_NANOSEC_F32 | 1 | NoanoSec | 40000000.0F
Function Name | SetNtcStInfo | Type | Min | Max
Arguments Passed | PhaOnTiMeasd_NanoSec_T_u32 | uint32 | 0 | 4294967295
 | PhaOnTiSumExp_NanoSec_T_u32 | uint32 | 0 | 4294967295
 | Err_NanoSec_T_f32 | float32 | -3.4E+38 | +3.4E+38
 | BitMask_Cnt_u08 | uint8 | 0x01 | 0x10
 | *NtcStInfo_Uls_T_u08 | uint8 | 0x00 | 0x1F
Return Value | Flt_Uls_T_lgc | boolean | FALSE | TRUE
Abbreviation or Acronym | Description
 | 
 | 
