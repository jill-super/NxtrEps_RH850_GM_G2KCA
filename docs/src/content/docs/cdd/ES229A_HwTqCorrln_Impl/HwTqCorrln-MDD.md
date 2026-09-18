---
title: "Handwheel Torque Correlation — HwTqCorrln MDD"
description: "Converted Design / Integration Document from HwTqCorrln_MDD.docx (DOCX, 154 KB)."
---

:::note
Converted from `ES229A_HwTqCorrln_Impl/doc/HwTqCorrln_MDD.docx` (Design / Integration Document; original DOCX, about 154 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES229A_HwTqCorrln_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

 HwTqCorrln

 , 201

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	HwTqCorrln & High-Level Description	4

2	Design details of software module	5

2.1	Graphical representation of HwTqCorrln	5

2.2	Data Flow Diagram	6

2.2.1	Component level DFD	6

2.2.2	Function level DFD	6

3	Constant Data Dictionary	7

3.1	Program (fixed) Constants	7

3.1.1	Embedded Constants	7

4	Software Component Implementation	8

4.1	Sub-Module Functions	8

4.1.1	Init: HwTqCorrlnInit1	8

4.1.2	Per: HwTqCorrlnPer1	8

4.1.3	Per: HwTqCorrlnPer2	8

4.1.4	Per: HwTqCorrlnPer3	8

4.2	Server Runables	8

4.3	Interrupt Functions	8

4.4	Module Internal (Local) Functions	8

4.4.1	Local Function #1	8

4.4.1.1	Design Rationale	8

4.4.1.2	Processing	8

4.4.2	Local Function #2	9

4.4.2.1	Design Rationale	9

4.4.2.2	Processing	9

4.5	GLOBAL Function/Macro Definitions	9

5	Known Limitations with Design	10

6	UNIT TEST CONSIDERATION	11

Appendix A	Abbreviations and Acronyms	12

Appendix B	Glossary	13

Appendix C	References	14

HwTqCorrln & High-Level Description

Refer FDD

Design details of software module

Refer FDD

Graphical representation of HwTqCorrln

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

Software Component Implementation

Refer FDD

Sub-Module Functions

Init: HwTqCorrlnInit1

Refer FDD

Per: HwTqCorrlnPer1

Refer FDD

Per: HwTqCorrlnPer2

Refer FDD

Per: HwTqCorrlnPer3

Refer FDD

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

None

Processing

Refer FDD CorrSigAvlChkRev1 State flow Chart

Local Function #2

Design Rationale

None

Processing

Refer FDD ImdtCorrlnChk block

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
Initial Version | SB | 1.0 | 04-Aug-2015
Updated to FDD v2.1.0 | NS | 2.0 | 07-Oct-2015
Anomaly EA4#1980 fixed | NS | 3.0 | 20-Oct-2015
 |  |  | 
Constant Name | Resolution | Units | Value
Refer .m file |  |  | 
HWTQCORRLNSTSSIGA_CNT_U08 | 1 | Cnt | 0x01
HWTQCORRLNSTSSIGB_CNT_U08 | 1 | Cnt | 0x02
HWTQCORRLNSTSSIGC_CNT_U08 | 1 | Cnt | 0x04
HWTQCORRLNSTSSIGD_CNT_U08 | 1 | Cnt | 0x08
MAXSTALL_CNT_U08 | 1 | Cnt | 255
HWTQIDPTSIGALL_CNT_U08 | 1 | Cnt | 4
HWTQIDPTSIGHALF_CNT_U08 | 1 | Cnt | 2
HWTQIDPTSIGNZERO_CNT_U08 | 1 | Cnt | 0
 |  |  | 
 |  |  | 
Function Name | CorrlnSigAvlChk | Type | Min | Max
Arguments Passed | SigRollgCnt_Cnt_T_u08 | uint8 | 0 | 255
 | SigQlfr_Cnt_T_enum | SigQlfr1 | SIGQLFR_NORES | SIGQLFR_FAILD
 | MaxStallCnt_Cnt_T_u08 | Uint8 | 0 | 255
 | * LstRollgCnt_Cnt_T_u08 | uint8 | 0 | 255
 | * StallCnt_Cnt_T_u08 | uint8 | 0 | 255
Return Value | SigAvl_Cnt_T_lgc | boolean | FALSE | TRUE
Function Name | ImdtCorrlnChk | Type | Min | Max
Arguments Passed | Sig1Avl_Cnt_T_lgc | Booelan | FALSE | TRUE
 | Sig2Avl_Cnt_T_lgc | Boolean | FALSE | TRUE
 | HwTq1_HwNwtMtr_T_f32 | Float32 | -10.0 | 10.0
 | HwTq2_HwNwtMtr_T_f32 | Float32 | -10.0 | 10.0
 | ImdtCorrlnChkFailThd_HwNwtMtr_T_f32 | Float32 | 0.0 | 20.0
 | ImdtCorrlnChkPassThd_HwNwtMtr_T_f32 | Float32 | 0.0 | 20.0
 | NtcNr_T_enum | Enum | 1 | 511
 | *CorrlnSigAPass_Cnt_T_lgc | Boolean | FALSE | TRUE
 | *CorrlnSigBPass_Cnt_T_lgc | Boolean | FALSE | TRUE
 | *ImdtCorrlnChk_Cnt_T_lgc | Boolean | FALSE | TRUE
Return Value | ChAImdtCorrlnChk_Cnt_T_lgc | boolean | FALSE | TRUE
