---
title: "Stability Compensation — StabyCmp MDD"
description: "Converted Design / Integration Document from StabyCmp_MDD.docx (DOCX, 131 KB)."
---

:::note
Converted from `SF029A_StabyCmp_Impl/doc/StabyCmp_MDD.docx` (Design / Integration Document; original DOCX, about 131 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF029A_StabyCmp_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

StabyCmp

Prepared By: 

,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

1.2	Scope	4

2	StabyCmp High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of ‘StabyCmp’	6

3.2	Data Flow Diagram	6

3.2.1	Component level DFD	6

3.2.2	Function level DFD	6

4	Constant Data Dictionary	7

4.1	Program (fixed) Constants	7

4.1.1	Embedded Constants	7

5	Software Component Implementation	8

5.1.1	Sub-Module Functions	8

5.1.2	Interrupt Service Routines	8

5.1.3	Server Runnable Functions	8

5.1.4	Module Internal (Local) Functions	8

5.2	Local Function #1	8

5.3	Description	8

5.4	Local Function #2	9

5.5	Description	9

5.5.1	Transition Functions	9

6	Known Limitations with Design	10

7	UNIT TEST CONSIDERATION	11

Appendix A	Abbreviations and Acronyms	12

Appendix B	Glossary	13

Appendix C	References	14

Introduction

Purpose

StabyCmp High-Level Description

Refer FDD

Design details of software module

Graphical representation of ‘StabyCmp’

Data Flow Diagram

Component level DFD

Refer FDD

Function level DFD

Refer FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Refer .m file

Local Constants

None

Software Component Implementation

Sub-Module Functions

Initialization sub-module {}

Design Rational:

FDD details are not complete for notch filter initialization. Upon discussion with FDD owner, implemented in line with EA3 implementation.

Periodic sub-module {}

Refer FDD for details

Design Rational:

In design version 1..0, .m file has some additional PIMs for notch filters, which are not required in the notch filter implementation. 

 Notch filter implementation in SW based on design 1.0.0 .m file PIMs is not changed. 

Interrupt Service Routines

None

Server Runnable Functions

None

Module Internal (Local) Functions

Local Function #1

Description

Notch filter initialization function implemented based on EA3 design.

Local Function #2

Description

Notch filter output calculation. Implemented based on ‘Compensator1’ block functionality. Compensator2, Compensator3 and Compensator4 also have the same functionality.

Transition Functions

None

Known Limitations with Design

UNIT TEST CONSIDERATION

Since the notch filter implementation used in this module is dynamic in nature, absolute ranges are difficult to determine without pre-defined knowledge on the combination of coefficient values (A1, A2, B0, B1, B2).  Because of this, the systems group ran simulations on 10 different combinations of coefficients (2 with defined default calibrations, 8 considered extreme cases of notch filters) and logged the ranges of the filter state variables and outputs during a frequency sweep.  The ranges given throughout this module were taken as the worst case results of all of the given test cases.

To provide useful cases for unit testing, the boundary checks tested during unit testing should be altered to test the state variable minimum and maximum for each of the 10 test cases with the given coefficients set to the values given in that test case.  In the case where the default values of the coefficients are used in a vector, the unit tester should not test the corresponding state variables with values over the range defined for that set of coefficients.  See attached simulation results.

(Note: this section is copied from EA3 Stability Compensation documentation)

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
Initial Version | Sankardu Varadapureddi | 1.0 | 21-July-2015
Updated for FDD version 1.1.0 | Sankardu Varadapureddi | 2.0 | 11-Mar-2016
 |  |  | 
Function Name | FilNotchInit | Type | Min | Max
Arguments Passed | Inp | float32 | See unit test consideration | See unit test consideration | See unit test consideration
 | FilNotchStRecPtr | FilNotchStRec1 | See unit test consideration | See unit test consideration | See unit test consideration
 | FilNotchGainRecPtr | FilNotchGainRec1 | See unit test consideration | See unit test consideration | See unit test consideration
Return Value | None |  | See unit test consideration | See unit test consideration | See unit test consideration
Function Name | FilNotchFullUpdOutp_f32 | Type | Min | Max
Arguments Passed | Inp | float32 | See unit test consideration | See unit test consideration
 | FilNotchStRecPtr | FilNotchStRec1 | See unit test consideration | See unit test consideration
 | FilNotchGainRecPtr | FilNotchGainRec1 | See unit test consideration | See unit test consideration
Return Value | FilOut | float32 | See unit test consideration | See unit test consideration
Abbreviation or Acronym | Description
 | 
 | 
