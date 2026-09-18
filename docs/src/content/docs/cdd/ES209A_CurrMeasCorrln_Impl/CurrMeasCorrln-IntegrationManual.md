---
title: "Current Measurement Correlation — CurrMeasCorrln IntegrationManual"
description: "Converted Integration Manual from CurrMeasCorrln_IntegrationManual.docx (DOCX, 79 KB)."
---

:::note
Converted from `ES209A_CurrMeasCorrln_Impl/doc/CurrMeasCorrln_IntegrationManual.docx` (Integration Manual; original DOCX, about 79 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES209A_CurrMeasCorrln_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Integration Manual

For

CURRENT MEASUREMENT CORRELATION

VERSION: 2

DATE: 2--201

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

Refer DataDict.m file

Required Global Data Outputs

Refer DataDict.m file

Specific Include Path present

No

Runnable Scheduling 

This section specifies the required runnable scheduling.

.

Memory Map REQUIREMENTS

Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements. 

Usage

Table 1: ARM Cortex R4 Memory Usage

Non  RTE NvM Blocks

Note : Size of the NVM block if configured in developer   

 RTE NvM Blocks

Note : Size of the NVM block if configured in developer   

Compiler Settings

 Preprocessor MACRO

None

Optimization Settings

None

Appendix

None

Sl. No. | Description | Author | Version | Date
1 | Initial version | Selva Sengottaiyan | 1.0 | 09-Apr-2015
 |  |  |  | 
 |  |  |  | 
Abbreviation | Description
DFD | Design functional diagram
MDD | Module design Document
 | <ADD  more to the table if applicable>
 | 
 | 
Sr. No. | Title | Version
<1> | FDD - ES209A Current Measurement Correlation | <.2.0>
 |  | 
 |  | 
 |  | 
 |  | 
Module | Required Feature
None | N/A
