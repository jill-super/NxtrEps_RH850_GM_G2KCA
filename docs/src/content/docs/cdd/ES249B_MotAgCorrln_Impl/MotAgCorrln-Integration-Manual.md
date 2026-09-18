---
title: "Motor Angle Correlation — MotAgCorrln Integration Manual"
description: "Converted Integration Manual from MotAgCorrln_Integration Manual.docx (DOCX, 76 KB)."
---

:::note
Converted from `ES249B_MotAgCorrln_Impl/doc/MotAgCorrln_Integration Manual.docx` (Integration Manual; original DOCX, about 76 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES249B_MotAgCorrln_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Integration Manual

For

‘MotAgCorrln’

VERSION: 1.0

DATE: 01 JUN 2016

Prepared By: 

Software Engineering,

Nexteer Automotive,

 Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System.

Revision History

Table of Contents

1	Abbrevations And Acronyms	4

2	References	5

3	Dependencies	6

3.1	SWCs	6

3.2	Global Functions(Non RTE) to be provided to Integration Project	6

4	Configuration REQUIREMeNTS	7

4.1	Build Time Config	7

4.2	Configuration Files to be provided by Integration Project	7

4.3	Da Vinci Parameter Configuration Changes	7

4.4	DaVinci Interrupt Configuration Changes	7

4.5	Manual Configuration Changes	7

5	Integration  DATAFLOW REQUIREMENTS	8

5.1	Required Global Data Inputs	8

5.2	Required Global Data Outputs	8

5.3	Specific Include Path present	8

6	Runnable Scheduling	9

7	Memory Map REQUIREMENTS	10

7.1	Mapping	10

7.2	Usage	10

7.3	NvM Blocks	10

8	Compiler Settings	11

8.1	Preprocessor MACRO	11

8.2	Optimization Settings	11

9	Appendix	12

Abbrevations And Acronyms

References

This section lists the title & version of all the documents that are referred for development of this document

Dependencies

SWCs

Global Functions(Non RTE) to be provided to Integration Project

None

Configuration REQUIREMeNTS

Build Time Config

Configuration Files to be provided by Integration Project

None

Da Vinci Parameter Configuration Changes

DaVinci Interrupt Configuration Changes

Manual Configuration Changes

Integration  DATAFLOW REQUIREMENTS

Required Global Data Inputs

Refer DataDict.m file in the FDD

Required Global Data Outputs

Refer DataDict.m file in the FDD

Specific Include Path present

No

Runnable Scheduling 

This section specifies the required runnable scheduling.

.

Memory Map REQUIREMENTS

Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements. 

Usage

Table : ARM Cortex R4 Memory Usage

NvM Blocks

None

Compiler Settings

 Preprocessor MACRO

None

Optimization Settings

None

Appendix

None

Sl. No. | Description | Author | Version | Date
1 | Initial version | Nick Saxton | 1.0 | 01-Jun-2016
Abbreviation | Description
DFD | Design functional diagram
MDD | Module design Document
 | 
 | 
 | 
Sr. No. | Title | Version
1 | FDD – ES249B_MotAgCorrln_Design | See Synergy sub project version
2 | Software Naming Conventions | Process 04.2.00
3 | Software Design and Coding Standards | Process 04.2.00
 |  | 
 |  | 
Module | Required Feature
None | 
