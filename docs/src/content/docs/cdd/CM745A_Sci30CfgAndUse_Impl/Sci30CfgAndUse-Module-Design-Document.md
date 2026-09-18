---
title: "Sci30 Configuration And Use — Sci30CfgAndUse Module Design Document"
description: "Converted Design / Integration Document from Sci30CfgAndUse Module Design Document.docx (DOCX, 87 KB)."
---

:::note
Converted from `CM745A_Sci30CfgAndUse_Impl/doc/Sci30CfgAndUse Module Design Document.docx` (Design / Integration Document; original DOCX, about 87 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM745A_Sci30CfgAndUse_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

Sci30CfgAndUse

Jan 20, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Software Group,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1.1	Purpose	5

1.1.2	Scope	5

2	Sci30CfgAndUse & High-Level Description	6

3	Design details of software module	7

3.1.1	Graphical representation of Sci30CfgAndUse	7

3.1.2	Data Flow Diagram	7

3.1.3	Component level DFD	7

3.1.4	Function level DFD	7

4	Constant Data Dictionary	8

4.1.1	Program (fixed) Constants	8

4.1.2	Embedded Constants	8

5	Variable Data Dictionary	9

5.1.1	User defined typedef definition/declaration	9

5.1.2	Variable definition for enumerated types	9

6	Software Component Implementation	10

6.1.1	Sub-Module Functions	10

6.1.2	Init: Sci30CfgAndUseInit1	10

6.1.3	Design Rationale	10

6.1.4	Module Outputs	10

6.1.5	Per: Sci30CfgAndUsePer1	10

6.1.6	Per: Sci30CfgAndUsePer2	10

6.1.7	Per: Sci30CfgAndUsePer3	11

6.1.8	Per: Sci30CfgAndUsePer4	11

6.1.9	Server Runnables	11

6.1.10	Interrupt Functions	12

6.1.11	Module Internal (Local) Function: RollOvrAdd	12

6.1.12	Module Internal (Local) Function: UpdDtsTxReg	12

6.1.13	Module Internal (Local) Function: UpdDtsRxReg	12

6.1.14	GLOBAL Function/Macro Definitions	12

7	Known Limitations with Design	14

8	UNIT TEST CONSIDERATION	15

Appendix A	Abbreviations and Acronyms	16

Appendix B	Glossary	17

Appendix C	References	18

Introduction

Purpose

Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance. 

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.  

May: indicates an optional action.

Sci30CfgAndUse & High-Level Description

See FDD

Design details of software module

Graphical representation of Sci30CfgAndUse

Data Flow Diagram

Component level DFD

See FDD

Function level DFD

See FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Variable Data Dictionary

User defined typedef definition/declaration 

Variable definition for enumerated types

Software Component Implementation

We have the global transmit and receive buffers declared at the file level as static variables in different memory map sections. The global transmit is in a memory map section aligned at 128 bit boundary in the Sci30CfgAndUse data section as DTS has to read the data from the buffer. The global memory map is also aligned on a 128 bit boundary but defined in the .data_dma_128 memory map as the DTS has to write data to the buffer

Sub-Module Functions

Init: Sci30CfgAndUseInit1

Design Rationale

Refer FDD

Module Outputs

None

Per: Sci30CfgAndUsePer1

Design Rationale

See FDD

Store Module Inputs to Local copies

Refer to FDD

(Processing of function)………

Refer to FDD

Store Local copy of outputs into Module Outputs

Refer to FDD

Module Outputs

None

Per: Sci30CfgAndUsePer2

Design Rationale

See FDD

Store Module Inputs to Local copies

Refer to FDD

(Processing of function)………

Refer to FDD

Store Local copy of outputs into Module Outputs

Refer to FDD

Module Outputs

None

Per: Sci30CfgAndUsePer3

Design Rationale

See FDD

Store Module Inputs to Local copies

Refer to FDD

(Processing of function)………

Refer to FDD

Store Local copy of outputs into Module Outputs

Refer to FDD

Module Outputs

None

Per: Sci30CfgAndUsePer4

Design Rationale

See FDD

Store Module Inputs to Local copies

Refer to FDD

(Processing of function)………

Refer to FDD

Store Local copy of outputs into Module Outputs

Refer to FDD

Module Outputs

None

Server Runnables 

None

Design Rationale

Store Module Inputs to Local copies

 (Processing of function)………

Store Local copy of outputs into Module Outputs

Interrupt Functions

None

Module Internal (Local) Function: RollOvrAdd

Design Rationale

Function which returns the index value rolled over the max number of bytes received

Processing

Module Internal (Local) Function: UpdDtsTxReg

Design Rationale

Processing

Module Internal (Local) Function: UpdDtsRxReg

Design Rationale

Processing

GLOBAL Function/Macro Definitions

IninSciDtsChMstReg

Design Rationale

The DTS channel master registers can only be configured in the supervisor mode. Hence we need to make use of a trusted function to configure the channel master registers

Processing

Known Limitations with Design

UNIT TEST CONSIDERATION

*Rte_Pim_SciDiagcRxMaxDataErrCntr(),*Rte_Pim_SciDiagcOvrrunErrCntr(),*Rte_Pim_SciDiagcParErrCntr() and *Rte_Pim_SciDiagcFrmErrCntr()are used as rolling counters. Hence rollover on them is intentional.

Abbreviations and Acronyms

Glossary

Note: Terms and definitions from the source “Nexteer Automotive” take precedence over all other definitions of the same term.  Terms and definitions from the source “Nexteer Automotive” are formulated from multiple sources, including the following:

ISO 9000

ISO/IEC 12207

ISO/IEC 15504

Automotive SPICE® Process Reference Model (PRM)

Automotive SPICE® Process Assessment Model (PAM)

ISO/IEC 15288

ISO 26262

IEEE Standards

SWEBOK

PMBOK

Existing Nexteer Automotive documentation

References

Description | Author | Version | Date
Initial Version | Avinash James | 1.0 | 01/20/17
Constant Name | Resolution | Units | Value
SCITXMAXBUFSIZE_CNT_U08 | 1 | Cnt | 80
IMCARBNRXDATASRCSCI_CNT_U08 | 1 | Cnt | 1
Refer .m file |  |  | 
Typedef Name | Element Name | User Defined Type | Legal Range
(min) | Legal Range
(max)
Ary1D_u8_Sci30CfgAndUseA |  |  |  | 
Ary2D_u8_Sci30CfgAndUseA |  |  |  | 
Ary2D_u8_Sci30CfgAndUseB |  |  |  | 
Ary2D_u8_Sci30CfgAndUseC |  |  |  | 
Enum  Name | Element Name | Value
 |  | 
