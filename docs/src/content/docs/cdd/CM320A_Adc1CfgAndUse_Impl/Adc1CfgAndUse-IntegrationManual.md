---
title: "Analog to Digital Converter 1 Configuration And Use — Adc1CfgAndUse IntegrationManual"
description: "Converted Integration Manual from Adc1CfgAndUse_IntegrationManual.docx (DOCX, 79 KB)."
---

:::note
Converted from `CM320A_Adc1CfgAndUse_Impl/doc/Adc1CfgAndUse_IntegrationManual.docx` (Integration Manual; original DOCX, about 79 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM320A_Adc1CfgAndUse_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Integration Manual

For

Adc1 Cfg And Use

VERSION: .0

DATE: 09--2016

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

Yes

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

Memory Map REQUIREMENTS

Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements. 

Usage

Table 1: ARM Cortex R4 Memory Usage

NvM Blocks

*See DataDict.m

Compiler Settings

 Preprocessor MACRO

None

Optimization Settings

None

Appendix

None

Sl. No. | Description | Author | Version | Date
1 | Initial version | Selva Sengottaiyan | 1.0 | 4-May-2015
2 | Updated for design rev. 2.0.0 | Rijvi | 2.0 | 05-Feb-2016
 |  |  |  | 
Abbreviation | Description
DFD | Design functional diagram
MDD | Module design Document
 | <ADD  more to the table if applicable>
 | 
 | 
Sr. No. | Title | Version
1 | FDD – CM320A Adc1CfgAndUse | See synergy sub project version
 |  | 
 |  | 
 |  | 
 |  | 
Module | Required Feature
None | N/A
