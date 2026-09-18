---
title: "Handwheel Ag1 Measurement — HwAg1Meas MDD"
description: "Converted Design / Integration Document from HwAg1Meas_MDD.docx (DOCX, 192 KB)."
---

:::note
Converted from `CM670A_HwAg1Meas_Impl/doc/HwAg1Meas_MDD.docx` (Design / Integration Document; original DOCX, about 192 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM670A_HwAg1Meas_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

HwAg1Meas

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Change History

Table of Contents

1	Introduction	4

1.1	Purpose	4

1.2	Scope	4

2	HwAg1Meas High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of HwAg1Meas	6

3.2	Data Flow Diagram	6

3.2.1	Component level DFD	6

3.2.2	Function level DFD	6

4	Constant Data Dictionary	7

4.1	Program (fixed) Constants	7

4.1.1	Embedded Constants	7

5	Software Component Implementation	8

5.1.1	Sub-Module Functions	8

5.1.2	Interrupt Service Routines	8

5.1.3	Server Runnable Functions	9

5.1.4	Module Internal (Local) Functions	9

5.1.4.1	Local Function #1	9

5.1.4.2	Description	9

5.1.5	Transition Functions	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

Introduction

Purpose

MDD for HwAg1.

Scope

HwAg1Meas High-Level Description

Refer to FDD

Design details of software module

Graphical representation of HwAg1Meas

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

 HwAg1MeasInit1  (Refer FDD for details)

Periodic sub-module {_Per()}

HwAg1MeasPer1  (Refer FDD for details)

Periodic sub-module {_Per()}

HwAg1MeasPer2  (Refer FDD for details)

Periodic sub-module {_Per()}

HwAg1MeasPer3  (Refer FDD for details)

Periodic sub-module {_Per()}

HwAg1MeasPer4  (Refer FDD for details)

Periodic sub-module {_Per()}

HwAg1MeasPer5  (Refer FDD for details)

Design Rationale:

The implementation brings in the block “HwAg1Final” inside the True Condition of the “finalAbsAg”  as the other error condition will just retain the previous value and rolling counter will not change. It saves extra instructions in the implementation to the match the FDD. Final Functionality is still the same.

Interrupt Service Routines

None

Server Runnable Functions

Server Runnable: HwAg1MeasHwAg1AutTrim

Refer FDD for details

Server Runnable: HwAg1MeasHwAg1ClrTrim

Refer FDD for details

Server Runnable: HwAg1MeasHwAg1ReadTrim

Refer FDD for details

Server Runnable: HwAg1MeasHwAg1TrimPrfmdSts

Refer FDD for details

Server Runnable: HwAg1MeasHwAg1WrTrim

Refer FDD for details

Module Internal (Local) Functions

Local Function #1

Description

The implementation deviates from the FDD block “Intpn” block.   The implementation finds the minimum of  absolute values of the difference between HwAg1Step with all the values from the Calibration table and find the index  associated with minimum value of the difference in the calibration table. 

Transition Functions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

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
Updated to v1.2.0 of the FDD | Selva Sengottaiyan | 2.0 | 11-Sep-15
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
