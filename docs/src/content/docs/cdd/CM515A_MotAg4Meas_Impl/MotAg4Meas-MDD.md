---
title: "Motor Ag4 Measurement — MotAg4Meas MDD"
description: "Converted Design / Integration Document from MotAg4Meas_MDD.docx (DOCX, 109 KB)."
---

:::note
Converted from `CM515A_MotAg4Meas_Impl/doc/MotAg4Meas_MDD.docx` (Design / Integration Document; original DOCX, about 109 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM515A_MotAg4Meas_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

MotAg4Meas

Nov 7, 2016

Prepared By: 

Shruthi Raghavan,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

2	MotAg4Meas & High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of MotAg4Meas	6

3.2	Data Flow Diagram	6

3.2.1	Component level DFD	6

3.2.2	Function level DFD	6

4	Constant Data Dictionary	7

4.1	Program (fixed) Constants	7

4.1.1	Embedded Constants	7

5	Software Component Implementation	8

5.1	Sub-Module Functions	8

5.1.1	Init: MotAg4MeasInit1	8

5.1.2	Per: None	8

5.2	Server Runables	8

5.2.1	GetMotAg4Mecl_Oper	8

5.3	Interrupt Functions	8

5.3.1	Interrupt Function Name	8

5.4	Module Internal (Local) Functions	9

5.4.1	Local Function #1	9

5.5	GLOBAL Function/Macro Definitions	9

5.5.1	GLOBAL Function #1	9

6	Known Limitations with Design	10

7	UNIT TEST CONSIDERATION	11

Appendix A	Abbreviations and Acronyms	12

Appendix B	Glossary	13

Appendix C	References	14

Introduction

Purpose

Module design document for MotAg4Meas SWC.

MotAg4Meas & High-Level Description

Refer to design.

Design details of software module

Graphical representation of MotAg4Meas

Data Flow Diagram

Component level DFD

N/A

Function level DFD

N/A

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Refer DataDict.m file for rest of the constants.

Software Component Implementation

Sub-Module Functions

Init: MotAg4MeasInit1

Design Rationale

Initialization of registers according to CM515A_MotAg4Meas_RegisterConfiguration.xlsm

Module Outputs

None

Per: None

Design Rationale

Module Outputs

Server Runables 

GetMotAg4Mecl_Oper

Design Rationale

Refer to FDD

 (Processing of function)………

Refer to FDD

Interrupt Functions

None

Interrupt Function Name

Design Rationale

 (Processing of the ISR function)…..

Module Internal (Local) Functions

None

Local Function #1

Design Rationale

Processing

GLOBAL Function/Macro Definitions

None

GLOBAL Function #1

Design Rationale

Processing

Known Limitations with Design

None.

UNIT TEST CONSIDERATION

None.

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
Initial Version | Shruthi Raghavan | 1.0 | 7-Nov-16
Constant Name | Resolution | Units | Value
REGENCA1CTLINITVAL_CNT_U16 | 1 | Cnt | 0x03U
REGENCA1IOC1INITVAL_CNT_U08 | 1 | Cnt | 0x04U
REGENCA1TTINITVAL_CNT_U08 | 1 | Cnt | 0x01U
REGENCA1TSINITVAL_CNT_U08 | 1 | Cnt | 0x01U
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
