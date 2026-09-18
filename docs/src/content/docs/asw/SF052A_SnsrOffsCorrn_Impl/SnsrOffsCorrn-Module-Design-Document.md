---
title: "Sensor Offset Correction — SnsrOffsCorrn Module Design Document"
description: "Converted Design / Integration Document from SnsrOffsCorrn Module Design Document.docx (DOCX, 159 KB)."
---

:::note
Converted from `SF052A_SnsrOffsCorrn_Impl/doc/SnsrOffsCorrn Module Design Document.docx` (Design / Integration Document; original DOCX, about 159 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF052A_SnsrOffsCorrn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Module Design Document

For

SnsrOffsCorrn

Jan 27, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Software Group,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	SnsrOffsCorrn High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of SnsrOffsCorrn	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: SnsrOffsCorrnInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: SnsrOffsCorrnPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.5	GLOBAL Function/Macro Definitions	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	16

Introduction

Purpose

This document defines the module level design for the Sensor Offset and Correction Component. Major part of design has been captured in the FDD and any design rationale that has not been identified in the FDD and has been used to implement the component has been documented in the MDD

Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance. 

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.  

May: indicates an optional action.

 SnsrOffsCorrn High-Level Description

 Sensor Offset and Correction (SnsrOffsCorrn) corrects the Yaw rate, Hand wheel Position and Hand wheel Torque signals using their corresponding offset learnt values.  Each offset value is learnt by the SF051A Sensor Offset Learning.

Design details of software module

See FDD.

Graphical representation of SnsrOffsCorrn 

Data Flow Diagram

See FDD.

Component level DFD

See FDD.

Function level DFD

See FDD.

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

<The detailed design of the function is provided in the FDD. The detail design shall only be added to the MDD when it is not provided in the FDD or the FDD is not adequate and clarification is needed.>

Sub-Module Functions

The sub-module functions are grouped based on similar functionality that needs to be executed in a given “State” of the system (refer States and Modes).  For a given module, the MDD will identify the type and number of sub-modules required.  The sub-module types are described below.

<(Note: For multiple init or per functions, insert new headers at the “Header 3” level – subset of “Sub-Module Functions section above” and follow the same sub-section design shown below .  If none required, place the text “None”))>

Init: SnsrOffsCorrnInit1  

Design Rationale

None – Empty Init Function

Module Outputs

None

Per: SnsrOffsCorrnPer1

Design Rationale

The periodic function reads the input port values and based on the calibration defined, applies the offset to the Yaw rate, Hand wheel Position and Hand wheel Torque signals and writes the corrected value to the corresponding output ports

Store Module Inputs to Local copies

None

(Processing of function)………

See FDD.

Store Local copy of outputs into Module Outputs

None

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
Initial Version | Avinash James | 1.0 | 27-Jan-2016
Constant Name | Resolution | Units | Value
HWAGHILIM_HWDEG_F32 | Single Precision Floating Point | HwDeg | 1440.0F
HWAGLOLIM_HWDEG_F32 | Single Precision Floating Point | HwDeg | -1440.0F
VEHYAWRATEHILIM_VEHDEGPERSEC_F32 | Single Precision Floating Point | VehDegPerSec | 120.0F
VEHYAWRATELOLIM_VEHDEGPERSEC_F32 | Single Precision Floating Point | VehDegPerSec | -120.0F
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
