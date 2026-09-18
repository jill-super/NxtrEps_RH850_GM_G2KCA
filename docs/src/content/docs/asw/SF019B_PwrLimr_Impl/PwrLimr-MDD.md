---
title: "Power Limiter — PwrLimr MDD"
description: "Converted Design / Integration Document from PwrLimr_MDD.docx (DOCX, 153 KB)."
---

:::note
Converted from `SF019B_PwrLimr_Impl/doc/PwrLimr_MDD.docx` (Design / Integration Document; original DOCX, about 153 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF019B_PwrLimr_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

PwrLimr

 , 201

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

PwrLimr High-Level Description

Refer FDD

Design details of software module

Graphical representation of PwrLimr

Data Flow Diagram

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

For other constants, refer DataDict.m

Software Component Implementation

Sub-Module Functions

Init: PwrLimrInit1

Design Rationale

Init function is present in DataDict.m file but not shown in FDD model. Per the note in SF019B_PwrLimr/PwrLimr in the model, the init function is responsible for updating the low pass filters used in the periodic functions. Additionally, the init function starts up a timer used in the ‘Asst_Lmt_Condition_Determination’ block in the model. 

Module Outputs

Refer FDD

Per: PwrLimrPer1

Design Rationale

Refer FDD

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Per: PwrLimrPer2

Design Rationale

GetTiSpan100MicroSec32bit returns elapsed time in counts where one count is equal to 100 microseconds. Therefore, the value returned from that function is divided by 10 to get the elapsed time in milliseconds.

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
Initial Version | Nick Saxton | 1.0 | 14-Aug-2015
 |  |  | 
Constant Name | Resolution | Units | Value
MAXNRIVTRS_CNT_F32 | Single precision float | Cnt | 2.0
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
