---
title: "Handwheel Angle Vehicle Center Trim — HwAgVehCentrTrim MDD"
description: "Converted Design / Integration Document from HwAgVehCentrTrim_MDD.docx (DOCX, 103 KB)."
---

:::note
Converted from `SF053A_HwAgVehCentrTrim_Impl/doc/HwAgVehCentrTrim_MDD.docx` (Design / Integration Document; original DOCX, about 103 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF053A_HwAgVehCentrTrim_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

HwAgVehCentrTrim

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	HwAgVehCentrTrim High-Level Description	4

2	Design details of software module	5

2.1	Graphical representation of HwAgVehCentrTrim	5

2.2	Data Flow Diagram	5

2.2.1	Component level DFD	5

2.2.2	Function level DFD	5

3	Constant Data Dictionary	6

3.1	Program (fixed) Constants	6

3.1.1	Embedded Constants	6

4	Software Component Implementation	7

4.1	Sub-Module Functions	7

4.1.1	Init: None	7

4.1.2	Per: GmStrtStopPer1	7

4.1.2.1	Design Rationale	7

4.1.2.2	Store Module Inputs to Local copies	7

4.1.2.3	(Processing of function)………	7

4.1.2.4	Store Local copy of outputs into Module Outputs	7

4.2	Server Runables	7

4.3	Interrupt Functions	7

4.4	Module Internal (Local) Functions	7

4.5	GLOBAL Function/Macro Definitions	7

5	Known Limitations with Design	8

6	UNIT TEST CONSIDERATION	9

Appendix A	Abbreviations and Acronyms	10

Appendix B	Glossary	11

Appendix C	References	12

HwAgVehCentrTrim High-Level Description

Refer to FDD

Design details of software module

Graphical representation of HwAgVehCentrTrim

Data Flow Diagram

Refer FDD

Component level DFD

Refer FDD

Function level DFD

Refer FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Refer .m file for other constants

Software Component Implementation

Sub-Module Functions

Init: 

Per: 

Design Rationale

Refer FDD for the overall functionality. 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

ClrHwAgTrimVal_Oper

Refer FDD

 GetHwAgTrimVal_ Oper

Refer FDD

SetHwAgTrimVal_Oper

Refer FDD

UpdHwAgTrimVal_Oper

Refer FDD

Interrupt Functions

None

Module Internal (Local) Functions

None

GLOBAL Function/Macro Definitions

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
Initial Version | Nick Saxton | 1 | 24-Feb-2016
Updated graphical representation | Nick Saxton | 2 | 04-Apr-2016
Updated graphical representation for FDD v1.3.0 | Nick Saxton | 3 | 15-Jun-2016
 |  |  | 
Constant Name | Units | Value
HALFFACTOR_ULS_F32 | ULS | 0.5
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
