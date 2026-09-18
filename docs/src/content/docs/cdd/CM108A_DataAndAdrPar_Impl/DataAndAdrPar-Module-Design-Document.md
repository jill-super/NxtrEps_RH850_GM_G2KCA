---
title: "Data and Address Parity — DataAndAdrPar Module Design Document"
description: "Converted Design / Integration Document from DataAndAdrPar Module Design Document.docx (DOCX, 94 KB)."
---

:::note
Converted from `CM108A_DataAndAdrPar_Impl/doc/DataAndAdrPar Module Design Document.docx` (Design / Integration Document; original DOCX, about 94 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM108A_DataAndAdrPar_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

DataAndAdrPar

Mar 15, 2016

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

2	DataAndAdrPar & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of DataAndAdrPar	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init:DataAndAdrParInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Init:DataAndAdrParInit2	9

5.1.2.1	Design Rationale	9

5.1.2.2	Module Outputs	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.4.1	ChkForECMBit28	9

5.4.1.1	Design Rationale	9

5.4.1.2	Processing	9

5.4.2	WrTestModeCtrReg	9

5.4.2.1	Design Rationale	10

5.4.2.2	Processing	10

5.5	GLOBAL Function/Macro Definitions	10

5.5.1	GLOBAL Function #1	10

5.5.1.1	Design Rationale	10

5.5.1.2	Processing	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

Introduction

Purpose

Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance. 

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.  

May: indicates an optional action.

DataAndAdrPar & High-Level Description

See FDD

Design details of software module

Graphical representation of DataAndAdrPar

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

Init:DataAndAdrParInit1

Design Rationale

Non-RTE Init function to verify the Data Parity Data Transfer Path micro diagnostic. Refer FDD for more details

Module Outputs

None

Init:DataAndAdrParInit2

Design Rationale

RTE empty Init function 

Module Outputs

None

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

ChkForEcmBit28

Design Rationale

Static function to check whether ECM bit was set or not within a time out interval of max 2uSec

Processing

To be called from DataAndAdrParInit1 function

WrTestModeCtrReg

Design Rationale

Static function to write to the Test Mode Control register and verify the write was successful

Processing

To be called from DataAndAdrParInit1 function

GLOBAL Function/Macro Definitions

GLOBAL Function #1

Design Rationale

Processing

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
Initial Version | Avinash James | 1 | 03/15/16
Constant Name | Resolution | Units | Value
VCIFERRSETBFRTEST_CNT_U32 | 1 | Counts | ((uint32)1U<<0U)
ECMERRSETBFRTEST_CNT_U32 | 1 | Counts | ((uint32)1U<<1U)
READOPERECMERR_CNT_U32 | 1 | Counts | ((uint32)1U<<2U)
WROPERECMERR_CNT_U32 | 1 | Counts | ((uint32)1U<<3U)
WROPERADRPARERR_CNT_U32 | 1 | Counts | ((uint32)1U<<4U)
CLRERRSTSFLGFAIL_CNT_U32 | 1 | Counts | ((uint32)1U<<5U)
TESTMODCTRLREGWRFAIL_CNT_U32 | 1 | Counts | ((uint32)1U<<6U)
TOUT_MICROSEC_U32 | 1 | MicroSec | 2U
Function Name | ChkForEcmBit28 | Type | Min | Max
Arguments Passed | None |  |  | 
Return Value | RetVal_Cnt_T_logl | Boolean | 0 | 1
Function Name | WrTestModCtrlReg | Type | Min | Max
Arguments Passed | Val | Uint32 | 0 | 0xFFFFFFFF
 | ErrFlg_Cnt_T_u32 | Uint32 | 0 | 0xFFFFFFFF
Return Value | None |  |  | 
