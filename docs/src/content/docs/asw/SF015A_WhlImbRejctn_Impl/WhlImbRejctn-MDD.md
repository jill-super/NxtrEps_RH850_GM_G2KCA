---
title: "Wheel Imbalance Rejection — WhlImbRejctn MDD"
description: "Converted Design / Integration Document from WhlImbRejctn_MDD.docx (DOCX, 109 KB)."
---

:::note
Converted from `SF015A_WhlImbRejctn_Impl/doc/WhlImbRejctn_MDD.docx` (Design / Integration Document; original DOCX, about 109 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF015A_WhlImbRejctn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

WhlImbRejctn

Version: 

, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Matt Leser,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	WhlImbRejctn High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of WhlImbRejctn	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	8

4	Constant Data Dictionary	9

4.1	Program (fixed) Constants	9

4.1.1	Embedded Constants	9

5	Software Component Implementation	10

5.1	Sub-Module Functions	10

5.1.1	Init: WhlImbRejctnInit1	10

5.1.1.1	Design Rationale	10

5.1.1.2	Module Outputs	10

5.1.2	Per: WhlImbRejctnPer1	10

5.1.2.1	Design Rationale	10

5.1.2.2	Store Module Inputs to Local copies	10

5.1.2.3	(Processing of function)………	10

5.1.2.4	Store Local copy of outputs into Module Outputs	10

5.1.3	Per: WhlImbRejctnPer2	10

5.1.3.1	Design Rationale	10

5.1.3.2	Store Module Inputs to Local copies	10

5.1.3.3	(Processing of function)………	10

5.1.3.4	Store Local copy of outputs into Module Outputs	10

5.2	Server Runables	10

5.3	Interrupt Functions	10

5.4	Module Internal (Local) Functions	11

5.4.1	Local Function #1	11

5.4.1.1	Description	11

5.4.2	Local Function #2	11

5.4.2.1	Description	11

5.4.3	Local Function #3	12

5.4.3.1	Description	12

5.4.4	Local Function #4	12

5.4.4.1	Description	12

5.4.5	Local Function #5	12

5.4.5.1	Description	12

5.4.6	Local Function #6	13

5.4.6.1	Description	13

5.4.7	Local Function #7	13

5.4.7.1	Description	13

5.4.8	Local Function #8	13

5.4.8.1	Description	14

5.4.9	Local Function #9	14

5.4.9.1	Description	14

5.4.10	Local Function #10	14

5.4.10.1	Description	14

5.4.11	Local Function #11	14

5.4.11.1	Description	14

5.4.12	Local Function #12	14

5.4.12.1	Description	15

5.4.13	Local Function #13	15

5.4.13.1	Description	15

5.5	GLOBAL Function/Macro Definitions	15

6	Known Limitations with Design	16

7	UNIT TEST CONSIDERATION	17

Appendix A	Abbreviations and Acronyms	18

Appendix B	Glossary	19

Appendix C	References	20

Introduction

Purpose

Scope

WhlImbRejctn High-Level Description

Refer to FDD

Design details of software module

Graphical representation of WhlImbRejctn

Data Flow Diagram

Refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

For other constants, refer .m file.

Local Constants

Software Component Implementation

Sub-Module Functions

Init: WhlImbRejctnInit1

Design Rationale

Refer FDD 

Module Outputs

Refer FDD

Per: WhlImbRejctnPer1

Design Rationale

Refer FDD 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Per: WhlImbRejctnPer2

Design Rationale

Refer FDD 

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

Description

‘UGR’ filter implementation. ‘Ugr1_MotRadPerSec_T_f32’ and ‘Ugr2_MotRadPerSec_T_f32’ corresponds to PIMs used in internal calculations.

Local Function #2

Description

"Determine Enabled Amt" block implementation. In determination of ‘DistbnMagEnadPrev’, ‘ScaleL’ and ‘ScaleR’ values, some if-else loops were combined in software for optimization. 

*Enable_Uls_T_f32 is an output of this function.

Local Function #3

Description

"Enable Ramp" block implementation.

Local Function #4

Description

"DistMagL/DistMagR" block implementation. ‘PeakPrev_Uls_T_f32’ is a PIM used in the internal implementation. 

‘LePeakPrev’ is output of this function.

Local Function #5

Description

"Active Rejection Command " block implementation. “WhlImbRejctnAmp_MtrNm_T_f32” is the output of this function.

PIMs ‘StordValLe’ and ‘StordValRi’ directly used in the software for signals ‘FiltWhlSpdLScld’ and ‘FiltWhlSpdRScld’ in the FDD. 

Local Function #6

Description

"Filter1 / Filter2 " block implementation. 

Local Function #7

Description

'Set NTC Block' implementation. 

Local Function #8

Description

"MaxMagDiag" block implementation.

Local Function #9

Description

" DcTrendDiag" block implementation.

Local Function #10

Description

' FrequencyDiag ' block implementation. 

Local Function #11

Description

" WhlSpdCorrDiag" block implementation.

Local Function #12

Description

"Elapsed Timer" block implementation. 

FltStsTrue_Cnt_T_lgc - Fault condition current status

PrevFltStsTrue_Cnt_T_lgc - Fault condition previous status (PIM) 

RefTi_Sec_T_u32 - Reference Timer (PIM)

Local Function #13

Description

"Flt Recovery" block implementation. Elapsed time is passed as argument

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

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
Initial Version | Sankardu Varadapureddi | 1 | 4-Mar-2016
Updated for FDD ver 1.2.0 | Sankardu Varadapureddi | 2 | 21-Mar-2016
Updated for FDD ver 1.6.0 | Matt Leser | 3 (Version 4 in Synergy) | 21-Sep-2016
Updated version number to match Synergy Database | Matt Leser | 6 | 28-Sep-2016
 |  |  | 
Constant Name | Resolution | Units | Value
MAXMGNMASK_CNT_U08 | 1 | Cnt | 1
QUALMASK_CNT_U08 | 1 | Cnt | 2
DCTRENDMASK_CNT_U08 | 1 | Cnt | 4
FREQDIAGCMASK_CNT_U08 | 1 | Cnt | 8
WHLSPDCORRLNMASK_CNT_U08 | 1 | Cnt | 16
MINSTOMILLISEC_ULS_F32 | 1 | Cnt | 60000
Function Name | UGRFilOutp | Type | Min | Min | Max
Arguments Passed | Y_Hz_T_f32 | float32 | -8.8 | 376.991118 | 376.991118
 | FreqEst_Hz_T_f32 | float32 | 0.005 | 60 | 60
 | PoleMag_Uls_T_f32 | float32 | 0 | 1 | 1
 | * Ugr1_MotRadPerSec_T_f32 | float32 | 0 | 256 | 256
 | * Ugr2_MotRadPerSec_T_f32 | float32 | 0 | 256 | 256
Return Value | YFild_Hz_T_f32 | float32 | 0 | 127 | 127
Function Name | DtrmnEnadAmnt | Type | Min | Min | Max
Arguments Passed | FreqEstAvg_Hz_T_f32 | float32 | 0.005 | 60 | 60
 | WhlSpdLFilt_MotRadPerSec_T_f32 | float32 | -100 | 100 | 100
 | WhlSpdRFilt_MotRadPerSec_T_f32 | float32 | -100 | 100 | 100
 | VehSpd_Kph_T_f32 | float32 | 0 | 511 | 511
 | VehSpdVld_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
 | WhlImbRejctnCustEna_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
 | WhlImbRejctnDi_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
 | SysSt_Cnt_T_enum | SysSt1 | SYSST_DI | SYSST_WRMININ | SYSST_WRMININ
 | *Enable_Uls_T_f32 | float32 | 0 | 1 | 1
Return Value | WhlImbRejctnActv_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
