---
title: "Analog to Digital Converter 0 Configuration And Use — Adc0CfgAndUse IntegrationManual"
description: "Converted Integration Manual from Adc0CfgAndUse_IntegrationManual.docx (DOCX, 83 KB)."
---

:::note
Converted from `CM300A_Adc0CfgAndUse_Impl/doc/Adc0CfgAndUse_IntegrationManual.docx` (Integration Manual; original DOCX, about 83 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM300A_Adc0CfgAndUse_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Integration Manual

For

Adc0 Cfg And Use

VERSION: .0

DATE: --2016

Prepared By: 

Software Group,

Nexteer Automotive,

 Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System.

Revision History

Table of Contents

Abbrevations And Acronyms

References

This section lists the title & version of all the documents that are referred for development of this document

Dependencies

SWCs

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be referred. Developer should track the references.

Global Functions(Non RTE) to be provided to Integration Project

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

Table : ARM Cortex R4 Memory Usage

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
<1> | FDD – CM300A Adc0CfgAndUse | See synergy sub project version
 |  | 
 |  | 
 |  | 
 |  | 
Module | Required Feature
 | 
