---
title: "General Motors Function Disable Arbitration — GmFctDiArbn MDD"
description: "Converted Design / Integration Document from GmFctDiArbn_MDD.docx (DOCX, 115 KB)."
---

:::note
Converted from `CF025A_GmFctDiArbn_Impl/doc/GmFctDiArbn_MDD.docx` (Design / Integration Document; original DOCX, about 115 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CF025A_GmFctDiArbn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

GmFctDiArbn

June 30, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	GmStrtStop High-Level Description	5

2	Design details of software module	6

2.1	Graphical representation of GmStrtStop	6

2.2	Data Flow Diagram	6

2.2.1	Component level DFD	6

2.2.2	Function level DFD	6

3	Constant Data Dictionary	7

3.1	Program (fixed) Constants	7

3.1.1	Embedded Constants	7

4	Software Component Implementation	8

4.1	Sub-Module Functions	8

4.1.1	Init: None	8

4.1.2	Per: GmStrtStopPer1	8

4.1.2.1	Design Rationale	8

4.1.2.2	Store Module Inputs to Local copies	8

4.1.2.3	(Processing of function)………	8

4.1.2.4	Store Local copy of outputs into Module Outputs	8

4.2	Server Runables	8

4.3	Interrupt Functions	8

4.4	Module Internal (Local) Functions	8

4.4.1	Local Function #1	8

4.4.1.1	Description	8

4.4.2	Local Function #2	8

4.4.2.1	Description	9

4.4.3	Local Function #3	9

4.4.3.1	Description	9

4.5	GLOBAL Function/Macro Definitions	9

5	Known Limitations with Design	10

6	UNIT TEST CONSIDERATION	11

Appendix A	Abbreviations and Acronyms	12

Appendix B	Glossary	13

Appendix C	References	14

GmStrtStop High-Level Description

Refer to FDD

Design details of software module

Graphical representation of GmStrtStop

Data Flow Diagram

Refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Refer .m file

Software Component Implementation

Sub-Module Functions

Init: None

Per: GmStrtStopPer1

Design Rationale

Refer FDD for the overall functionality. 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

GmFctDiReq_Oper

Design Rationale

Refer FDD for the overall functionality. 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Description

Implementation of ‘FcnDi_ElpdTi’ block in the model.

Local Function #2

Description

Implementation of 'CheckEotPosInRng' block in the model.

Local Function #3

Description

Implementation of 'CheckHwTqZeroAndHwAgZero' block in the model.      

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
Initial Version | Nick Saxton | 1 | 30-June-2016
Function Name | GetElpdTi | Type | Min | Min | Max
Arguments Passed | FctDi_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
 | FctDiStrtTi_MicroSec_T_u32 | uint32 | 0 | 10000000 | 10000000
Return Value | ElpdTi_Sec_T_f32 | float32 | 0 | 10000000 | 10000000
Function Name | ChkEotPosInRng | Type | Min | Min | Max
Arguments Passed | FctDi_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
 | HwAgFinal_HwDeg_T_f32 | float32 | -1440 | 1440 | 1440
 | CwEot_HwDeg_T_f32 | float32 | 360 | 900 | 900
 | CcwEot_HwDeg_T_f32 | float32 | -900 | -360 | -360
Return Value | GmFctDiSts_Cnt_T_enum | GmFctDiArbnSts1 | GMFCTDIARBNSTS_WAIT | GMFCTDIARBNSTS_TIMEOUTFAIL | GMFCTDIARBNSTS_TIMEOUTFAIL
Function Name | ChkHwTqZeroAndHwAgZero | Type | Min | Min | Max
Arguments Passed | HwAgFinal_HwDeg_T_f32 | float32 | -1440 | 1440 | 1440
 | HwTq_HwNwtMtr_T_f32 | float32 | -10 | 10 | 10
Return Value | OnCenterEna_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
