---
title: "Hands-Off Detection — HowDetn MDD"
description: "Converted Design / Integration Document from HowDetn_MDD.docx (DOCX, 111 KB)."
---

:::note
Converted from `SF044A_HowDetn_Impl/doc/HowDetn_MDD.docx` (Design / Integration Document; original DOCX, about 111 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF044A_HowDetn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

HowDetn

Jan 29, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By:  Basavaraja Ganeshappa

Software Group,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	HowDetn High-Level Description	6

2.1	Graphical representation of HowDetn	6

2.2	Data Flow Diagram	7

2.2.1	Component level DFD	7

2.2.2	Function level DFD	7

3	Constant Data Dictionary	8

3.1	Program (fixed) Constants	8

3.1.1	Embedded Constants	8

4	Software Component Implementation	9

4.1	Sub-Module Functions	9

4.1.1	Init: HowDetnInit1	9

4.1.1.1	Design Rationale	9

4.1.1.2	Module Outputs	9

4.1.2	Per: HowDetnPer1	9

4.1.2.1	Design Rationale	9

4.1.2.2	Store Module Inputs to Local copies	9

4.1.2.3	(Processing of function)………	9

4.1.2.4	Store Local copy of outputs into Module Outputs	9

4.2	Server Runables	9

4.3	Interrupt Functions	9

4.4	Module Internal (Local) Functions	9

4.5	GLOBAL Function/Macro Definitions	9

5	Known Limitations with Design	10

6	UNIT TEST CONSIDERATION	11

Appendix A	Abbreviations and Acronyms	12

Appendix B	Glossary	13

Appendix C	References	14

Introduction

Purpose

The purpose of this document is to document the module level design for a HowDetn software module which is the part of the software related to Nexteer’s Electrical Steering Systems product line. 

Scope

Scope of the document is to capture the software implementation details of HowDetn Module.

HowDetn High-Level Description

Determination of a continuous valued estimate that represents the likelihood that a driver's hands are on the steering wheel (value =1) or off the steering wheel (value=0).  A discrete value corresponding to the confidence of the estimate is also specified Design details of software module

Graphical representation of HowDetn

Data Flow Diagram

Refer to FDD

Component level DFD

Refer to FDD

Function level DFD

Refer to FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Refer FDD

Sub-Module Functions

Init: HowDetnInit1

Design Rationale

Refer FDD

Module Outputs

Refer FDD

Per: HowDetnPer1

Design Rationale

Refer FDD

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
Initial Version | BG | 1 | 01/29/2016
Server runnables, Interrupt functions, Module Internal (Local) Functions, GLOBAL Function/Macro Definitions - sub portions were removed
Footer template updated to EA4 01.00.01 | BG | 2 | 02/15/2016
Constant Name | Resolution | Units | Value
Refer SF044A_HowDetn_DataDict.m | NA | NA | NA
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
