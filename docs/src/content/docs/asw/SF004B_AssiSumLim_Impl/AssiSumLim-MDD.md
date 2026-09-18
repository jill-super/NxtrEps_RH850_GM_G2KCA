---
title: "Assist Summation Limiter — AssiSumLim MDD"
description: "Converted Design / Integration Document from AssiSumLim_MDD.docx (DOCX, 107 KB)."
---

:::note
Converted from `SF004B_AssiSumLim_Impl/doc/AssiSumLim_MDD.docx` (Design / Integration Document; original DOCX, about 107 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF004B_AssiSumLim_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Module Design Document

For

‘AssiSumLim’

VERSION: 1.0

DATE: 03-June-2015

Prepared By: 

Sankardu Varadapureddi,

Nexteer Automotive,

 Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System.

Revision History

Table of Contents

1	Abbrevations And Acronyms	5

2	References	6

3	AssiSumLim High-Level Description	7

4	Design details of software module	8

4.1	Graphical representation of AssiSumLim	8

4.2	Data Flow Diagram	8

4.2.1	Module level DFD	8

4.2.2	Sub-Module level DFD	9

4.3	COMPONENT FLOW DIAGRAM	9

5	Variable Data Dictionary	10

5.1	User defined typedef definition/declaration	10

5.2	Variable definition for enumerated types	10

6	Constant Data Dictionary	11

6.1	Program(fixed) Constants	11

6.1.1	Embedded Constants	11

6.1.1.1	Local	11

6.1.1.2	Global	11

6.1.2	Module specific Lookup Tables Constants	11

7	Software Module Implementation	12

7.1	Sub-Module Functions	12

7.1.1	Initialization Functions	12

7.1.1.1	INIT: AssiSumLimInit1	12

7.1.1.1.1	Design Rationale	12

7.1.1.1.2	Module Outputs	12

7.1.1.1.3	Module Internal	12

7.1.2	PERIODIC FUNCTIONS	12

7.1.2.1	Per: AssiSumLimPer1	12

7.1.2.1.1	Design Rationale	12

7.1.2.1.2	Store Module Inputs to Local copies	12

7.1.2.1.3	(Processing of function)………	12

7.1.2.1.4	Store Local copy of outputs into Module Outputs	12

7.1.3	Interrupt Functions	12

7.1.4	Server runnables	13

7.1.4.1	SetManTqCmd	13

7.1.4.1.1	Design Rationale	13

7.1.4.1.2	Store Module Inputs to Local copies	13

7.1.4.1.3	(Processing of function)………	13

7.1.4.1.4	Store Local copy of outputs into Module Outputs	13

7.1.5	Local Function/Macro Definitions	13

7.1.5.1	Local Function #1	13

7.1.5.1.1	Description	13

7.1.5.2	Local Function #2	13

7.1.5.2.1	Description	13

7.1.6	GLObAL Function/Macro Definitions	13

7.1.7	Tranisition FUNCTIONS	13

8	Known Limitations With Design	14

9	UNIT TEST CONSIDERATION	15

10	Appendix	16

Abbrevations And Acronyms

References

This section lists the title & version of all the documents that are referred for development of this document

AssiSumLim High-Level Description

Design details of software module

Graphical representation of AssiSumLim

Data Flow Diagram

 Refer FDD

Module level DFD

Refer FDD

Sub-Module level DFD

Refer FDD

COMPONENT FLOW DIAGRAM

Refer FDD

Variable Data Dictionary

User defined typedef definition/declaration 

<This section documents any user types uniquely used for the module.>

Variable definition for enumerated types

Constant Data Dictionary

Program(fixed) Constants

Embedded Constants

Local         

Note: Refer .m file for constants definitions.

Global

Module specific Lookup Tables Constants

Software Module Implementation

Sub-Module Functions    

Initialization Functions

AssiSumLimInit1

INIT: AssiSumLimInit1

Design Rationale

Design follows implemenetation in FDD.

Module Outputs

Refer ‘AssiSumLimInit1’ block in FDD

Module Internal  

None

PERIODIC FUNCTIONS  

Per: AssiSumLimPer1

Design Rationale

Design follows implementation in FDD. 

Store Module Inputs to Local copies

Refer to FDD

 (Processing of function)………

Refer to FDD  (Block ‘AssiSumLmtPer1’)

Store Local copy of outputs into Module Outputs

Refer to FDD

Interrupt Functions

None

Server runnables

 SetManTqCmd

Design Rationale

None

Store Module Inputs to Local copies

None

(Processing of function)………

Refer ‘SetManTqCmd’ block in FDD

Store Local copy of outputs into Module Outputs

None

Local Function/Macro Definitions

None 

GLObAL Function/Macro Definitions

None

Tranisition FUNCTIONS     

None

Known Limitations With Design

None

UNIT TEST CONSIDERATION

None

Appendix

None

Sl. No. | Description | Author | Version | Date
1 | Initial Version | Sankardu Varadapureddi | 1.0 | 03-June-2015
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
Abbreviation | Description
DFD | Design functional diagram
MDD | Module design Document
FDD | Functional Design Document
Sr. No. | Title | Version
1 | MDD Guidelines | Process 3.06.00
2 | Software Naming Conventions | Process 3.06.00
3 | Software Design and Coding standards | Process 3.06.00
4 | FDD - SF004B_AssiSumLim_Design | See Synergy sub project version
 |  | 
Typedef Name | Element Name | User Defined Type | Legal Range
(min) | Legal Range
(max)
None |  |  |  | 
 |  |  |  | 
