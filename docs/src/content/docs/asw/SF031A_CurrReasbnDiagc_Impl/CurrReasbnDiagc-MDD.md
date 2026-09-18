---
title: "Current Reasonableness Diagnostic — CurrReasbnDiagc MDD"
description: "Converted Design / Integration Document from CurrReasbnDiagc_MDD.docx (DOCX, 107 KB)."
---

:::note
Converted from `SF031A_CurrReasbnDiagc_Impl/doc/CurrReasbnDiagc_MDD.docx` (Design / Integration Document; original DOCX, about 107 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF031A_CurrReasbnDiagc_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

CurrReasbnDiagc

Dec 15, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Krishna Anne

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

2	MotRplCoggCmd & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of MotRplCoggCmd	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: MotRplCoggCmdInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: MotRplCoggCmdPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.2.1	GetMotCoggCmdPrm_Oper	9

5.2.1.1	Design Rationale	9

5.2.1.2	Store Module Inputs to Local copies	10

5.2.1.3	(Processing of function)………	10

5.2.1.4	Store Local copy of outputs into Module Outputs	10

5.2.1	SetMotCoggCmdPrm_Oper	10

5.2.1.1	Design Rationale	10

5.2.1.2	Store Module Inputs to Local copies	10

5.2.1.3	(Processing of function)………	10

5.2.1.4	Store Local copy of outputs into Module Outputs	10

5.3	Module Internal (Local) Functions	10

5.3.1	Local Function #1	10

5.3.1.1	Design Rationale	10

5.3.1.2	Processing	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

Introduction

Please refer the Design Subproject.

MotRplCoggCmd & High-Level Description

Please refer the Design Subproject.

Design details of software module

Graphical representation of CurrReasbnDiagc

Please refer the Design Subproject.

Data Flow Diagram

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Please refer the Design Subproject 

Sub-Module Functions

Please refer the Design Subproject 

Init: CurrReasbnDiagcInit1

Design Rationale

Runs at speed of MotorControl X2. Please refer the Design Subproject for more details.

Module Outputs

Please refer the Design Subproject 

Init: CurrReasbnDiagcInit2

Design Rationale

Please refer the Design Subproject 

Module Outputs

Please refer the Design Subproject 

Per: CurrReasbnDiagcPer1

Design Rationale

Runs at speed of MotorControl X2. Please refer the Design Subproject for more details.

Store Module Inputs to Local copies

Please refer the Design Subproject 

 (Processing of function)………

Please refer the Design Subproject 

Store Local copy of outputs into Module Outputs

Please refer the Design Subproject 

Per: CurrReasbnDiagcPer2

Design Rationale

Please refer the Design Subproject 

Store Module Inputs to Local copies

Please refer the Design Subproject 

 (Processing of function)………

Please refer the Design Subproject 

Store Local copy of outputs into Module Outputs

Please refer the Design Subproject 

Server Runables 

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

Version | Description | Author | Date
1 | Initial Version | Krishna Anne | 15-Dec-2016
Constant Name | Resolution | Units | Value
Please refer the Design Subproject. | Please refer the Design Subproject. | Please refer the Design Subproject. | Please refer the Design Subproject.
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
