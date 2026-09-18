---
title: "Pull Compensation Activation — PullCmpActv MDD"
description: "Converted Design / Integration Document from PullCmpActv_MDD.docx (DOCX, 139 KB)."
---

:::note
Converted from `SF013A_PullCmpActv_Impl/doc/PullCmpActv_MDD.docx` (Design / Integration Document; original DOCX, about 139 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF013A_PullCmpActv_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

Prepared For:

Nexteer Automotive,

Prepared By: 

Spandana Balani,

Nexteer Automotive,

Change History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	Active Pull Compensation & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of Active Pull Compensation	7

3.2	Data Flow Diagram	8

3.2.1	Component level DFD	8

3.2.2	Function level DFD	8

4	Constant Data Dictionary	9

4.1	Program (fixed) Constants	9

4.1.1	Embedded Constants	9

5	Software Component Implementation	10

5.1	Sub-Module Functions	10

5.1.1	Init: PullCmpActvInit1	10

5.1.1.1	Design Rationale	10

5.1.1.2	Module Outputs	10

5.1.2	Per: PullCmpActvPer1	10

5.1.2.1	Design Rationale	10

5.1.2.2	Store Module Inputs to Local copies	10

5.1.2.3	(Processing of function)………	10

5.1.2.4	Store Local copy of outputs into Module Outputs	10

5.1.3	Per: PullCmpActvPer2	10

5.1.3.1	Design Rationale	10

5.1.3.2	Store Module Inputs to Local copies	10

5.1.3.3	(Processing of function)………	10

5.1.3.4	Store Local copy of outputs into Module Outputs	10

5.2	Server Runnables	11

5.2.1	GetPullCmpPrm	11

5.2.1.1	Design Rationale	11

5.2.1.2	(Processing of function)………	11

5.2.2	RstPullCmp	11

5.2.2.1	Design Rationale	11

5.2.2.2	(Processing of function)………	11

5.2.3	SetPullCmpLongTerm	11

5.2.3.1	Design Rationale	11

5.2.3.2	(Processing of function)………	11

5.2.4	SetPullCmpShoTerm	11

5.2.4.1	Design Rationale	11

5.2.4.2	(Processing of function)………	11

5.3	Interrupt Functions	11

5.4	Module Internal (Local) Functions	11

5.4.1	Local Function #1	11

5.4.1.1	Design Rationale	12

5.4.1.2	Processing	12

5.4.2	Local Function #2	12

5.4.2.1	Design Rationale	12

5.4.2.2	Processing	12

5.4.3	Local Function #1	12

5.4.3.1	Design Rationale	13

5.4.3.2	Processing	13

5.5	GLOBAL Function/Macro Definitions	13

5.5.1	GLOBAL Function #1	13

5.5.1.1	Design Rationale	13

5.5.1.2	processing	13

6	Known Limitations with Design	14

7	UNIT TEST CONSIDERATION	15

Appendix A	Abbreviations and Acronyms	16

Appendix B	Glossary	17

Appendix C	References	18

Active Pull Compensation & High-Level Description

The Active Pull Compensation Function corrects vehicle pull issues by compensating for HW torque offsets detected by the steering system.  These torque offsets are classified as short-term and long-term, each of which is compensated for independently by the algorithm.  When the compensation is applied, the need for the driver to provide a constant input torque to counter these offsets is greatly reduced.

Design details of software module

Graphical representation of Active Pull Compensation

Data Flow Diagram

Please refer FDD.

Component level DFD

Please refer FDD.

Function level DFD

Please refer FDD.

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: PullCmpActvInit1

Design Rationale

None

Module Outputs

None

Per: PullCmpActvPer1

Design Rationale

None

Store Module Inputs to Local copies

None

(Processing of function)………

Please refer FDD

Store Local copy of outputs into Module Outputs

Please refer FDD

Per: PullCmpActvPer2

Design Rationale

Please refer FDD.

Store Module Inputs to Local copies

Please refer FDD and design rationale noted above.

(Processing of function)………

Please refer FDD.

Store Local copy of outputs into Module Outputs

None

Server Runnables 

GetPullCmpPrm

Design Rationale

None

 (Processing of function)………

See GetPullCmpPrm block in FDD

RstPullCmp

Design Rationale

None

 (Processing of function)………

See RstPullCmp block in FDD

SetPullCmpLongTerm

Design Rationale

None

(Processing of function)………

See SetPullCmpLongTerm block in FDD

SetPullCmpShoTerm

Design Rationale

None

 (Processing of function)………

See SetPullCmpShoTerm block in FDD

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

None

Processing

(Place flowchart/design for local function)

Refer to the “ActvCmpEna” block of the Simulink model of the design.

Local Function #2

Design Rationale

None

Processing

(Place flowchart/design for local function)

Refer to the “CalcIntgtrGain” block of the Simulink model of the design

Local Function #3

Design Rationale

None

Processing

(Place flowchart/design for local function)

Refer to the “ErrIntgtr&ActvLim” block of the Simulink model of the design.

GLOBAL Function/Macro Definitions

GLOBAL Function #1

None

Design Rationale

processing

(Place flowchart/design for local function)

Known Limitations with Design

None.

UNIT TEST CONSIDERATION

None.

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

Sl. No. | Description | Author | Version | Date
1 | Initial Version | Akhil Krishna N D | 1.0 | 16-Oct-2015
2 | Updated to FDD version SF013A_PullCmpActv_Design_1.4.0 | SB | 2.0 | 29-Feb-2016
 |  |  |  | 
Constant Name | Resolution | Units | Value
Please refer .m file |  |  | 
Function Name | ActvCmpEna | Type | Min | Max
Arguments Passed | PullCmpActvShoTermRst_Cnt_T_logl | boolean | FALSE | TRUE
 | AbslHwTqFild_HwNwtMtr_T_f32 | float32 | 0.0 | 10.0
 | AbslHwAg_HwDeg_T_f32 | float32 | 0.0 | 1440.0
 | AbslVehYawRateFild_VehDegPerSec_T_f32 | float32 | 0.0 | 128.0
 | AbslVehLatA_MtrPerSecSqd_T_f32 | float32 | 0.0 | 10.0
 | PinionAgConf_Uls_T_f32 | float32 | 0.0 | 1.0
 | VehSpd_Kph_T_f32 | float32 | 0.0 | 511.0
 | VehSpdVld_Cnt_T_logl | boolean | FALSE | TRUE
 | AbslHwVel_HwRadPerSec_T_f32 | float32 | 0.0 | 42.0
 | PullCmpSts_Cnt_T_logl | boolean | FALSE | TRUE
Return Value | LrngEnad_Cnt_T_logl | boolean | FALSE | TRUE
Function Name | CalcIntgrGain | Type | Min | Max
Arguments Passed | HwTq_HwNwtMtr_T_f32 | float32 | -10.0 | 10.0
 | PullCmpShoTermPrev_HwNwtMtr_T_f32 | float32 | -10.0 | 10.0
Return Value | IntgtrGainShoTerm_Uls_T_f32 | float32 | 0.0 | 1.0
