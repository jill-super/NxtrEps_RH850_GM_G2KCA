---
title: "General Motors Road Wheel Input Qualifier — GmRoadWhlInQlfr MDD"
description: "Converted Design / Integration Document from GmRoadWhlInQlfr_MDD.docx (DOCX, 104 KB)."
---

:::note
Converted from `CF018A_GmRoadWhlInQlfr_Impl/doc/GmRoadWhlInQlfr_MDD.docx` (Design / Integration Document; original DOCX, about 104 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CF018A_GmRoadWhlInQlfr_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

GmRoadWhlInQlfr

March 2, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	GmRoadWhlInQlfr High-Level Description	5

2	Design details of software module	6

2.1	Graphical representation of GmRoadWhlInQlfr	6

2.2	Data Flow Diagram	6

2.2.1	Component level DFD	6

2.2.2	Function level DFD	6

3	Constant Data Dictionary	7

3.1	Program (fixed) Constants	7

3.1.1	Embedded Constants	7

4	Software Component Implementation	8

4.1	Sub-Module Functions	8

4.1.1	Init: GmRoadWhlInQlfrInit1	8

4.1.1.1	Design Rationale	8

4.1.1.2	Module Outputs	8

4.1.2	Per: GmRoadWhlInQlfrPer1	8

4.1.2.1	Design Rationale	8

4.1.2.2	Store Module Inputs to Local copies	8

4.1.2.3	(Processing of function)………	8

4.1.2.4	Store Local copy of outputs into Module Outputs	8

4.2	Server Runables	8

4.3	Interrupt Functions	8

4.4	Module Internal (Local) Functions	8

4.4.1	Local Function #1	8

4.4.1.1	Design Rationale	9

4.4.1.2	Processing	9

4.4.2	Local Function #2	9

4.4.2.1	Design Rationale	9

4.4.2.2	Processing	9

4.4.3	Local Function #3	9

4.4.3.1	Design Rationale	10

4.4.3.2	Processing	10

4.5	GLOBAL Function/Macro Definitions	10

5	Known Limitations with Design	11

6	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

GmRoadWhlInQlfr High-Level Description

Refer FDD

Design details of software module

Graphical representation of GmRoadWhlInQlfr

Data Flow Diagram

Refer FDD

Component level DFD

Refer FDD

Function level DFD

Refer FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Refer DataDict.m for constants

Software Component Implementation

Sub-Module Functions

Refer FDD

Init: GmRoadWhlInQlfrInit1

Design Rationale

Refer FDD 

Module Outputs

Refer FDD

Per: GmRoadWhlInQlfrPer1

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

* LeWhlFrqVld_Cnt_T_logl,  * WhlLeFrq_Hz_T_f32, *LeFrqOutOfRng_Cnt_T_logl, *LeFrqChgOutOfRng_Cnt_T_logl and *LeWhlDiagFlg_Cnt_T_logl  are outputs of this function

Design Rationale

Implementation of "Chk Curr and Prev LeWhlDstTiStamp" block

Processing

Refer FDD

Local Function #2

* RiWhlFrqVld_Cnt_T_logl,  * WhlRiFrq_Hz_T_f32, *RiFrqOutOfRng_Cnt_T_logl, *RiFrqChgOutOfRng_Cnt_T_logl and *RiWhlDiagFlg_Cnt_T_logl  are outputs of this function

Design Rationale

Implementation of "Chk Curr and Prev RiWhlDstTiStamp" block

Processing

Refer FDD

Local Function #3

Design Rationale

Implementation of "NTC Diag" block and immediately preceding logic

Processing

Refer FDD

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
Initial Version | N. Saxton | 1.0 | 02-Mar-2016
Function Name | CalcLeWhlFrqAndFrqVld | Type | Min | Max
Arguments Passed | WhlRotlStsTiStampResl_SecPerCnt_T_f32 | Float32 | 2e-09 | 4.084e-06
 | WhlLeDstPlsCntr_Cnt_T_u16 | Uint16 | 0 | 1023
 | WhlLeDstTiStamp_Cnt_T_u16 | Uint16 | 0 | 65535
 | WhlPlsPerRev_CntPerRoadWhlRev_T_u08 | Uint08 | 1 | 127
 | *LeWhlFrqVld_Cnt_T_logl | Boolean | FALSE | TRUE
 | *WhlLeFrq_Hz_T_f32 | Float32 | 0.01 | 60
 | *LeFrqOutOfRng_Cnt_T_logl | Boolean | FALSE | TRUE
 | *LeFrqChgOutOfRng_Cnt_T_logl | Boolean | FALSE | TRUE
 | *LeWhlDiagFlg_Cnt_T_logl | Boolean | FALSE | TRUE
Function Name | CalcRiWhlFrqAndFrqVld | Type | Min | Max
Arguments Passed | WhlRotlStsTiStampResl_SecPerCnt_T_f32 | Float32 | 2e-09 | 4.084e-06
 | WhlRiDstPlsCntr_Cnt_T_u16 | Uint16 | 0 | 1023
 | WhlRiDstTiStamp_Cnt_T_u16 | Uint16 | 0 | 65535
 | WhlPlsPerRev_CntPerRoadWhlRev_T_u08 | Uint08 | 1 | 127
 | *RiWhlFrqVld_Cnt_T_logl | Boolean | FALSE | TRUE
 | *WhlRiFrq_Hz_T_f32 | Float32 | 0.01 | 60
 | *RiFrqOutOfRng_Cnt_T_logl | Boolean | FALSE | TRUE
 | *RiFrqChgOutOfRng_Cnt_T_logl | Boolean | FALSE | TRUE
 | *RiWhlDiagFlg_Cnt_T_logl | Boolean | FALSE | TRUE
Function Name | NTCDiag | Type | Min | Max
Arguments Passed | LeWhlDiagFlag_Cnt_T_logl | Boolean | FALSE | TRUE
 | RiWhlDiagFlag_Cnt_T_logl | Boolean | FALSE | TRUE
 | LeFrqOutOfRng_Cnt_T_logl | Boolean | FALSE | TRUE
 | RiFrqOutOfRng_Cnt_T_logl | Boolean | FALSE | TRUE
 | LeFrqChgOutOfRng_Cnt_T_logl | Boolean | FALSE | TRUE
 | RiFrqChgOutOfRng_Cnt_T_logl | Boolean | FALSE | TRUE
