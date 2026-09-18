---
title: "Universal Measurement and Calibration Protocol Interface — XcpIf MDD"
description: "Converted Design / Integration Document from XcpIf_MDD.docx (DOCX, 1130 KB)."
---

:::note
Converted from `ES104A_XcpIf_Impl/doc/XcpIf_MDD.docx` (Design / Integration Document; original DOCX, about 1130 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES104A_XcpIf_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Module Design Document

For

XCP Interface (XcpIf)

VERSION: .0

DATE: --

Prepared By: 

Kevin Smith

EPS Software,

Nexteer Automotive,

 Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System.

Revision History

Table of Contents

1	Abbrevations And Acronyms	5

2	References	6

3	XCP Interface & High-Level Description	7

4	Design details of software module	8

4.1	Graphical representation of XCP Interface	8

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

7.2	Initialization Functions	11

7.3	PERIODIC FUNCTIONS	11

7.3.1	Xcp2msDaq	11

7.3.1.1	Design Rationale	11

7.3.1.2	Store Module Inputs to Local copies	11

7.3.1.3	(Processing of function)………	11

7.3.1.4	Store Local copy of outputs into Module Outputs	11

7.4	Non PERIODIC FUNCTIONS	11

7.5	Interrupt Functions	11

7.6	Serial Communication Functions	11

7.7	Local Function/Macro Definitions	11

7.8	GLObAL Function/Macro Definitions	11

7.8.1	ApplXcpGetTimestamp	11

7.8.1.1	Description	12

7.8.2	ApplXcpGetPointer	12

7.8.2.1	Description	12

7.8.3	ApplXcpCalibrationWrite	12

7.8.3.1	Description	12

7.8.4	ApplXcpWrCmn	13

7.8.4.1	Description	13

7.8.5	ApplXcpCalibrationRead	13

7.8.5.1	Description	13

7.9	TRANSIENT FUNCTIONS	13

8	Unit Test Considerations	14

9	Known Limitations With Design	15

10	Appendix	16

Abbrevations And Acronyms

References

This section lists the title & version of all the documents that are referred for development of this document

XCP Interface & High-Level Description

XCP Interface provides multiple functions that allow XCP end users and tools to interface with software components contained in the application. 

Design details of software module

Graphical representation of XCP Interface

None

Data Flow Diagram

None

Module level DFD

None

Sub-Module level DFD

None

COMPONENT FLOW DIAGRAM

None

Variable Data Dictionary

User defined typedef definition/declaration 

Variable definition for enumerated types

Constant Data Dictionary

Program(fixed) Constants

Embedded Constants

Local

Global

Module specific Lookup Tables Constants

Software Module Implementation

Sub-Module Functions

None

Initialization Functions

None

PERIODIC FUNCTIONS  

Xcp2msDaq

Design Rationale

This function is called every 2ms for executing the XcpEvent functions for the 2ms DAQ.

Store Module Inputs to Local copies

None

(Processing of function)………

Store Local copy of outputs into Module Outputs

None

Non PERIODIC FUNCTIONS  

None

Interrupt Functions

None

Serial Communication Functions

None

Local Function/Macro Definitions

None

GLObAL Function/Macro Definitions

ApplXcpGetTimestamp

Description

This function returns the timestamp that is based on a reference timer. The range of return values vary depending on the configuration of the Xcp Component. The data type can range from a full range of a uint8 to a uint32 value. 

ApplXcpGetPointer

Description

This function takes the extension and address of and returns the physical address of the item.

ApplXcpCalibrationWrite

Description

This function calls the common XCP writing function. For this deisgn, the function call will be translated into a trusted function call.

ApplXcpWrCmn

Description

This function writes the data passed in by the XCP user to the designated address.

ApplXcpCalibrationRead

Description

This function reads the data in the designated address and returns it to the XCP user.

TRANSIENT FUNCTIONS  

None

Unit Test Considerations

The value datatype of XcpDaqTimestampType can be uint8, uint16, or uint32 depending on the configuration of XCP. Unit testing shall test full ranges for all three types to ensure proper functionality. 

Known Limitations With Design

There are no protections in this design for executing on NULL_PTRs

Appendix

None

Sl. No. | Description | Author | Version | Date | Approved By
1 | Initial Version | K. Smith | 1.0 | 16Jun15 | 
 |  |  |  |  | 
Abbreviation | Description
DFD | Design functional diagram
MDD | Module design Document
 | <ADD  more to the table if applicable>
 | 
Sr. No. | Title | Version
<1> | <MDD Guidelines> | 4.0.0
<2> | <Software Naming Conventions> | 4.0.0
<3> | <Coding standards> | 4.0.0
<4> | <FDD > | Not available
 | <Add if more available> | 
Typedef Name | Element Name | User Defined Type | Legal Range
(min) | Legal Range
(max)
 |  |  |  | 
 |  |  |  | 
