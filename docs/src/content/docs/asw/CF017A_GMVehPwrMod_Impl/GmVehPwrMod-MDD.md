---
title: "General Motors Vehicle Power Mode — GmVehPwrMod MDD"
description: "Converted Design / Integration Document from GmVehPwrMod_MDD.docx (DOCX, 113 KB)."
---

:::note
Converted from `CF017A_GMVehPwrMod_Impl/doc/GmVehPwrMod_MDD.docx` (Design / Integration Document; original DOCX, about 113 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CF017A_GMVehPwrMod_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

GmVehPwrMod

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	GmVehPwrMod High-Level Description	4

2	Design details of software module	5

2.1	Graphical representation of GmVehPwrMod	5

2.2	Data Flow Diagram	5

2.2.1	Component level DFD	5

2.2.2	Function level DFD	5

3	Constant Data Dictionary	6

3.1	Program (fixed) Constants	6

3.1.1	Embedded Constants	6

4	Software Component Implementation	7

4.1	Sub-Module Functions	7

4.1.1	Per: GmVehPwrModPer1	7

4.1.1.1	Design Rationale	7

4.1.1.2	Store Module Inputs to Local copies	7

4.1.1.3	(Processing of function)………	7

4.1.1.4	Store Local copy of outputs into Module Outputs	7

4.2	Server Runables	7

4.3	Interrupt Functions	7

4.4	Module Internal (Local) Functions	7

4.4.1	Local Function #1	7

4.4.1.1	Design Rationale	7

4.4.1.2	Processing	7

4.4.2	Local Function #2	8

4.4.2.1	Design Rationale	8

4.4.2.2	Processing	8

4.5	GLOBAL Function/Macro Definitions	8

5	Known Limitations with Design	9

6	UNIT TEST CONSIDERATION	10

Appendix A	Abbreviations and Acronyms	11

Appendix B	Glossary	12

Appendix C	References	13

GmVehPwrMod High-Level Description

This GM specific function runs periodically to determine whether to enable assist (if not previously enabled) or to disable assist based on the inputs provided to the function.

Design details of software module

Graphical representation of GmVehPwrMod

Data Flow Diagram

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

The sub-module functions are grouped based on similar functionality that needs to be executed in a given “State” of the system (refer States and Modes).  For a given module, the MDD will identify the type and number of sub-modules required.  The sub-module types are described below.

Per: GmVehPwrModPer1

Design Rationale

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

Created to reduce static path count and cyclomatic complexity of periodic function.

Processing

Local Function #2

Design Rationale

Created to reduce static path count and cyclomatic complexity of periodic function.

Processing

Sets MotTqCmdSca to 1.0 if AssiEna is TRUE and sets it to 0.0 otherwise.

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

UNIT TEST CONSIDERATION

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
Initial Version | N. Saxton | 1.0 | 28-Sep-2015
Updated with new graphical representation and local function | N. Saxton | 2.0 | 01-Oct-2015
New graphical representation | N. Saxton | 3.0 | 12-Nov-2015
 |  |  | 
Constant Name | Units | Value
 | CNT | 
 |  | 
Refer .m file for other constants |  | 
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
