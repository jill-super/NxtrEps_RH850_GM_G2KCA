---
title: "Random Access Memory Handling — RamMem Module Design Document"
description: "Converted Design / Integration Document from RamMem_Module Design Document.docx (DOCX, 100 KB)."
---

:::note
Converted from `CM103A_RamMem_Impl/doc/RamMem_Module Design Document.docx` (Design / Integration Document; original DOCX, about 100 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM103A_RamMem_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

RamMem

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Software Group,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	RamMem & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of RamMem	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: RamMemInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: RamMemPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Module Outputs	9

5.2	Server Runables	9

5.2.1	SpiDblBitEcc	9

5.2.1.1	Design Rationale	9

5.2.1.2	Processing	9

5.2.2	RamMemLclRamSngBitEcc	9

5.2.2.1	Design Rationale	9

5.2.2.2	Processing	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	10

5.4.1	Local Function #1	10

5.4.1.1	Design Rationale	10

5.4.1.2	Processing	10

5.4.2	Local Function #2	10

5.4.2.1	Design Rationale	10

5.4.2.2	Processing	10

5.4.3	Local Function #3	10

5.4.3.1	Design Rationale	10

5.4.3.2	Processing	10

5.4.4	Local Function #4	11

5.4.4.1	Design Rationale	11

5.4.4.2	Processing	11

5.4.5	Local Function #5	11

5.4.5.1	Design Rationale	11

5.4.5.2	Processing	11

5.5	GLOBAL Function/Macro Definitions	11

5.5.1	GLOBAL Function #1	11

5.5.1.1	Design Rationale	11

5.5.1.2	Processing	11

6	Known Limitations with Design	13

7	UNIT TEST CONSIDERATION	14

Appendix A	Abbreviations and Acronyms	15

Appendix B	Glossary	16

Appendix C	References	17

Introduction

Purpose

Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance. 

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.  

May: indicates an optional action.

RamMem & High-Level Description

See FDD

Design details of software module

Graphical representation of RamMem

Data Flow Diagram

Component level DFD

N/A

Function level DFD

N/A

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: RamMemInit1

Design Rationale

Module Outputs

Refer to FDD

Per: RamMemPer1

Design Rationale

Module Outputs

Refer to FDD

Server Runables 

RamMemLclRamSngBitEcc

Design Rationale

Refer the FDD

Processing

Refer the FDD

Interrupt Functions

Module Internal (Local) Functions

Local Function #1

Design Rationale

Refer the FDD

Processing

Refer the FDD

Local Function #2

Design Rationale

Refer the FDD

Processing

Refer the FDD

Local Function #3

Design Rationale

Refer the FDD

Processing

Refer the FDD

Local Function #4

Design Rationale

Refer the FDD

Processing

Refer the FDD

Local Function #5

Design Rationale

Refer the FDD

Processing

Refer the FDD

GLOBAL Function/Macro Definitions

GLOBAL Function #1

Design Rationale

Processing

Known Limitations with Design

Local RAM Single bit PIM for address store will be overwritten for each banks which can be avoided by defining Pims for each memory block. Will be reviewed POST IVER build

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
Initial Version | Selva Sengottaiyan | 1 | 04/06/16
Created local functions for reducing cyclometric complexity | Selva Sengottaiyan | 2 | 06/26/2016
 |  |  | 
Constant Name | Resolution | Units | Value
LCLRAMBASADR_CNT_U32 | 1 | Cnt | 0xFEB80000U
VLDADRTESTBITMASK_CNT_U32 | 1 | Cnt | 0xFFFE0000U
VLDADRTESTRES_CNT_U32 | 1 | Cnt | 0x00060000U
WORDLINEADRMASK_CNT_U32 | 1 | Cnt | 0xFFFFFF1FU
BNK0ERRCLRMASK_CNT_U32 | 1 | Cnt | 0x00000001U
BNK1ERRCLRMASK_CNT_U32 | 1 | Cnt | 0x00000002U
BNK2ERRCLRMASK_CNT_U32 | 1 | Cnt | 0x00000004U
BNK3ERRCLRMASK_CNT_U32 | 1 | Cnt | 0x00000008U
BNK0SNGBITERRMASK_CNT_U32 | 1 | Cnt | 0x00000001U
BNK1SNGBITERRMASK_CNT_U32 | 1 | Cnt | 0x00000100U
BNK2SNGBITERRMASK_CNT_U32 | 1 | Cnt | 0x00010000U
BNK3SNGBITERRMASK_CNT_U32 | 1 | Cnt | 0x01000000U
 |  |  | 
Function Name | RamFailrModClassnChk | Type | Min | Max
Arguments Passed | None |  |  | 
 |  |  |  | 
Return Value |  |  |  | 
Function Name | RamMemLclRamFailrChk | Type | Min | Max
Arguments Passed | LclRamFailrAdr_Cnt_T_u32 | uint32 | 0 | 4294967295
 |  |  |  | 
Return Value |  |  |  | 
