---
title: "Current Measurement — CurrMeas IntegrationManual"
description: "Converted Integration Manual from CurrMeas_IntegrationManual.docx (DOCX, 80 KB)."
---

:::note
Converted from `ES200A_CurrMeas_Impl/doc/CurrMeas_IntegrationManual.docx` (Integration Manual; original DOCX, about 80 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES200A_CurrMeas_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Integration Manual

For

CURRENT MEASUREMENT 

VERSION: .0

DATE: 

Prepared By: 

Software Group,

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

7.3	Non  RTE NvM Blocks	10

7.4	RTE NvM Blocks	10

8	Compiler Settings	11

8.1	Preprocessor MACRO	11

8.2	Optimization Settings	11

9	Appendix	12

Abbrevations And Acronyms

References

This section lists the title & version of all the documents that are referred for development of this document

Dependencies

SWCs

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be referred. Developer should track the references.

Global Functions(Non RTE) to be provided to Integration Project

CurrMeasPer2()

Configuration REQUIREMeNTS

Build Time Config

Configuration Files to be provided by Integration Project

None

Da Vinci Parameter Configuration Changes

DaVinci Interrupt Configuration Changes

Manual Configuration Changes

Integration  DATAFLOW REQUIREMENTS

Required Global Data Inputs

Refer DataDict.m file

Required Global Data Outputs

Refer DataDict.m file

Specific Include Path present

Yes

Runnable Scheduling 

This section specifies the required runnable scheduling.

.

Memory Map REQUIREMENTS

Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements. 

Usage

Table : ARM Cortex R4 Memory Usage

Non  RTE NvM Blocks

Note : Size of the NVM block if configured in developer   

 RTE NvM Blocks

Note : Size of the NVM block if configured in developer   

The NVM block needs not used.

Compiler Settings

 Preprocessor MACRO

None

Optimization Settings

None

Appendix

None

Sl. No. | Description | Author | Version | Date
1 | Initial version | Selva Sengottaiyan | 1.0 | 4-May-2015
2 | Added fault injection | Nick Saxton | 2.0 | 10-Aug-2015
3 | Updated to v 3.1.0 of FDD | Selva Sengottaiyan | 3.0 | 29-Sep-2015
 |  |  |  | 
Abbreviation | Description
DFD | Design functional diagram
MDD | Module design Document
 | <ADD  more to the table if applicable>
 | 
 | 
Sr. No. | Title | Version
<1> | FDD – ES200A Current Measurement | See synergy subversion
 |  | 
 |  | 
 |  | 
 |  | 
Module | Required Feature
None | N/A
