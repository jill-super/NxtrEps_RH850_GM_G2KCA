---
title: "Handwheel Angle Correlation — HwAgCorrln MDD"
description: "Converted Design / Integration Document from HwAgCorrln_MDD.docx (DOCX, 96 KB)."
---

:::note
Converted from `ES239B_HwAgCorrln_Impl/doc/HwAgCorrln_MDD.docx` (Design / Integration Document; original DOCX, about 96 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES239B_HwAgCorrln_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

HwAgCorrln

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Matthew Leser

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

1.2	Scope	4

2	HwAgCorrln High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of ‘HwAgCorrln’	6

3.2	Data Flow Diagram	6

3.2.1	Component level DFD	6

3.2.2	Function level DFD	6

4	Constant Data Dictionary	7

4.1	Program (fixed) Constants	7

4.1.1	Embedded Constants	7

5	Software Component Implementation	8

5.1.1	Sub-Module Functions	8

5.1.2	Interrupt Service Routines	8

5.1.3	Server Runnable Functions	8

5.1.4	Module Internal (Local) Functions	8

5.1.5	Transition Functions	8

6	Known Limitations with Design	9

7	UNIT TEST CONSIDERATION	10

Appendix A	Abbreviations and Acronyms	11

Appendix B	Glossary	12

Appendix C	References	13

Introduction

Purpose

Scope

HwAgCorrln High-Level Description

Refer FDD

Design details of software module

Graphical representation of ‘HwAgCorrln’

Data Flow Diagram

Component level DFD

Refer FDD

Function level DFD

Refer FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Refer .m file

Local Constants

Software Component Implementation

Sub-Module Functions

Initialization sub-module {_Init()}

None

Periodic sub-module {_Per()}

HwAgCorrlnPer1 (Refer FDD for details) 

Interrupt Service Routines

None

Server Runnable Functions

None

Module Internal (Local) Functions

Local Function #1

Description

Transition Functions

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
 |  |  | 
Constant Name | Resolution | Units | Value
CORRLNSTSMINVAL_CNT_U08 | 1 | CNT | 0U
CORRLNSTSMAXVAL_CNT_U08 | 1 | CNT | 1U
NRVLDSIGMIN_CNT_U08 | 1 | CNT | 0U
NRVLDSIGMAX_CNT_U08 | 1 | CNT | 2U
MAXSTALLCNTR_CNT_U08 | 1 | CNT | 255U
Function Name | HwAgSigAvlChk | Type | Min | Min | Max
Arguments Passed | SigRollg_Cnt_T_u08 | uint8 | 0 | 255 | 255
 | SigQlfr_Cnt_T_enum | SigQlfr1 | SIGQLFR_NORES | SIGQLFR_FAILD | SIGQLFR_FAILD
 | *LstRollgCnt_Cnt_T_u08 | uint8 | 0 | 255 | 255
 | *LstStallCnt_Cnt_T_u08 | uint8 | 0 | 255 | 255
Return Value | SigAvl_Cnt_T_lgc | boolean | FALSE | TRUE | TRUE
Abbreviation or Acronym | Description
 | 
 | 
