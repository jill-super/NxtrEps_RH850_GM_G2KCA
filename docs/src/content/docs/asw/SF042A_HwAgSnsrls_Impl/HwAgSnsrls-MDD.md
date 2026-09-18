---
title: "Handwheel Angle Sensorless Estimation — HwAgSnsrls MDD"
description: "Converted Design / Integration Document from HwAgSnsrls_MDD.docx (DOCX, 118 KB)."
---

:::note
Converted from `SF042A_HwAgSnsrls_Impl/doc/HwAgSnsrls_MDD.docx` (Design / Integration Document; original DOCX, about 118 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF042A_HwAgSnsrls_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Module Design Document

For

HwAgSnsrls

VERSION: 4.0

DATE:  17-Nov-2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

TATA ELXSI

CHENNAI, INDIA

Change History

Table of Contents

1	Introduction	5

1.1	Purpose	5

2	HwAgSnsrls & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of HwAgSnsrls	7

3.2	Data Flow Diagram	8

3.2.1	Component level DFD	8

3.2.2	Function level DFD	8

4	Constant Data Dictionary	9

4.1	Program (fixed) Constants	9

4.1.1	Embedded Constants	9

5	Software Component Implementation	10

5.1	Sub-Module Functions	10

5.1.1	Init: HwAgSnsrlsInit1	10

5.1.1.1	Design Rationale	10

5.1.1.2	Module Outputs	10

5.1.2	Per: HwAgSnsrlsPer1	10

5.1.2.1	Design Rationale	10

5.1.2.2	Store Module Inputs to Local copies	10

5.1.2.3	(Processing of function)………	10

5.1.2.4	Store Local copy of outputs into Module Outputs	10

5.2	Server Runnables	10

5.2.1	FSnsrlsHwCentr	10

5.2.1.1	Design Rationale	10

5.2.1.2	(Processing of function)………	10

5.2.2	RstSnsrlsHwCentr	11

5.2.2.1	Design Rationale	11

5.2.2.2	(Processing of function)………	11

5.3	Interrupt Functions	11

5.4	Module Internal (Local) Functions	11

5.4.1	Local Function #1	11

5.4.1.1	Design Rationale	11

5.4.1.2	Processing	11

5.4.2	Local Function #2	12

5.4.2.1	Design Rationale	12

5.4.2.2	Processing	12

5.4.3	Local Function #3	12

5.4.3.1	Design Rationale	12

5.4.3.2	Processing	13

5.4.4	Local Function #4	13

5.4.4.1	Design Rationale	13

5.4.4.2	Processing	13

6	Known Limitations with Design	14

7	UNIT TEST CONSIDERATION	15

Appendix A	Abbreviations and Acronyms	16

Appendix B	Glossary	17

Appendix C	References	18

Introduction

Purpose

MDD for Handwheel Angle Sensorless.

HwAgSnsrls & High-Level Description

Please refer FDD.

Design details of software module

Graphical representation of HwAgSnsrls

Data Flow Diagram

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

Init: HwAgSnsrlsInit1

Design Rationale

None

Module Outputs

None

Per: HwAgSnsrlsPer1

Design Rationale

None

Store Module Inputs to Local copies

None

 (Processing of function)………

Please refer FDD

Store Local copy of outputs into Module Outputs

Please refer FDD

Server Runnables 

 FSnsrlsHwCentr

Design Rationale

None

 (Processing of function)………

Please see FSnsrlsHwCentr block in FDD

 RstSnsrlsHwCentr

Design Rationale

None

 (Processing of function)………

Please see RstSnsrlsHwCentr block in FDD

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

None.

Processing

Refer to the “WhlSpdAutocentr” block of the Simulink model of the design.

Local Function #2

Design Rationale

None.

Processing

Refer to the “VehDynAutoCentr” block of the Simulink model of the design.

Local Function #3

Design Rationale

None.

Processing

Refer to the “PinionTqCalc” and “LpFilOneEna” blocks of the Simulink model of the design.

Local Function #4

Design Rationale

None.

Processing

Please refer to the “Arbitration” and “Smoothing” blocks of the Simulink model of the design.

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

Description | Author | Version | Date
Initial Version | TATA | 1.0 | 29-Jun-2016
Implemented design 1.2.0, 1.3.0 and fixed anomaly 6881 | Hari Mattupalli | 2.0 | 22-Sep-2016
Implemented design 1.4.0 and fixed anomaly 7844 | Hari Mattupalli | 3.0 | 21-Oct-2016
Updated per design rev. 1.6.0 | TATA | 4.0 | 17-Nov-2016
Constant Name | Units | Value
Please refer Data Dictionary .m file | NA | NA
Function Name | WhlSpdAutocentr | Type | Min | Max
Arguments Passed | WhlFrqVld_Cnt_T_lgc | boolean | FALSE | TRUE
 | WhlLeFrq_Hz_T_f32 | float32 | 0.01F | 60.0F
 | WhlRiFrq_Hz_T_f32 | float32 | 0.01F | 60.0F
 | VehSpd_Kph_T_f32 | float32 | 0.0F | 511.0F
 | RelHwAg_HwDeg_T_f32 | float32 | -1440.0F | 1440.0F
 | *WhlSpdHwConf_Uls_T_f32 | float32 | 0.0F | 1.0F
Return Value | None |  |  | 
Function Name | VehDynAutoCentr | Type | Min | Max
Arguments Passed | MotTqCmdCrf_MotNwtMtr_T_f32 | float32 | -8.8 | 8.8
 | HwTq_HwNwtMtr_T_f32 | float32 | -10.0F | 10.0F
 | VehYawRate_VehDegPerSec_T_f32 | float32 | -120.0F | 120.0F
 | VehSpd_Kph_T_f32 | float32 | 0.0F | 511.0F
 | MotVelCrf_MotRadPerSec_T_f32 | float32 | -1350.0F | 1350.0F
 | VehSpdVld_Cnt_T_logl | Boolean | FALSE | TRUE
 | RelHwAg_HwDeg_T_f32 | float32 | -1440.0F | 1440.0F
 | *VehDynHwConf_Uls_T_f32 | float32 | 0.0F | 1.0F
Return Value | None |  |  | 
