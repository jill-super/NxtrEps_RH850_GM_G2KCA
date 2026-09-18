---
title: "Motor Ripple and Cogging Configuration — MotRplCoggCfg MDD"
description: "Converted Design / Integration Document from MotRplCoggCfg_MDD.docx (DOCX, 116 KB)."
---

:::note
Converted from `SF106A_MotRplCoggCfg_Impl/doc/MotRplCoggCfg_MDD.docx` (Design / Integration Document; original DOCX, about 116 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF106A_MotRplCoggCfg_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

MotRplCoggCfg

Feb 9, 2016

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

2	MotRplCoggCfg & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of MotRplCoggCfg	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: MotRplCoggCfgInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: MotRplCoggCfgPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.2.1	GetMotRplCoggPrm_Oper	9

5.2.1.1	Design Rationale	9

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

Refer the Design Subproject.

MotRplCoggCfg & High-Level Description

Refer the Design Subproject.

Design details of software module

Graphical representation of MotRplCoggCfg

Data Flow Diagram

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

<The detailed design of the function is provided in the FDD. The detail design shall only be added to the MDD when it is not provided in the FDD or the FDD is not adequate and clarification is needed.>

Sub-Module Functions

The sub-module functions are grouped based on similar functionality that needs to be executed in a given “State” of the system (refer States and Modes).  For a given module, the MDD will identify the type and number of sub-modules required.  The sub-module types are described below.

<(Note: For multiple init or per functions, insert new headers at the “Header 3” level – subset of “Sub-Module Functions section above” and follow the same sub-section design shown below .  If none required, place the text “None”))>

Init: MotRplCoggCfgInit1

Design Rationale

Refer the Design Subproject 

Module Outputs

Refer the Design Subproject 

Per: MotRplCoggCfgPer1

Design Rationale

Refer the Design Subproject 

Store Module Inputs to Local copies

Refer the Design Subproject 

 (Processing of function)………

Refer the Design Subproject 

Store Local copy of outputs into Module Outputs

Refer the Design Subproject 

Server Runables 

GetMotRplCoggPrm_Oper

Design Rationale

Refer the Design Subproject 

Store Module Inputs to Local copies

Refer the Design Subproject 

 (Processing of function)………

Refer the Design Subproject 

Store Local copy of outputs into Module Outputs

Refer the Design Subproject 

Module Internal (Local) Functions

Local Function #1

Design Rationale

Processing

Init function and SetMotRplCoggPrm_Oper updates the Per Instance Memory from Calibrations and NVM values.

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
1 | Initial Version | Selva Sengottaiyan | 09-Feb-2016
Constant Name | Resolution | Units | Value
Refer the Design Subproject. | Refer the Design Subproject. | Refer the Design Subproject. | Refer the Design Subproject.
Function Name | CalcCoggTqTbl | Type | Min | Max
Arguments Passed | None |  |  | 
 |  |  |  | 
Return Value | None |  |  | 
Abbreviation or Acronym | Description
 | 
 | 
