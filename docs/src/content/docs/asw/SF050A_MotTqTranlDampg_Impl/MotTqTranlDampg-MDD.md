---
title: "Motor Torque Transient Damping — MotTqTranlDampg MDD"
description: "Converted Design / Integration Document from MotTqTranlDampg_MDD.docx (DOCX, 111 KB)."
---

:::note
Converted from `SF050A_MotTqTranlDampg_Impl/doc/MotTqTranlDampg_MDD.docx` (Design / Integration Document; original DOCX, about 111 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF050A_MotTqTranlDampg_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

Transistional Damping (SF-50A)

August 12, 2015

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Krishna Kanth Anne,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	MotTqTranlDampg & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of MotTqTranlDampg	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	8

4	Constant Data Dictionary	9

4.1	Program (fixed) Constants	9

4.1.1	Embedded Constants	9

5	Software Component Implementation	10

5.1	Sub-Module Functions	10

5.1.1	Init: MotTqTranlDampgInit1	10

5.1.1.1	Design Rationale	10

5.1.1.2	Module Outputs	10

5.1.2	Per: MotTqTranlDampgPer1	10

5.1.2.1	Design Rationale	10

5.1.2.2	Store Module Inputs to Local copies	10

5.1.2.3	(Processing of function)………	10

5.1.2.4	Store Local copy of outputs into Module Outputs	10

5.2	Server Runables	10

5.3	Interrupt Functions	10

5.4	Module Internal (Local) Functions	10

5.4.1	Local Function #1	10

5.4.1.1	Design Rationale	11

5.4.1.2	Processing	11

5.4.2	Local Function #2	11

5.4.2.1	Design Rationale	11

5.4.2.2	Processing	11

5.5	GLOBAL Function/Macro Definitions	11

5.5.1	GLOBAL Function #1	11

6	Known Limitations with Design	12

7	UNIT TEST CONSIDERATION	13

Appendix A	Abbreviations and Acronyms	14

Appendix B	Glossary	15

Appendix C	References	16

Introduction

Purpose

MDD for Motor Torque Transistional Damping.

Scope

MotTqTranlDampg & High-Level Description

Please refer FDD.

Design details of software module

Graphical representation of MotTqTranlDampg

Data Flow Diagram

Please refer FDD.

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: MotTqTranlDampgInit1

Design Rationale

None

Module Outputs

None

Per: MotTqTranlDampgPer1

Design Rationale

None

Store Module Inputs to Local copies

Please refer FDD

 (Processing of function)………

Please refer FDD

Store Local copy of outputs into Module Outputs

Please refer FDD

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

None

Processing

(Place flowchart/design for local function)

Refer to the “SwOutputCntrl” block of the Simulink model of the design.

Local Function #2

Design Rationale

None

Processing

(Place flowchart/design for local function)

Refer to the “SwOutputCntrl” block of the Simulink model of the design.

GLOBAL Function/Macro Definitions

None

GLOBAL Function #1

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
Initial Version | Krishna Kanth Anne | EA4 01.00.01 | 12-Aug-2015
Constant Name | Resolution | Units | Value
Please refer .m file |  |  | 
Function Name | SwOpCtrlPart1 | Type | Min | Max
Arguments Passed | TranlDampgTiElpsd_MilliSec_T_f32 | float32 | 0.0 | 1000.0
Arguments Passed | AbslMotVelCrf_MotRadPerSec_T_f32 | float32 | 0.0 | 1350.0
Return Value | MotTqTranlDampgCmpl_Cnt_T_lgc | boolean | FALSE | TRUE
Function Name | SwOpCtrlPart2 | Type | Min | Max
Arguments Passed | DiagcStsCtrldShtDwnFltPrsnt_Cnt_T_lgc | boolean | FALSE | TRUE
Arguments Passed | CtrlDampTrq_MotNwtMtr_T_f32 | float32 | -3.0 | 3.0
 | SysSt_Cnt_T_enum | SysSt1 | 0 | 3
 | MotTqCmdCrf_MotNwtMtr_T_f32 | float32 | -8.8 | 8.8
 | MotTqTranlDampgCmpl_Cnt_T_lgc | boolean | FALSE | TRUE
Return Value | MotTqCmdCrfDampd_MotNwtMtr_T_f32 | float32 | -11.8 | 11.8
