---
title: "Handwheel Angle System Arbitration — HwAgSysArbn MDD"
description: "Converted Design / Integration Document from HwAgSysArbn_MDD.docx (DOCX, 142 KB)."
---

:::note
Converted from `SF045A_HwAgSysArbn_Impl/doc/HwAgSysArbn_MDD.docx` (Design / Integration Document; original DOCX, about 142 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF045A_HwAgSysArbn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

HwAgSysArbn

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Change History

Table of Contents

HwAgSysArbn & High-Level Description

The Handwheel angle system arbitration function accepts inputs from the various angle sources available in the EPS system and selects the angle source to be used for the system handwheel angle value. It also provides for compliance compensation of the angle value and determines the angle value and angle validity to be output on the vehicle data bus.

Design details of software module

Graphical representation of HwAgSysArbn

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

Refer .m file

Software Component Implementation

Sub-Module Functions

Init: HwAgSysArbn_Init1

Design Rationale

Refer FDD

Module Outputs

Refer FDD

Per: HwAgSysArbn_Per1

Design Rationale

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

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

None

References

 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
