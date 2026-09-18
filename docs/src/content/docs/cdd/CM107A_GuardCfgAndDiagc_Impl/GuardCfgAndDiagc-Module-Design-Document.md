---
title: "Guard Configuration and Diagnostic — GuardCfgAndDiagc Module Design Document"
description: "Converted Design / Integration Document from GuardCfgAndDiagc Module Design Document.docx (DOCX, 108 KB)."
---

:::note
Converted from `CM107A_GuardCfgAndDiagc_Impl/doc/GuardCfgAndDiagc Module Design Document.docx` (Design / Integration Document; original DOCX, about 108 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM107A_GuardCfgAndDiagc_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

GuardCfgAndDiagc

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

2	GuardCfgAndDiagc & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of GuardCfgAndDiagc	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: GuardCfgAndDiagcInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Init: GuardCfgAndDiagcInit2	9

5.1.2.1	Design Rationale	9

5.1.2.2	Module Outputs	9

5.1.3	Init: GuardCfgAndDiagcInit3	9

5.1.3.1	Design Rationale	9

5.1.3.2	Module Outputs	9

5.1.4	Per: None	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	10

5.4.1	ConfigureFilterN	10

5.4.1.1	Design Rationale	10

5.4.1.2	Processing	10

5.4.2	ChkForPBGErr	10

5.4.2.1	Design Rationale	10

5.4.2.2	Processing	10

5.4.3	ChkForECMErr	10

5.4.3.1	Design Rationale	10

5.4.3.2	Processing	11

5.4.4	Vrfy32BitPBGRegAcs	11

5.4.4.1	Design Rationale	11

5.4.4.2	Processing	11

5.4.5	Vrfy16BitPBGRegAcs	11

5.4.5.1	Design Rationale	11

5.4.5.2	Processing	11

5.4.6	Vrfy8BitPBGRegAcs	11

5.4.6.1	Design Rationale	11

5.4.6.2	Processing	11

5.5	GLOBAL Function/Macro Definitions	12

5.5.1	GLOBAL Function #1	12

5.5.1.1	Design Rationale	12

5.5.1.2	Processing	12

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

GuardCfgAndDiagc & High-Level Description

See FDD

Design details of software module

Graphical representation of GuardCfgAndDiagc

Data Flow Diagram

Component level DFD

See FDD

Function level DFD

See FDD	

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: GuardCfgAndDiagcInit1

Design Rationale

Non-RTE function for Guard configuration initialization of PEG, IPG, and PBG so that guard protection can be initialized and enabled before the RTE is started

Module Outputs

Configuration registers for PEG, IPG, and PBG

Init: GuardCfgAndDiagcInit2

Design Rationale

RTE Empty function for purposes of memory mapping

See FDD for more.

Module Outputs

None

Init: GuardCfgAndDiagcInit3

Design Rationale

Non-RTE function for Start Up Initialization test of PBG of Group 3A

See FDD for more.

Module Outputs

None

Per: None

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

ConfigureFilterN

Design Rationale

This local function sets the value Val to the register address PbgProtReg passed as the arguments and verifies the write operation was successful. If not a diagnostic is set.

Processing

Figure 4.5.3 from SAN ver 1.20

ChkForPBGErr

Design Rationale

This local function checks PBG access violation error is captured. If not set diagnostic, clear the error and if the error doesn’t clear set diagnostic.

Processing

Figure 4.5.3 from SAN ver 1.20

ChkForECMErr

Design Rationale

This local function checkscwhether ECM captures the error sets diagnostic message and clears the ECM errors after the check else set diagnostic.

Processing

Refer FDD 4.5.3 Implementation

Vrfy32BitPBGRegAcs

Design Rationale

This is defined to reduce the path count and modularizes the check for the 32 bit Access registers alone.

Processing

Vrfy16BitPBGRegAcs

Design Rationale

This is defined to reduce the path count and modularizes the check for the 16 bit Access registers alone.

Processing

Vrfy8BitPBGRegAcs

Design Rationale

This is defined to reduce the path count and modularizes the check for the 8 bit Access registers alone.

Processing

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
Initial Version | Avinash James | 1.0 | 02/16/16
 |  |  | 
Constant Name | Resolution | Units | Value
PBGPROTNCMN_CNT_U32 | 1 | uint32 | 0x0405FE1FU
PBGUSRMODENA_CNT_U32 | 1 | uint32 | 0x02000000U
PBGUSRMODDI_CNT_U32 | 1 | uint32 | 0x00000000U
PBGSPID321ENA_CNT_U32 | 1 | uint32 | 0x000001C0U
PBGSPID31ENA_CNT_U32 | 1 | uint32 | 0x00000140U
PBGSPID21ENA_CNT_U32 | 1 | uint32 | 0x000000C0U
PBGSPID1ENA_CNT_U32 | 1 | uint32 | 0x00000040U
PBGSETNOREADWRACS_CNT_U32 | 1 | uint32 | 0x405FE5CU
NROF8BITREG_CNT_U08 | 1 | uint8 | ((uint8)0x09)
NROF32BITREG_CNT_U08 | 1 | uint8 | ((uint8)0x02)
READERRBIT_CNT_U32 | 1 | uint32 | ((uint32)1U<<6U)
WRERRBIT_CNT_U32 | 1 | uint32 | ((uint32)1U<<7U)
CFGERRBIT_CNT_U32 | 1 | uint32 | ((uint32)1U<<8U)
PBGERRBIT_CNT_U32 | 1 | uint32 | ((uint32)1U<<9U)
ECMERRBIT_CNT_U32 | 1 | uint32 | ((uint32)1U<<10U)
REGTYPE8BIT_CNT_U32 | 1 | uint32 | ((uint32)0U<<4U)
REGTYPE16BIT_CNT_U32 | 1 | uint32 | ((uint32)1U<<4U)
REGTYPE32BIT_CNT_U32 | 1 | uint32 | ((uint32)2U<<4U)
PBGSTRTUPTESTNOFAILR_CNT_U32 | 1 | uint32 | 0x0U
 |  |  | 
Function Name | ConfigureFilterN | Type | Min | Max
Arguments Passed | PbgProtReg | volatile uint32* | 0 | 0xFFFFFFFF
 | Val | uint32 | 0 | 0xFFFFFFFF
 | PbgStrtUpTestFailSts | Uint32 * | 0 | 0xFFFFFFFF
Return Value | None |  |  | 
Function Name | ChkForPBGErr | Type | Min | Max
Arguments Passed | PbgStrtUpTestFailSts | Uint32 * | 0 | 0xFFFFFFFF
 |  |  |  | 
Return Value | None |  |  | 
