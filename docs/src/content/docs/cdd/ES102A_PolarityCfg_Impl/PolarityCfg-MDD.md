---
title: "Polarity Configuration — PolarityCfg MDD"
description: "Converted Design / Integration Document from PolarityCfg_MDD.docx (DOCX, 98 KB)."
---

:::note
Converted from `ES102A_PolarityCfg_Impl/doc/PolarityCfg_MDD.docx` (Design / Integration Document; original DOCX, about 98 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES102A_PolarityCfg_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Module Design Document

For

‘PolarityCfg’

VERSION: 1.0

DATE: 26-May-2015

Prepared By: 

Sankardu Varadapureddi,

Nexteer Automotive,

 Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System.

Revision History

Table of Contents

1	Abbrevations And Acronyms	5

2	References	6

3	Power Disconnect High-Level Description	7

4	Design details of software module	8

4.1	Graphical representation of POWER DISCONNECT	8

4.2	Data Flow Diagram	8

4.2.1	Module level DFD	8

4.2.2	Sub-Module level DFD	8

4.3	COMPONENT FLOW DIAGRAM	8

5	Variable Data Dictionary	9

5.1	User defined typedef definition/declaration	9

5.2	Variable definition for enumerated types	9

6	Constant Data Dictionary	10

6.1	Program(fixed) Constants	10

6.1.1	Embedded Constants	10

6.1.1.1	Local	10

6.1.1.2	Global	10

6.1.2	Module specific Lookup Tables Constants	10

7	Software Module Implementation	12

7.1	Sub-Module Functions	12

7.1.1	Initialization Functions	12

7.1.1.1	INIT: PolarityCfgInit	12

7.1.1.1.1	Design Rationale	12

7.1.1.1.2	Module Outputs	12

7.1.1.1.3	Module Internal	12

7.1.2	PERIODIC FUNCTIONS	12

7.1.3	Interrupt Functions	12

7.1.4	Server runnables	13

7.1.4.1	PolarityCfgRead	13

7.1.4.1.1	Design Rationale	13

7.1.4.1.2	Store Module Inputs to Local copies	13

7.1.4.1.3	(Processing of function)………	13

7.1.4.1.4	Store Local copy of outputs into Module Outputs	13

7.1.4.2	PolarityCfgWr	13

7.1.4.2.1	Design Rationale	13

7.1.4.2.2	Store Module Inputs to Local copies	13

7.1.4.2.3	(Processing of function)………	13

7.1.4.2.4	Store Local copy of outputs into Module Outputs	13

7.1.5	Local Function/Macro Definitions	13

7.1.5.1	Local Function #1	13

7.1.5.2	Description	13

7.1.6	GLObAL Function/Macro Definitions	13

7.1.7	Tranisition FUNCTIONS	14

8	Known Limitations With Design	15

9	UNIT TEST CONSIDERATION	16

10	Appendix	17

Abbrevations And Acronyms

References

This section lists the title & version of all the documents that are referred for development of this document

Power Disconnect High-Level Description

This function will identify polarity control settings for certain points in the design.

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

PolarityCfgInit

INIT: PolarityCfgInit

Design Rationale

Design follows implemenetation in FDD.

Module Outputs

Refer ‘PolarityCfgInit’ block in FDD

Module Internal  

None

PERIODIC FUNCTIONS  

None

Interrupt Functions

None

Server runnables

 PolarityCfgRead

Design Rationale

None

Store Module Inputs to Local copies

None

(Processing of function)………

Refer ‘PolarityCfgRead’ block in FDD

Store Local copy of outputs into Module Outputs

None

PolarityCfgWr

Design Rationale

None

Store Module Inputs to Local copies

None

(Processing of function)………

Refer  ‘PolarityCfgWr’ block in FDD

Store Local copy of outputs into Module Outputs

None

Local Function/Macro Definitions

Local Function #1

Description

Design:

if ( (Polarity_Cnt_T_u32 & PolarityMask_Cnt_T_u32) == PolarityMask_Cnt_T_u32 )

                 set  ‘Polarity_Cnt_T_s08’ to ‘1’

         else

                 set  ‘Polarity_Cnt_T_s08’ to ‘-1’

Note:  ‘PolarityMask_Cnt_T_u32’ is a bit field mask and takes values mentioned in table at sec 6.1.1.1

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
1 | Initial Version | Sankardu Varadapureddi | 1.0 | 26-May-2015
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
4 | FDD – ES102A_PolarityCfg_Design | See Synergy sub project version
 |  | 
Typedef Name | Element Name | User Defined Type | Legal Range
(min) | Legal Range
(max)
None |  |  |  | 
 |  |  |  | 
