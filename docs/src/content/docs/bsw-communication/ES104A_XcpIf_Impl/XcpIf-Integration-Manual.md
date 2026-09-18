---
title: "Universal Measurement and Calibration Protocol Interface — XcpIf Integration Manual"
description: "Converted Integration Manual from XcpIf Integration Manual.docx (DOCX, 81 KB)."
---

:::note
Converted from `ES104A_XcpIf_Impl/doc/XcpIf Integration Manual.docx` (Integration Manual; original DOCX, about 81 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES104A_XcpIf_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Integration Manual

For

XCP Interface (XcpIf)

VERSION: .0

DATE: --2015

Prepared By: 

Kevin Smith

ESG Software,

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

4.6	OS Configuration Changes	7

5	Integration  DATAFLOW REQUIREMENTS	8

5.1	Required Global Data Inputs	8

5.2	Required Global Data Outputs	8

5.3	Specific Include Path present	8

5.4	Other Header Changes	8

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

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be referred. Developer should track the references.

Global Functions(Non RTE) to be provided to Integration Project

None

Configuration REQUIREMeNTS

Build Time Config

Configuration Files to be provided by Integration Project

Da Vinci Parameter Configuration Changes

DaVinci Interrupt Configuration Changes

Manual Configuration Changes

OS Configuration Changes

Integration  DATAFLOW REQUIREMENTS

Required Global Data Inputs

None

Required Global Data Outputs

None

Specific Include Path present

Yes

Other Header Changes

Runnable Scheduling 

This section specifies the required runnable scheduling.

Memory Map REQUIREMENTS

Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements. 

Usage

Table : ARM Cortex R4 Memory Usage

NvM Blocks

None

Compiler Settings

 Preprocessor MACRO

The file xcp.cfg needs to have “#define XCP_ENABLE_CALIBRATION_MEM_ACCESS_BY_APPL” added. When the XCP component is generated in GENy, this will enable the application read/write calls. 

Optimization Settings

None

Appendix

N/A

Sl. No. | Description | Author | Version | Date | Approved By
1 | Initial version | K. Smith | 1.0 | 6-Jun-15 | 
 |  |  |  |  | 
Abbreviation | Description
DFD | Design functional diagram
MDD | Module design Document
 | 
Sr. No. | Title | Version
1 | MDD Guidelines | 4.0.0
2 | Software Naming Conventions | 
3 | Coding standards | 
4 | FDD | Not available
 | <Add if more available> | 
Module | Required Feature
None | 
