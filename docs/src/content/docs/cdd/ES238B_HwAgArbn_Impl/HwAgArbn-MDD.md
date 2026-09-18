---
title: "Handwheel Angle Arbitration — HwAgArbn MDD"
description: "Converted Design / Integration Document from HwAgArbn_MDD.docx (DOCX, 95 KB)."
---

:::note
Converted from `ES238B_HwAgArbn_Impl/doc/HwAgArbn_MDD.docx` (Design / Integration Document; original DOCX, about 95 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES238B_HwAgArbn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

 HwAgArbn

Version: 1.0

                                                      Date: 7-Nov-2016

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

2	HwAgArbn & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of HwAgArbn	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: <Component Name>_Init<n>	9

5.1.2	Per: HwAgArbnPer1	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.5	GLOBAL Function/Macro Definitions	9

6	Known Limitations with Design	10

7	UNIT TEST CONSIDERATION	11

Appendix A	Abbreviations and Acronyms	12

Appendix B	Glossary	13

Appendix C	References	14

Introduction

Purpose

Scope

 HwAgArbn & High-Level Description

Refer FDD

Design details of software module

Refer FDD

Graphical representation of HwAgArbn

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

Init: <Component Name>_Init<n>

None

Per: HwAgArbnPer1

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
Initial Version | Matthew Leser | 1.0 | 7-Nov-2016
Constant Name | Resolution | Units | Value
CORRLNSTSMASKSIGA_CNT_U08 | 1 | Cnt | 0x01
MAXSTALLCNTR_CNT_U08 | 1 | Cnt | 255U
HWAGLIM_HWDEG_F32 | 1 | HwDeg | 900.0F
Function Name | CorrSigAvlChkRev1 | Type | Min | Max
Arguments Passed | SigRollgCnt_Cnt_T_u08 | uint8 | 0 | 255
 | SigQlfr_Cnt_T_enum | SigQlfr1 | SIGQLFR_NORES | SIGQLFR_FAILD
 | * LstRollgCnt_Cnt_T_u08 | uint8 | 0 | 255
 | * StallCnt_Cnt_T_u08 | uint8 | 0 | 255
Return Value | SigAvl_Cnt_T_lgc | boolean | FALSE | TRUE
Abbreviation or Acronym | Description
 | 
 | 
