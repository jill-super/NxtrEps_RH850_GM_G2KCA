---
title: "Loss of Assist Manager — LoaMgr MDD"
description: "Converted Design / Integration Document from LoaMgr_MDD.docx (DOCX, 156 KB)."
---

:::note
Converted from `SF049A_LoaMgr_Impl/doc/LoaMgr_MDD.docx` (Design / Integration Document; original DOCX, about 156 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF049A_LoaMgr_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

LoaMgr

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

2	LoaMgr High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of LoaMgr	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	8

3.2.2	Function level DFD	8

4	Constant Data Dictionary	9

4.1	Program (fixed) Constants	9

4.1.1	Embedded Constants	9

5	Software Component Implementation	10

5.1	Sub-Module Functions	10

5.1.1	Init: LoaMgrInit1	10

5.1.1.1	Design Rationale	10

5.1.1.2	Module Outputs	10

5.1.2	Per: LoaMgrPer1	10

5.1.2.1	Design Rationale	10

5.1.2.2	Store Module Inputs to Local copies	10

5.1.2.3	(Processing of function)………	10

5.1.2.4	Store Local copy of outputs into Module Outputs	10

5.2	Server Runables	10

5.3	Interrupt Functions	10

5.4	Module Internal (Local) Functions	10

5.4.1	Local Function #1	10

5.4.1.1	Design Rationale	10

5.4.1.2	Processing	11

5.4.2	Local Function #2	11

5.4.2.1	Design Rationale	11

5.4.2.2	Processing	11

5.4.3	Local Function #3	11

5.4.3.1	Design Rationale	11

5.4.3.2	Processing	11

5.4.4	Local Function #4	11

5.4.4.1	Design Rationale	11

5.4.4.2	Processing	11

5.4.5	Local Function #5	11

5.4.5.1	Design Rationale	12

5.4.5.2	Processing	12

5.4.6	Local Function #6	12

5.4.6.1	Design Rationale	12

5.4.6.2	Processing	12

5.4.7	Local Function #7	12

5.4.7.1	Design Rationale	12

5.4.7.2	Processing	12

5.4.8	Local Function #8	13

5.4.8.1	Design Rationale	13

5.4.8.2	Processing	13

5.5	GLOBAL Function/Macro Definitions	13

6	Known Limitations with Design	14

7	UNIT TEST CONSIDERATION	15

Appendix A	Abbreviations and Acronyms	16

Appendix B	Glossary	17

Appendix C	References	18

Introduction

Purpose

Scope

LoaMgr High-Level Description

Refer to FDD

Design details of software module

Graphical representation of LoaMgr

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

Init: LoaMgrInit1

Design Rationale

Refer FDD

Module Outputs

Refer FDD

Per: LoaMgrPer1

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

Design Rationale

None

Processing

Refer to ‘HwTqResp’ block in FDD at ‘SF049A_LoaMgr/LoaMgr/LoaMgrPer1/Request_Responses’

Local Function #2

Design Rationale

None

Processing

Refer to ‘MotAgResp’ block in FDD at ‘SF049A_LoaMgr/LoaMgr/LoaMgrPer1/Request_Responses’

Local Function #3

Design Rationale

None

Processing

Refer to ‘CurrMeasResp’ block in FDD at ‘SF049A_LoaMgr/LoaMgr/LoaMgrPer1/Request_Responses’

Local Function #4

Design Rationale

None

Processing

Refer to ‘CurrMeasResp’ block in FDD at ‘SF049A_LoaMgr/LoaMgr/LoaMgrPer1/Request_Responses’

Local Function #5

Design Rationale

None

Processing

This function corresponds to common logic (for all requests) in ‘CntSwBasdMtgtn’ block in FDD at ‘SF049A_LoaMgr/LoaMgr/LoaMgrPer1/Arbitrate_Responses’

Local Function #6

Design Rationale

None

Processing

This function corresponds to ‘SelFinalResp’ block in FDD at ‘SF049A_LoaMgr/LoaMgr/LoaMgrPer1/Arbitrate_Responses’

Local Function #7

Design Rationale

None

Processing

This function corresponds to ‘Set_Faults’ block in FDD at ‘SF049A_LoaMgr/LoaMgr/LoaMgrPer1’

Local Function #8

Design Rationale

None

Processing

This function corresponds to ‘SwMtgtn’ block in FDD at ‘SF049A_LoaMgr/LoaMgr/LoaMgrPer1/Assign_Scale’. 

Note that ‘*LoaSca_Uls_T_f32’ and ‘*LoaRateLim_UlsPerSec_T_f32’ are the outputs of this function.

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
Initial Version | Sankardu Varadapureddi | 1 | 04-Aug-2015
 |  |  | 
Constant Name | Resolution | Units | Value
Refer .m file |  |  | 
Function Name | ReqHwTqResp | Type | Min | Max
Arguments Passed | HwTqIdptMin_Cnt_T_u08 | uint8 | 0 | 4
 | TqLoaAvl_Cnt_T_lgc | boolean | FALSE | TRUE
Return Value | HwTqResp_Cnt_T_u08 | uint8 | 0 | 5
Function Name | ReqMotAgResp | Type | Min | Max
Arguments Passed | MotAgIdptMin_Cnt_T_u08 | uint8 | 0 | 3
 | SmpAvl_Cnt_T_lgc | boolean | FALSE | TRUE
Return Value | MotAgResp_Cnt_T_u08 | uint8 | 0 | 5
