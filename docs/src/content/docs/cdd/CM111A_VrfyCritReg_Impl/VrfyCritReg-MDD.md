---
title: "Verify Critical Registers — VrfyCritReg MDD"
description: "Converted Design / Integration Document from VrfyCritReg_MDD.docx (DOCX, 103 KB)."
---

:::note
Converted from `CM111A_VrfyCritReg_Impl/doc/VrfyCritReg_MDD.docx` (Design / Integration Document; original DOCX, about 103 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM111A_VrfyCritReg_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

VrfyCritReg

Apr 14, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Selva Sengottaiyan

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	VrfyCritReg High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of VrfyCritReg	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: VrfyCritRegInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: VrfyCritRegPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.4.1	Local Function #2	9

5.4.1.1	Description	9

5.5	GLOBAL Function/Macro Definitions	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

Introduction

Purpose

Scope

VrfyCritReg High-Level Description

Refer to FDD

Design details of software module

Graphical representation of VrfyCritReg

Data Flow Diagram

Refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Refer .m file

Local Constants

Software Component Implementation

Sub-Module Functions

Init: VrfyCritRegInit1

Design Rationale

Refer FDD 

Module Outputs

None

Per: VrfyCritRegPer1

Design Rationale

Refer FDD 

Store Module Inputs to Local copies

None

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

None

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

GLOBAL Function/Macro Definitions

Known Limitations with Design

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
Initial Version | Sankardu Varadapureddi | 1 | 14-Jan-2016
 |  |  | 
 |  | 
 |  | 
 |  | 
 |  | 
 |  | 
 |  | 
 |  | 
 |  | 
 |  |  |  |  | 
 |  |  |  |  | 
 |  |  |  |  | 
 |  |  |  |  | 
 |  |  |  |  | 
 |  |  |  |  | 
