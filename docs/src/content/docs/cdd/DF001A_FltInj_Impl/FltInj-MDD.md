---
title: "Fault Injection — FltInj MDD"
description: "Converted Design / Integration Document from FltInj_MDD.docx (DOCX, 105 KB)."
---

:::note
Converted from `DF001A_FltInj_Impl/doc/FltInj_MDD.docx` (Design / Integration Document; original DOCX, about 105 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to DF001A_FltInj_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

FltInj

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

,

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

FltInj High-Level Description

Refer FDD

Design details of software module

Graphical representation of FltInj

Data Flow Diagram

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

For other constants, refer DataDict.m

Software Component Implementation

Sub-Module Functions

Init: 

None

Design Rationale

N/A

Module Outputs

N/A

Per: FltInjPer1

Design Rationale

Refer FDD

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

FltInj_f32_Oper

Design Rationale

Refer FDD

 (Processing of function)………

Refer FDD

FltInj_logl_Oper

Design Rationale

Refer FDD

 (Processing of function)………

Refer FDD

FltInj_u08_Oper

Design Rationale

Refer FDD

 (Processing of function)………

Refer FDD

FltInj_u0p16_Oper

Design Rationale

Refer FDD

 (Processing of function)………

Refer FDD

Interrupt Functions

None

Interrupt Function Name

N/A

Design Rationale

N/A

(Processing of the ISR function)…..

N/A

Module Internal (Local) Functions

GLOBAL Function/Macro Definitions

Known Limitations with Design

UNIT TEST CONSIDERATION

Unit testing should be performed for when the build constant FLTINJENA is set to STD_ON in order to enable core functionality of this module.  This will have to be done by manually altering FltInj.h to change the value of this #define.

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
Initial Version | Lucas Wendling | 1.0 | 08/26/15
 |  |  | 
Constant Name | Resolution | Units | Value
TICNVN_MICROTOMILLI_F32 | Single precision float | MicroToMilli | 0.001
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
