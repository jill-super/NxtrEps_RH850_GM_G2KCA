---
title: "Motor Velocity Control — MotVelCtrl MDD"
description: "Converted Design / Integration Document from MotVelCtrl_MDD.docx (DOCX, 106 KB)."
---

:::note
Converted from `NM100A_MotVelCtrl_Impl/doc/MotVelCtrl_MDD.docx` (Design / Integration Document; original DOCX, about 106 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to NM100A_MotVelCtrl_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

MotVelCtrl

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

2	MotVelCtrl High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of MotVelCtrl	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: MotVelCtrlInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: MotVelCtrlPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.2.1	GetCtrlPrm_Oper	9

5.2.1.1	Design Rationale	9

5.2.1.2	(Processing of function)………	9

5.2.2	SetCtrlPrm_Oper	9

5.2.2.1	Design Rationale	9

5.2.2.2	(Processing of function)………	9

5.2.3	StopCtrl_Oper	10

5.2.3.1	Design Rationale	10

5.2.3.2	(Processing of function)………	10

5.2.4	StrtCtrl_Oper	10

5.2.4.1	Design Rationale	10

5.2.4.2	(Processing of function)………	10

5.3	Interrupt Functions	10

5.4	Module Internal (Local) Functions	10

5.4.1	Local Function #1	10

5.4.1.1	Description	10

5.5	GLOBAL Function/Macro Definitions	11

6	Known Limitations with Design	12

7	UNIT TEST CONSIDERATION	13

Appendix A	Abbreviations and Acronyms	14

Appendix B	Glossary	15

Appendix C	References	16

Introduction

Purpose

Scope

MotVelCtrl High-Level Description

Refer to FDD

Design details of software module

Graphical representation of MotVelCtrl

Data Flow Diagram

Refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

For other constants, refer .m file.

Local Constants

Software Component Implementation

Sub-Module Functions

Init: MotVelCtrlInit1

Design Rationale

Refer FDD 

Module Outputs

Refer FDD

Per: MotVelCtrlPer1

Design Rationale

Refer FDD 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

GetCtrlPrm_Oper

Design Rationale

Refer FDD

 (Processing of function)………

Refer FDD

SetCtrlPrm_Oper

Design Rationale

Refer FDD

 (Processing of function)………

Refer FDD

StopCtrl_Oper

Design Rationale

Refer FDD

 (Processing of function)………

Refer FDD

StrtCtrl_Oper

Design Rationale

Refer FDD

 (Processing of function)………

Refer FDD

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Description

Blocks "F_PID Control_1" , "F_PID Control_2"  and "F_PID Control_3" are of same functionality in the FDD.  This sub function corresponds to those blocks implementation.

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

None.

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
Initial Version | Sankardu Varadapureddi | 1 | 17-Feb-2016
 |  |  | 
Constant Name | Resolution | Units | Value
ONEOVERTWOMPLR_ULS_F32 | 1 | Cnt | 0.5
Function Name | FPIDControl | Type | Min | Min | Max
Arguments Passed | MotVelTarSlewed_MotRadPerSec_T_f32 | float32 | - 183500 | 183500 | 183500
 | MotVelrf_MotRadPerSec_T_f32 | float32 | -1350 | 1350 | 1350
Return Value | PIDCmdLimid_MotNwtMtr_T_f32 | float32 | -8.8 | 8.8 | 8.8
Abbreviation or Acronym | Description
 | 
 | 
