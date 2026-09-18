---
title: "Motor Angle Correlation — MotAgCorrln MDD"
description: "Converted Design / Integration Document from MotAgCorrln_MDD.docx (DOCX, 106 KB)."
---

:::note
Converted from `ES249B_MotAgCorrln_Impl/doc/MotAgCorrln_MDD.docx` (Design / Integration Document; original DOCX, about 106 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES249B_MotAgCorrln_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

‘MotAgCorrln’

Jun 01, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

2	MotAgCorrln & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of MotAgCorrln	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: MotAgCorrlnInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: MotAgCorrlnPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.3	NoneInterrupt Functions	9

5.3.1	Interrupt Function Name	9

5.3.1.1	Design Rationale	9

5.3.1.2	(Processing of the ISR function)…..	9

5.4	Module Internal (Local) Functions	10

5.4.1	Local Function #1	10

5.4.1.1	Design Rationale	10

5.4.1.2	Processing	10

5.4.2	Local Function #2	10

5.4.2.1	Design Rationale	10

5.4.2.2	Processing	10

5.5	GLOBAL Function/Macro Definitions	10

5.5.1	GLOBAL Function #1	10

5.5.1.1	Design Rationale	10

5.5.1.2	processing	11

6	Known Limitations with Design	12

7	UNIT TEST CONSIDERATION	13

Appendix A	Abbreviations and Acronyms	14

Appendix B	Glossary	15

Appendix C	References	16

Introduction

MDD for MotAgCorrln .

MotAgCorrln & High-Level Description

Refer FDD

Design details of software module

Graphical representation of MotAgCorrln

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

Sub-Module Functions

Init: MotAgCorrlnInit1

Refer FDD

Design Rationale

Design follows implementation in FDD. 

Module Outputs

Refer FDD

Per: MotAgCorrlnPer1

Refer FDD

Design Rationale

Refer FDD

Store Module Inputs to Local copies

Refer FDD

 (Processing of function)………

Refer to FDD  (Block ‘MotAgCorrlnPer1’)

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

NoneInterrupt Functions

None

Interrupt Function Name

None

Design Rationale

None

(Processing of the ISR function)…..

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

Checks Signal Availability of Motor. Implementation of 'MtrAgA SigAvlCheck' and 'MtrAgB SigAvlCheck' blocks.

Processing

Note: ‘* StallCntOutp_Cnt_T_u08’ is an output of this function.

 Local Function #2

Design Rationale

Implementation of 'TestOk' check functionality. This function corresponds to the block 'MotAgA vs MotAgB'.

Processing

Refer FDD.

GLOBAL Function/Macro Definitions

GLOBAL Function #1

None

Design Rationale

None

processing

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
Initial Version | Nick Saxton | 1.0 | 01-Jun-2016
Constant Name | Resolution | Units | Value
MOTAGMECLCORRLNSTMIN_CNT_U08 | None | Cnt | 0
MOTAGMECLCORRLNSTMAX_CNT_U08 | None | Cnt | 3
MOTAGMECLIDPTSIGMIN_CNT_U08 | None | Cnt | 0
MOTAGMECLIDPTSIGMAX_CNT_U08 | None | Cnt | 2
Function Name | MtrAgSigAvlCheck | Type | Min | Max
Arguments Passed | SigRollg_Cnt_T_u08 | uint8 | 0 | 255
 | SigQlfr_Cnt_T_enum | Enum (SigQlfr1) | SIGQLFR_NORES | SIGQLFR_FAILD
 | LstRollg_Cnt_T_u08 | uint8 | 0 | 255
 | LstStall_Cnt_T_u08 | uint8 | 0 | 255
 | *StallCntOutp_Cnt_T_u08 | uint8 | 0 | 255
Return Value | SigAvl_Cnt_T_lgc | boolean | FALSE | TRUE
Function Name | TestOkCheck | Type | Min | Max
Arguments Passed | MotAgAMecl_MotRev_T_u0p16 | u0p16 | 0 | 65535
 | MotAgBMecl_MotRev_T_u0p16 | u0p16 | 0 | 65535
Return Value | TestOk_Cnt_T_logl | boolean | FALSE | TRUE
