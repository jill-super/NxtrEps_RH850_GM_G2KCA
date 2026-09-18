---
title: "Damping — Dampg MDD"
description: "Converted Design / Integration Document from Dampg_MDD.docx (DOCX, 113 KB)."
---

:::note
Converted from `SF003A_Dampg_Impl/doc/Dampg_MDD.docx` (Design / Integration Document; original DOCX, about 113 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF003A_Dampg_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

Dampg

July 1, 2015

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Sankardu Varadapureddi,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

1.2	Scope	4

2	Dampg High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of <Component Name>	6

3.2	Data Flow Diagram	6

3.2.1	Component level DFD	6

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1.1	Sub-Module Functions	9

5.1.2	Interrupt Service Routines	9

5.1.3	Server Runnable Functions	9

5.1.4	Module Internal (Local) Functions	9

5.1.4.1	Local Function #1	9

5.1.4.2	Description	9

5.1.4.3	Local Function #2	9

5.1.4.4	Description	9

5.1.5	Transition Functions	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

Introduction

Purpose

Scope

Dampg High-Level Description

Refer to FDD

Design details of software module

Graphical representation of Dampg

Data Flow Diagram

Component level DFD

Refer FDD

Function level DFD

Refer FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

None

Software Component Implementation

Sub-Module Functions

Initialization sub-module {_Init()}

 DampgInit1  (Refer FDD for details)

Periodic sub-module {_Per()}

DampgPer1  (Refer FDD for details)

Interrupt Service Routines

None

Server Runnable Functions

None

Module Internal (Local) Functions

Local Function #1

Description

‘MotVelDampgCmd’ block implementation.

Local Function #2

Description

‘HydPwrSteerDampgCmd’ block implementation.

Transition Functions

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
Initial Version | Sankardu Varadapureddi | 1.0 | 01-July-2015
Function Name | MotVelDampgCmd | Type | Min | Max
Arguments Passed | MotVelCrf_MotRadPerSec_T_f32 | float32 | -1350 | 1350
 | HwTq_HwNwtMtr_T_f32 | float32 | -10 | 10
 | TSca_Uls_T_f32 | float32 | 0 | 10
 | VehSpd_Kph_T_f32 | float32 | 0 | 511
Return Value | ActvDampg_MotNwtMtr_T_f32 | float32 | -176 | 176
Function Name | HydPwrSteerDampgCmd | Type | Min | Max
Arguments Passed | VehSpd_Kph_T_f32 | float32 | 0 | 511
 | TSca_Uls_T_f32 | float32 | 0 | 10
 | AssiCmdBas_MotNwtMtr_T_f32 | float32 | -8.8 | 8.8
 | MotVelCrf_MotRadPerSec_T_f32 | float32 | -1350 | 1350
Return Value | HydDampg_MotNwtMtr_T_f32 | float32 | -8.8 | 8.8
Abbreviation or Acronym | Description
 | 
 | 
