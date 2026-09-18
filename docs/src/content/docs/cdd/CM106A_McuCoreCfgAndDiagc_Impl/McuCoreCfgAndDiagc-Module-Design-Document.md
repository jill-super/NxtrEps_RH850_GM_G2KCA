---
title: "Microcontroller Core Configuration and Diagnostic — McuCoreCfgAndDiagc Module Design Document"
description: "Converted Design / Integration Document from McuCoreCfgAndDiagc Module Design Document.docx (DOCX, 96 KB)."
---

:::note
Converted from `CM106A_McuCoreCfgAndDiagc_Impl/doc/McuCoreCfgAndDiagc Module Design Document.docx` (Design / Integration Document; original DOCX, about 96 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM106A_McuCoreCfgAndDiagc_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

McuCoreCfgAndDiagc

Oct 6, 2015

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

2	<Component Name> & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of <Component Name>	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: <Component Name>_Init<n>	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: <Component Name>_Per<n>	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.2.1	<Server Runable Name>	9

5.2.1.1	Design Rationale	9

5.2.1.2	(Processing of function)………	10

5.3	Interrupt Functions	10

5.3.1	Interrupt Function Name	10

5.3.1.1	Design Rationale	10

5.3.1.2	(Processing of the ISR function)…..	10

5.4	Module Internal (Local) Functions	10

5.4.1	Local Function #1	10

5.4.1.1	Design Rationale	10

5.4.1.2	Processing	10

5.5	GLOBAL Function/Macro Definitions	10

5.5.1	GLOBAL Function #1	10

5.5.1.1	Design Rationale	11

5.5.1.2	processing	11

6	Known Limitations with Design	12

7	UNIT TEST CONSIDERATION	13

Appendix A	Abbreviations and Acronyms	14

Appendix B	Glossary	15

Appendix C	References	16

Introduction

Purpose

Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance. 

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.  

May: indicates an optional action.

McuCoreCfgAndDiagc & High-Level Description

See FDD

Design details of software module

Graphical representation of McuCoreCfgAndDiagc

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

Init: McuCoreCfgAndDiagcInit1

Design Rationale

Temporary variables were created to read register values into in order to avoid MISRA violations that appear when volatile values are used in conditional statements.

Module Outputs

Refer to FDD

Init: McuCoreCfgAndDiagcInit2

Design Rationale

Temporary variables were created to read register values into in order to avoid MISRA violations that appear when volatile values are used in conditional statements.

Module Outputs

Refer to FDD

Init: McuCoreCfgAndDiagcInit3

Design Rationale

Empty function for purposes of memory mapping

Module Outputs

None

Per: McuCoreCfgAndDiagc_Per<n>

None

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

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
Initial Version | Lucas Wendling | 1 | 10/06/15
Constant Name | Resolution | Units | Value
None |  |  | 
Function Name | (Exact name used) | Type | Min | Max
Arguments Passed | None | <Refer MDD guidelines[1]> | <Refer MDD guidelines[1]> | <Refer MDD guidelines[1]>
 |  |  |  | 
Return Value |  |  |  | 
Function Name | (Exact name used) | Type | Min | Max
Arguments Passed | None | <Refer MDD guidelines[1]> | <Refer MDD guidelines[1]> | <Refer MDD guidelines[1]>
 |  |  |  | 
Return Value |  |  |  | 
