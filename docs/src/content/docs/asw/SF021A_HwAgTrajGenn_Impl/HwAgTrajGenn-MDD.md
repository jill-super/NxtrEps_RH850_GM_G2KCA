---
title: "Handwheel Angle Trajectory Generation — HwAgTrajGenn MDD"
description: "Converted Design / Integration Document from HwAgTrajGenn_MDD.docx (DOCX, 103 KB)."
---

:::note
Converted from `SF021A_HwAgTrajGenn_Impl/doc/HwAgTrajGenn_MDD.docx` (Design / Integration Document; original DOCX, about 103 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF021A_HwAgTrajGenn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

HwAgTrajGenn

Feb 4, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Sankardu Varadapureddi,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	HwAgTrajGenn High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of HwAgTrajGenn	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: None	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: HwAgTrajGennPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.2.1	SetTrajTarPrm_Oper	9

5.2.1.1	Design Rationale	9

5.2.1.2	(Processing of function)………	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.4.1	Local Function #1	9

5.4.1.1	Description	10

5.4.2	Local Function #2	10

5.4.2.1	Description	10

5.5	GLOBAL Function/Macro Definitions	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

Introduction

Purpose

Scope

HwAgTrajGenn High-Level Description

Refer to FDD

Design details of software module

Graphical representation of HwAgTrajGenn

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

Init: HwAgTrajGennInit1

Design Rationale

Dummy init function created to meet coding standards. 

Module Outputs

Per: HwAgTrajGennPer1

Design Rationale

Refer FDD for the overall functionality. 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

SetTrajTarPrm_Oper

Design Rationale

Refer FDD

 (Processing of function)………

Refer FDD

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Description

"Initialize Variables" block implementation.

Local Function #2

Description

 "Generate Signals" block implementation.

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
Initial Version | Sankardu Varadapureddi | 1 | 4-Feb-2016
Constant Name | Resolution | Units | Value
ONEOVERTWOMPLR_ULS_F32 | 1 | Cnt | 0.5
Function Name | HwAgTrajInitVaris | Type | Min | Min | Max
Arguments Passed | HwPosn_HwDeg_T_f32 | float32 | -1440 | 1440 | 1440
 | CalcFlg_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
 | HwATar_HwDegPerSecPerSec_T_f32 | float32 | 10 | 2000 | 2000
 | HwAgTar_HwDeg_T_f32 | float32 | -800 | 800 | 800
 | HwVelTar_HwDegPerSec_T_f32 | float32 | 10 | 1000 | 1000
Return Value | None |  |  |  | 
Function Name | HwAgTrajGenSigs | Type | Min | Min | Max
Arguments Passed | HwPosn_HwDeg_T_f32 | float32 | -1440 | 1440 | 1440
 | CalcFlg_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
Return Value | HwAgTrakgServoCmd_HwDeg_T_f32 | float32 | -1440 | 1440 | 1440
