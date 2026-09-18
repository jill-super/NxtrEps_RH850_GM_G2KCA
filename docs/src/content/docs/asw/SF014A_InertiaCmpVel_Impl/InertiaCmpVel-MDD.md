---
title: "Inertia Compensation by Velocity — InertiaCmpVel MDD"
description: "Converted Design / Integration Document from InertiaCmpVel_MDD.docx (DOCX, 158 KB)."
---

:::note
Converted from `SF014A_InertiaCmpVel_Impl/doc/InertiaCmpVel_MDD.docx` (Design / Integration Document; original DOCX, about 158 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF014A_InertiaCmpVel_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

InertiaCmpVel

Ju 1, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Krishna Anne,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

1.2	Scope	4

2	InertiaCmpVel & High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of InertiaCmpVel	6

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1.1	Sub-Module Functions	9

5.1.2	Interrupt Service Routines	9

5.1.3	Server Runnable Functions	9

5.1.4	Module Internal (Local) Functions	9

5.1.5	Transition Functions	11

6	Known Limitations with Design	12

7	UNIT TEST CONSIDERATION	13

Appendix A	Abbreviations and Acronyms	14

Appendix B	Glossary	15

Appendix C	References	16

Introduction

Purpose

Scope

InertiaCmpVel & High-Level Description

Refer FDD

Design details of software module

Graphical representation of InertiaCmpVel

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

Global Constants

Refer .m file

User defined typedef definition/declaration 

This section documents any user types uniquely used for the module.

Software Component Implementation

Sub-Module Functions

Initialization sub-module InertiaCmpVelInit1()

  Design Rational: 

Init function is not present in the model but in reference to the Init.txt  text file Low pass filter and Notch filter are initialized.

For Low pass filter standard EA4 LPF implementation from NxtrFil.h is followed and for Notch filter initialization, EA3 implementation is followed.

Periodic sub-module InertiaCmpVelPer1() 

Interrupt Service Routines

None

Server Runnable Functions

None

Module Internal (Local) Functions

Calculate Driver Velocity

Calculate ADD Coefficient

Calculate Gain

Calculate Filter Coefficients

Generate Command

NotchCmp

FilNotchFullUpdOutp_f32

Description

Notch filter output calculation implemented based on ‘Inertia Comp Notch’ block functionality.

FilNotchInit 

Description

Notch filter initialization function implemented based on EA3 design.

Transition Functions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

Since the notch filter implementation used in this module is dynamic in nature, absolute ranges are difficult to determine without pre-defined knowledge on the combination of coefficient values (A1, A2, B0, B1, B2).  Because of this, the systems group ran simulations on 10 different combinations of coefficients (2 with defined default calibrations, 8 considered extreme cases of notch filters) and logged the ranges of the filter state variables and outputs during a frequency sweep.  The ranges given throughout this module were taken as the worst case results of all of the given test cases.

To provide useful cases for unit testing, the boundary checks tested during unit testing should be altered to test the state variable minimum and maximum for each of the 10 test cases with the given coefficients set to the values given in that test case.  In the case where the default values of the coefficients are used in a vector, the unit tester should not test the corresponding state variables with values over the range defined for that set of coefficients.  See attached simulation results.

GenFddIcCmd function is designed to work with argument values from the calling function as used with the other functions in the module, and outputs may be out of the expected range if tested with arbitrary combinations of input values.  Unit testing of this function should use only passed argument value combinations coming from the calling function.

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

SNo | Description | Author | Version | Date
1 | Initial Version | SB | 1.0 | 23-Jul-2015
2 | Updated to version 1.3.0 of design | SB | 2.0 | 11-Mar-2016
3 | Updated to version 1.7.0 and 1.8.0 of design | KK | 3.0 | 21-Jun-2016
 |  |  |  | 
Typedef Name | Element Name | User Defined Type | Legal Range
(min) | Legal Range
(max)
typedef struct FilCoeffRec | b0_Uls_f32 | Float32 | FULL | FULL
 | b1_Uls_f32 | Float32 | FULL | FULL
 | b2_Uls_f32 | Float32 | FULL | FULL
 | a0_Uls_f32 | Float32 | FULL | FULL
 | a1_Uls_f32 | Float32 | FULL | FULL
 | a2_Uls_f32 | Float32 | FULL | FULL
Function Name | DrvrVelCalc | Type | Min | Max
Arguments Passed | HwTq_HwNwtMtr_T_f32 | float32 | -10 | 10
 | MotVelCrf_MotRadPerSec_T_f32 | float32 | -1350 | 1350
 | VehSpd_Kph_T_f32 | float32 | 0 | 511
Return Value | ScadDrvrVel_MotRadPerSec_T_f32 | float32 | -1350 | 1350
Function Name | ADDCoeffCalc | Type | Min | Max
Arguments Passed | AssiCmdBas_MotNwtMtr_T_f32 | float32 | -8.8 | 8.8
 | WhlImbRejctnAmp_MotNwtMtr_T_f32 | float32 | 0 | 8.8
 | VehSpd_Kph_T_f32 | float32 | 0 | 511
Return Value | ADDCoeffCalc_MotNwtMtrSpRad_T_f32 | float32 | 0.0 | 0.00007
