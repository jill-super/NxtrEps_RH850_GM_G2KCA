---
title: "Motor Current Regulator Voltage Limiter — MotCurrRegVltgLimr MDD"
description: "Converted Design / Integration Document from MotCurrRegVltgLimr_MDD.docx (DOCX, 133 KB)."
---

:::note
Converted from `SF105A_MotCurrRegVltgLimr_Impl/doc/MotCurrRegVltgLimr_MDD.docx` (Design / Integration Document; original DOCX, about 133 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF105A_MotCurrRegVltgLimr_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Module Design Document

For

‘MotCurrRegVltgLimr’

VERSION: .0

DATE: 

Prepared By: 

,

Nexteer Automotive,

 Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System.

Revision History

Table of Contents

1	Abbrevations And Acronyms	5

2	References	6

3	High-Level Description	7

4	Design details of software module	8

4.1	Graphical representation	8

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

7	Software Module Implementation	11

7.1	Sub-Module Functions	11

7.1.1	Initialization Functions	11

7.1.1.1	INIT: MotCurrRegVltgLimrInit1	11

7.1.1.1.1	Design Rationale	11

7.1.1.1.2	Module Outputs	11

7.1.1.1.3	Module Internal	11

7.1.2	PERIODIC FUNCTIONS	11

7.1.2.1	INIT: MotCurrRegVltgLimrPER1	11

7.1.2.1.1	Design Rationale	11

7.1.2.1.2	Module Outputs	11

7.1.3	Interrupt Functions	11

7.1.4	Server runnables	12

7.1.4.1.1	Store Local copy of outputs into Module Outputs	12

7.1.5	Local Function/Macro Definitions	12

7.1.5.1.1	 Local function #1	12

7.1.5.1.2	Local function #2	12

7.1.5.1.3	Local function #3	12

7.1.6	GLObAL Function/Macro Definitions	12

7.1.7	Tranisition FUNCTIONS	13

8	Known Limitations With Design	14

9	UNIT TEST CONSIDERATION	15

10	Appendix	16

Abbrevations And Acronyms

References

This section lists the title & version of all the documents that are referred for development of this document

High-Level Description

None

Design details of software module

Graphical representation

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

None

Software Module Implementation

Sub-Module Functions    

Initialization Functions

MotCurrRegVltgLimrInit1

INIT: MotCurrRegVltgLimrInit1

Design Rationale

Design follows implemenetation in FDD.

Module Outputs

Refer ‘MotCurrRegVltgLimrInit’ block in FDD

Module Internal  

None

PERIODIC FUNCTIONS  

INIT: MotCurrRegVltgLimrPER1

Design Rationale

Design follows implemenetation in FDD.

Module Outputs

Design follows implemenetation in FDD.

Interrupt Functions

None

Server runnables

None

Store Local copy of outputs into Module Outputs

None

Local Function/Macro Definitions

 Local function #1

* MotVltgPropCmd_Volt_T_f32 and * MotVltgIntglCmd_Volt_T_f32 are outputs of this function.

Local function #2 

*QaxCmdFinal_Ampr_T_f32 is also an output of this function.

Local function #3 

*CurrLoaScaFac_Uls_T_f32*IvtrLoaScaFac_Uls_T_f32 are outputs of this function.

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
1 | Initial Version | Selva Sengottaiyan | 1.0 | 26-May-2015
2 | Updated graphical representation and added local function information | Nick Saxton | 2.0 | 13-Apr-2016
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
Abbreviation | Description
DFD | Design functional diagram
MDD | Module design Document
FDD | Functional Design Document
Sr. No. | Title | Version
1 | MDD Guidelines | Process
2 | Software Naming Conventions | Process
3 | Software Design and Coding standards | Process
4 | FDD – SF105A_MotCurrRegVltgLimr_Design | See Synergy sub project version
 |  | 
Typedef Name | Element Name | User Defined Type | Legal Range
(min) | Legal Range
(max)
None |  |  |  | 
 |  |  |  | 
