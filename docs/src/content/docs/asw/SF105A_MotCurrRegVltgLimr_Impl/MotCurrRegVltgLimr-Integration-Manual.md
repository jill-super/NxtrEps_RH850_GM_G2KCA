---
title: "Motor Current Regulator Voltage Limiter — MotCurrRegVltgLimr Integration Manual"
description: "Converted Integration Manual from MotCurrRegVltgLimr_Integration Manual.docx (DOCX, 78 KB)."
---

:::note
Converted from `SF105A_MotCurrRegVltgLimr_Impl/doc/MotCurrRegVltgLimr_Integration Manual.docx` (Integration Manual; original DOCX, about 78 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF105A_MotCurrRegVltgLimr_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Integration Manual

For

‘MotCurrRegVltgLimr’

VERSION: 1.0

DATE: 26-May-2015

Prepared By: 

Selva Sengottaiyan

Nexteer Automotive,

 Saginaw, MI, USA

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

Refer DataDict.m file file in the FDD

Specific Include Path present

Yes

Runnable Scheduling 

This section specifies the required runnable scheduling.

Memory Map REQUIREMENTS

Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements. 

Usage

Table : ARM Cortex R4 Memory Usage

Non  RTE NvM Blocks

RTE NvM Blocks

Compiler Settings

 Preprocessor MACRO

None.

Optimization Settings

None

Appendix

None

Sl. No. | Description | Author | Version | Date
1 | Initial version | Selva Sengottaiyan | 1.0 | 4-June-2015
 |  |  |  | 
Abbreviation | Description
DFD | Design functional diagram
MDD | Module design Document
 | 
 | 
Sr. No. | Title | Version
1 | FDD – SF105A_MotCurrRegVltgLimr_Design | See Synergy sub project version
2 | Software Naming Conventions | Process 4.00.00
3 | Software Design and Coding Standards | Process 4.00.00
 |  | 
 |  | 
Module | Required Feature
None | 
