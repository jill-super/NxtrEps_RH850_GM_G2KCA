---
title: "General Motors Vehicle Speed Arbitration — GmVehSpdArbn MDD"
description: "Converted Design / Integration Document from GmVehSpdArbn_MDD.docx (DOCX, 146 KB)."
---

:::note
Converted from `CF016A_GMVehSpdArbn_Impl/doc/GmVehSpdArbn_MDD.docx` (Design / Integration Document; original DOCX, about 146 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CF016A_GMVehSpdArbn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

GmVehSpdArbn

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	GmVehSpdArbn High-Level Description	5

2	Design details of software module	6

2.1	Graphical representation of GmVehSpdArbn	6

2.2	Data Flow Diagram	6

2.2.1	Component level DFD	6

2.2.2	Function level DFD	6

3	Constant Data Dictionary	7

3.1	Program (fixed) Constants	7

3.1.1	Embedded Constants	7

4	Software Component Implementation	8

4.1	Sub-Module Functions	8

4.1.1	Per: GmVehSpdArbnPer1	8

4.1.1.1	Design Rationale	8

4.1.1.2	Store Module Inputs to Local copies	8

4.1.1.3	(Processing of function)………	8

4.1.1.4	Store Local copy of outputs into Module Outputs	8

4.1.2	Init: GmVehSpdArbnInit1	8

4.1.2.1	Design Rationale	8

4.1.2.2	Store Module Inputs to Local copies	8

4.1.2.3	(Processing of function)………	8

4.1.2.4	Store Local copy of outputs into Module Outputs	8

4.2	Server Runables	8

4.3	Interrupt Functions	8

4.4	Module Internal (Local) Functions	8

4.4.1	Local Function #1	8

4.4.1.1	Design Rationale	9

4.4.1.2	Processing	9

4.4.2	Local Function #2	9

4.4.2.1	Design Rationale	9

4.4.2.2	Processing	9

4.4.3	Local Function #3	9

4.4.3.1	Design Rationale	9

4.4.3.2	Processing	9

4.4.4	Local Function #4	9

4.4.4.1	Design Rationale	10

4.4.4.2	Processing	10

4.4.5	Local Function #5	10

4.4.5.1	Design Rationale	10

4.4.5.2	Processing	10

4.5	GLOBAL Function/Macro Definitions	10

5	Known Limitations with Design	11

6	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

GmVehSpdArbn High-Level Description

This GM specific function determines how EPS shall calculate Secure Vehicle Speed, Non-Secure Vehicle Speed, and how to arbitrate between those signals in addition to a serial communication supplied vehicle speed signal.

Design details of software module

Graphical representation of GmVehSpdArbn

Data Flow Diagram

Simulink model being created for component in near future

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Refer DataDict.m file.

Software Component Implementation

Sub-Module Functions

The sub-module functions are grouped based on similar functionality that needs to be executed in a given “State” of the system (refer States and Modes).  For a given module, the MDD will identify the type and number of sub-modules required.  The sub-module types are described below.

Per: GmVehSpdArbnPer1

Design Rationale

Simulink model being created for component in near future

Store Module Inputs to Local copies

 (Processing of function)………

Store Local copy of outputs into Module Outputs

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

Created to reduce static path count and avoid repeated code.

Processing

This function checks to see if at least one of the input valid signals is FALSE (invalid) or input stuck signals is TRUE (stuck) , returning an overall validity (OverallVld) of FALSE (invalid) if so, and TRUE (valid) otherwise.

Local Function #2

Design Rationale

Created to reduce static path count and avoid repeated code.

Processing

This function checks to see if all of the input signals (VldSig1 – 4) are FALSE (invalid), returning an overall invalidity (OverallInvld) of TRUE (invalid) if so, and FALSE (valid) otherwise.

Local Function #3

Design Rationale

Created to reduce static path count and avoid repeated code

* AvgSum and AvgCnt are outputs of this function

Processing

This function adds the velocity signal input (VelSig) to the average sum (AvgSum) and increments the average count (AvgCnt) if the input signal is valid (VldSig).

Local Function #4

Design Rationale

Created to reduce static path count and avoid repeated code.

* MaxVel_Kph_T_f32 is an output of this function

Processing

This function sets max velocity (MaxVel) to the maximum of the previous value of max velocity, velocity signal 1 (VelSig1), and velocity signal 2 (VelSig2) given that the valid signal condition (VldSig) is TRUE (valid).

Local Function #5

Design Rationale

Created to reduce static path count and avoid repeated code.

* MinVel_Kph_T_f32 is an output of this function

Processing

This function sets minimum velocity (MinVel) to the minimum of the previous value of minimum velocity, velocity signal 1 (VelSig1), and velocity signal 2 (VelSig2), given that VldSig is TRUE.

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

Simulink model being created for component in near future

UNIT TEST CONSIDERATION

Simulink model being created for component in near future

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
Initial Version | N. Saxton | 1.0 | 03-Sep-2015
Updated graphical representation | N. Saxton | 2.0 | 12-Nov-2015
 |  |  | 
Function Name | DetVld | Type | Min | Max
Arguments Passed | VldSig1_Cnt_T_logl | Boolean | FALSE | TRUE
 | VldSig2_Cnt_T_logl | Boolean | FALSE | TRUE
 | StuckSig1_Cnt_T_logl | Boolean | FALSE | TRUE
 | StuckSig2_Cnt_T_logl | Boolean | FALSE | TRUE
Return Value | OverallVld_Cnt_T_logl | Boolean | FALSE | TRUE
Function Name | DetInvld | Type | Min | Max
Arguments Passed | VldSig1_Cnt_T_logl | Boolean | FALSE | TRUE
 | VldSig2_Cnt_T_logl | Boolean | FALSE | TRUE
 | VldSig3_Cnt_T_logl | Boolean | FALSE | TRUE
 | VldSig4_Cnt_T_logl | Boolean | FALSE | TRUE
Return Value | OverallInvld_Cnt_T_logl | Boolean | FALSE | TRUE
Function Name | UpdtAvg | Type | Min | Max
Arguments Passed | VldSig_Cnt_T_logl | Boolean | FALSE | TRUE
 | VelSig_Kph_T_f32 | Float32 | 0.0 | 511.0
 | *AvgSum_Kph_T_f32 | Float32 | 0.0 | 2044.0
 | *AvgCnt_Cnt_T_f32 | Float32 | 0.0 | 4.0
