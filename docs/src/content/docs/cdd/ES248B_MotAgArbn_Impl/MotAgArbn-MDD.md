---
title: "Motor Angle Arbitration — MotAgArbn MDD"
description: "Converted Design / Integration Document from MotAgArbn_MDD.docx (DOCX, 93 KB)."
---

:::note
Converted from `ES248B_MotAgArbn_Impl/doc/MotAgArbn_MDD.docx` (Design / Integration Document; original DOCX, about 93 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES248B_MotAgArbn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

 MotAgArbn 

Nov 16, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Matthew Leser,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	MotAgArbn  & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of MotAgArbn	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: MotAgArbnInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: MotAgArbnPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.4.1	Local Function #1	9

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

MotAgArbn  & High-Level Description

Refer FDD.

Design details of software module

<The Data Flow Diagrams should be created in the absence of this representation with the FDD.>

Graphical representation of MotAgArbn 

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

Init: MotAgArbnInit1

Design Rationale

Init1 function is created so that it will allow a RTE model to be created in the AUTOSAR tools which allows  Per-Instance Memory and calibration definition needs.  The initialization function is doing nothing

Module Outputs

None

Per: MotAgArbnPer1

Design Rationale

None

Processing of function)……

Refer FDD

Server Runnables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

None

Processing

Refer FDD SigAvlChkRev2 State flow Chart

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
Initial Version | ML | 1.0 | 16-Nov-2016
Constant Name | Resolution | Units | Value
Refer .m file |  |  | 
CORRLNSTSMASKSIGA_CNT_U08 | 1 | Cnt | 0x01
MAXSTALLCNTR_CNT_U08 | 1 | Cnt | 255
Function Name | SigAvlChkRev | Type | Min | Max
Arguments Passed | SigCorrChk_Cnt_T_u08 | uint8 | 0 | 1
 | SigRollgCnt_Cnt_T_u08 | uint8 | 0 | 255
 | SigQlfr_Cnt_T_enum | SigQlfr1 | SIGQLFR_NORES | SIGQLFR_FAILD
 | * LstRollgCnt_Cnt_T_u08 | uint8 | 0 | 255
 | * StallCnt_Cnt_T_u08 | uint8 | 0 | 255
Return Value | SigAvl_Cnt_T_lgc | boolean | FALSE | TRUE
Abbreviation or Acronym | Description
 | 
 | 
