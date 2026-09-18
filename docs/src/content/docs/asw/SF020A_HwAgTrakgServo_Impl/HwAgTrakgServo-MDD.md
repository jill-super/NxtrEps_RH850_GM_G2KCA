---
title: "Handwheel Angle Tracking Servo — HwAgTrakgServo MDD"
description: "Converted Design / Integration Document from HwAgTrakgServo_MDD.docx (DOCX, 96 KB)."
---

:::note
Converted from `SF020A_HwAgTrakgServo_Impl/doc/HwAgTrakgServo_MDD.docx` (Design / Integration Document; original DOCX, about 96 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF020A_HwAgTrakgServo_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

HwAgTrakgServo

Dec 18, 2015

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Kannappa Chidambaram (Tata Elxsi),

Trivandrum, INDIA.

Change History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	HwAgTrakgServo & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of HwAgTrakgServo	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	8

4	Constant Data Dictionary	9

4.1	Program (fixed) Constants	9

4.1.1	Embedded Constants	9

5	Software Component Implementation	10

5.1	Sub-Module Functions	10

5.1.1	Init: HwAgTrakgServoInit1	10

5.1.1.1	Design Rationale	10

5.1.1.2	Module Outputs	10

5.1.2	Per: HwAgTrakgServoPer1	10

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

5.4.3	Local Function #3	11

5.4.3.1	Design Rationale	11

5.4.3.2	Processing	11

5.4.4	Local Function #4	11

5.4.4.1	Design Rationale	12

5.4.4.2	Processing	12

5.5	GLOBAL Function/Macro Definitions	12

6	Known Limitations with Design	13

7	UNIT TEST CONSIDERATION	14

Appendix A	Abbreviations and Acronyms	15

Appendix B	Glossary	16

Appendix C	References	17

Introduction

Purpose

MDD for Handwheel Angle Tracking Servo.

HwAgTrakgServo & High-Level Description

Please refer FDD

Design details of software module

Graphical representation of HwAgTrakgServo

Data Flow Diagram

Please refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: HwAgTrakgServoInit1

Design Rationale

None

Module Outputs

None

Per: HwAgTrakgServoPer1

Design Rationale

None

Store Module Inputs to Local copies

None

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

NA

Processing

Please refer FilterDesiredAngle block of the FDD. 

(Path : SF020A_HwAgTrakgServo/HwAgTrakgServo/HwAgTrakgServoPer1/FilterDesiredAngle)

GLOBAL Function/Macro Definitions

None.

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

Initial Version | Kannappa C | EA4 01.00.01 | 18-Dec-2015
Constant Name | Resolution | Units | Value
SECTOMILLISEC_ULS_F32 | Float32 | Uls | 1000.0F
Please refer .m file for the rest | NA | NA | NA
Function Name | FilterDesiredAngle | Type | Min | Max
Arguments Passed | VehSpd_Kph_T_u8p8 | u8p8 | 0U | 511U
 | HwAgTrakgServoEna_Uls_T_logl | boolean | FALSE | TRUE
 | HwAgTrakgServoCmd_HwDeg_T_f32 | float32 | -1440.0F | 1440.0F
 | HwAg_HwDeg_T_f32 | float32 | -1440.0F | 1440.0F
 | RampComplete_Cnt_T_logl | boolean | FALSE | TRUE
Return Value | HWATrgtFilt_HwDeg_T_f32 | float32 | -1440.0F | 1440.0F
Abbreviation or Acronym | Description
 | 
 | 
