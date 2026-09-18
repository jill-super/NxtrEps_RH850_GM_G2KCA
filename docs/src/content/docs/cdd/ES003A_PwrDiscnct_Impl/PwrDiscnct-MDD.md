---
title: "Power Disconnect — PwrDiscnct MDD"
description: "Converted Design / Integration Document from PwrDiscnct_MDD.docx (DOCX, 93 KB)."
---

:::note
Converted from `ES003A_PwrDiscnct_Impl/doc/PwrDiscnct_MDD.docx` (Design / Integration Document; original DOCX, about 93 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES003A_PwrDiscnct_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Module Design Document

For

‘PwrDiscnct’

VERSION: 1.0

DATE: 09-Apr-2015

Prepared By: 

Sankardu Varadapureddi,

Nexteer Automotive,

 Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System.

Revision History

Table of Contents

1	Abbrevations And Acronyms	4

2	References	5

3	Power Disconnect High-Level Description	6

4	Design details of software module	7

4.1	Graphical representation of POWER DISCONNECT	7

4.2	Data Flow Diagram	7

4.2.1	Module level DFD	7

4.2.2	Sub-Module level DFD	7

4.3	COMPONENT FLOW DIAGRAM	7

5	Variable Data Dictionary	8

5.1	User defined typedef definition/declaration	8

5.2	Variable definition for enumerated types	8

6	Constant Data Dictionary	9

6.1	Program(fixed) Constants	9

6.1.1	Embedded Constants	9

6.1.1.1	Local	9

6.1.1.2	Global	9

6.1.2	Module specific Lookup Tables Constants	9

7	Software Module Implementation	10

7.1	Sub-Module Functions	10

7.1.1	Initialization Functions	10

7.1.2	PERIODIC FUNCTIONS	10

7.1.2.1	Per: PwrDiscnct_Per1	10

7.1.2.1.1	Design Rationale	10

7.1.2.1.2	Store Module Inputs to Local copies	10

7.1.2.1.3	(Processing of function)………	10

7.1.2.1.4	Store Local copy of outputs into Module Outputs	10

7.1.3	Interrupt Functions	10

7.1.4	Serial Communication Functions	11

7.1.5	Local Function/Macro Definitions	11

7.1.6	GLObAL Function/Macro Definitions	11

7.1.7	Tranisition FUNCTIONS	11

8	Known Limitations With Design	12

9	UNIT TEST CONSIDERATION	13

10	Appendix	14

Abbrevations And Acronyms

References

This section lists the title & version of all the documents that are referred for development of this document

Power Disconnect High-Level Description

This function will verify that the PowerDisconnect is not stuck closed at init once per Ignition Cycle.

Design details of software module

Graphical representation of POWER DISCONNECT

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

Global

Module specific Lookup Tables Constants

Software Module Implementation

Sub-Module Functions    

Initialization Functions

None

PERIODIC FUNCTIONS  

Per: PwrDiscnctPer1

Design Rationale

Design follows implemenetation in FDD. 

Store Module Inputs to Local copies

Refer to FDD

 (Processing of function)………

Refer to FDD  (Block ‘PwrDiscnct’)

Store Local copy of outputs into Module Outputs

Refer to FDD

Interrupt Functions

None

Serial Communication Functions

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

Appendix

None

Sl. No. | Description | Author | Version | Date
1 | Initial Version | Sankardu Varadapureddi | 1.0 | 09-Apr-2015
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
4 | FDD - ES003A_PwrDiscnct_Design | See Synergy sub project version
 |  | 
Typedef Name | Element Name | User Defined Type | Legal Range
(min) | Legal Range
(max)
None |  |  |  | 
 |  |  |  | 
