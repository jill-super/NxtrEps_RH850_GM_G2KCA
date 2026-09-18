---
title: "Torque Estimation — TEstimn MDD"
description: "Converted Design / Integration Document from TEstimn_MDD.docx (DOCX, 120 KB)."
---

:::note
Converted from `SF006A_TEstimn_Impl/doc/TEstimn_MDD.docx` (Design / Integration Document; original DOCX, about 120 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF006A_TEstimn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

TEstimn

Sep 17, 2015

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

2	TEstimn High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of TEstimn	6

3.2	Data Flow Diagram	6

3.2.1	Component level DFD	6

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: TEstimnInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: TEstimnPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.5	GLOBAL Function/Macro Definitions	9

6	Known Limitations with Design	10

7	UNIT TEST CONSIDERATION	11

Appendix A	Abbreviations and Acronyms	12

Appendix B	Glossary	13

Appendix C	References	14

Introduction

Purpose

Scope

TEstimn High-Level Description

Refer to FDD

Design details of software module

Graphical representation of TEstimn

Data Flow Diagram

Refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Refer .m file

Local Constants

Software Component Implementation

Sub-Module Functions

Init: TEstimnInit1

Design Rationale

Refer FDD for the functionality. 

Module Outputs

Refer FDD

Per: TEstimnPer1

Design Rationale

In ‘AssistMechanismLeadLagFilterRe-Initialization’ block, blocks ‘AssistMechanismInitEnable’ and ‘AssistMechanismInitDisable’ have similar logic except for some calculations related to inputs.  So the differences are implemented in ‘if-else’ statement and common logic is implemented after ‘if-else’ statements in the SW.    

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

None

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

Due to the lead/lag filter implementation in this module, absolute ranges are difficult to determine without pre-defined knowledge on the combination of coefficient values (A1, B0, B1).  For unit test purposes, below four sets of lead/lag filter coefficient calibrations (TEstimnXXLLFilCoeffA1, TEstimnXXLLFilCoeffB0 and TEstimnXXLLFilCoeffB1) should be tested using the combinations of coefficient values in the table below, as well as the default values of the filter coefficient calibrations as given in the data dictionary.  The ranges given throughout this module were taken as the worst case results of the entire given filter coefficient sets.

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
Initial Version | Sankardu Varadapureddi | 1 | 17-Sep-2015
Fz | 0.0045 | 0.0045 | 0.00003 | 0.00003
Fp | 0.0045 | 0.00003 | 0.0045 | 0.00003
 |  |  |  | 
B0 | 1 | 0.0066760330 | 149.78955 | 1
B1 | -0.99717656 | -0.0066571836 | -149.78673 | -0.99998115
A1 | 0.99717656 | 0.99998115 | 0.99717656 | 0.99998115
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
