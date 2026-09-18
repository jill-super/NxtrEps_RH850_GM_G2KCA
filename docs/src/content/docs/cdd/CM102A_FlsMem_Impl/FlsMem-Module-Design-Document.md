---
title: "Flash Memory Handling — FlsMem Module Design Document"
description: "Converted Design / Integration Document from FlsMem Module Design Document.docx (DOCX, 314 KB)."
---

:::note
Converted from `CM102A_FlsMem_Impl/doc/FlsMem Module Design Document.docx` (Design / Integration Document; original DOCX, about 314 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM102A_FlsMem_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

FlsMem

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Software Group,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	FlsMem & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of FlsMem	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Variable Data Dictionary	9

5.1	User defined typedef definition/declaration	9

5.2	Variable definition for enumerated types	9

6	Software Component Implementation	10

6.1	Sub-Module Functions	10

6.1.1	Init: FlsMemInit1	10

6.1.1.1	Design Rationale	10

6.1.1.2	Module Outputs	10

6.1.2	Init: FlsMemInit2	10

6.1.2.1	Design Rationale	10

6.1.2.2	Module Outputs	10

6.1.3	Per: FlsMemPer2	10

6.1.3.1	Design Rationale	10

6.1.3.2	Store Module Inputs to Local copies	10

6.1.3.3	(Processing of function)………	10

6.1.3.4	Store Local copy of outputs into Module Outputs	10

6.2	Server Runnables	11

6.3	Interrupt Functions	11

6.4	Module Internal (Local) Functions	11

6.4.1	Local Function #1	11

6.4.1.1	Design Rationale	11

6.4.1.2	Processing	11

6.5	GLOBAL Function/Macro Definitions	11

6.5.1	DTSInit	11

6.5.1.1	Design Rationale	11

6.5.1.2	Processing	14

6.5.2	DTSClnUp	14

6.5.2.1	Design Rationale	14

6.5.2.2	Processing	14

7	Known Limitations with Design	15

8	UNIT TEST CONSIDERATION	16

Appendix A	Abbreviations and Acronyms	17

Appendix B	Glossary	18

Appendix C	References	19

Introduction

Purpose

Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance. 

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.  

May: indicates an optional action.

FlsMem & High-Level Description

See FDD

Design details of software module

Graphical representation of FlsMem

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

<This section documents any user types uniquely used for the module.>

Variable definition for enumerated types

Software Component Implementation

Sub-Module Functions

Init: FlsMemInit1

Design Rationale

Empty function for purposes of memory mapping

Module Outputs

None

Init: FlsMemInit2

Design Rationale

The FlsMemInit2 function is a non RTE function which shall be called to set up the DTS configuration for the Flash CRC check. The DTS channel configuration has to be applied only when the system is waking up from a Power On Reset or after a flash programming reset. In such a scenario a Hardware CRC unit is allocated by function call to the CRC module and once a hardware assignment is successful, the DTS channels are configured for chaining for the entire definition of the flash blocks (Boot, App, Cal1, Cal2 etc.). Record the time when the DTS transfer is initiated so that a check on a timeout can be made in the periodic function where a maximum timeout of 200 ms is checked for

This function shall be called in the startup sequence. Hence it is a non RTE function

See FDD for more.

Module Outputs

None

None

Per: FlsMemPer2

Design Rationale

See FDD

Store Module Inputs to Local copies

Refer to FDD

(Processing of function)………

Refer to FDD

Store Local copy of outputs into Module Outputs

Refer to FDD

Server Runnables 

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

Processing

GLOBAL Function/Macro Definitions

Design Rationale

Trusted function that performs all register initialization from the CM102A_FlsMem_DTSPeripheralCfg.xlsx spreadsheet in the FDD.  The DTSMstrCfg channel master registers can be written only in supervisor mode.  After the Channel master register for a given channel has been written, the selected Processor Element can write to that channel’s registers.  However, for simplicity, all DTS register initialization and chaining is being done in one trusted function.  

The chaining is done in the following manner

Consider the first flash region to have the CRC calculated 

Calculate the number of DTS chains required for the length of the CRC region. Each DTS channel can address up to a maximum of 0x3FFFC bytes of data (0xFFFF maximum transfer count multiplied by 4 bytes of data in each transfer).

Hence number of channel is equal to Region length/0x3FFFC + {1} if (Region length % 0x3FFFC is non zero)

Clear the DTS Transfer flag to make sure no pending requests are present for all the used channels

Configure the DTS channels starting from 0 using the configuration defined as per CM102A_FlsMem_DTSPeripheralCfg.xlsx for the above calculated number of chains

Configure the next DTS channel to transfer the CRC result from CRC HW output register to Per Instance Memory

Configure the next DTS channel to transfer zero value to the CRC HW output register to clear the output register to continue with next flash region operation

Repeat Step 1 thru 5 for all the flash regions(Boot, App, Cal1, Cal2 etc) The definition of the flash region is in the generated file CDD_FlsMem_Cfg.c which takes inputs defined in the Vector configurator Tool

Disable chaining on the last channel

Enable the Interrupt on the second last channel

Clear the interrupt status register which shall be monitored in the periodic

Start the DTS transfer

Processing

Design Rationale

None

Processing

None

Known Limitations with Design

We have made use of a static constant global variable (static const uint32 CrcClrData_M = 0U)  for the purpose of clearing the CRC hardware 

Also the result array (HwCrcCalcdRes_C[8]) has been also declared as a global array for the purpose of DTS write access in the MotCtrlMgr_MemMap memory map section

UNIT TEST CONSIDERATION

None

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
Initial Version | Lucas Wendling | 1.0 | 10/06/15
Updated with changes for DTS configuration for Flash CRC check | Avinash James | 2.0 | 03/18/16
Updates for DTS Transfer Clear | Avinash James | 3.0 | 3/29/16
Updated for removing the flash ECC single bit error handling and disabling the DTS channels after calculation | Avinash James | 4.0 | 3/31/16
Trusted function call for the DTS clean up updates | Avinash James | 5.0 | 04/18/16
 |  |  | 
Constant Name | Resolution | Units | Value
CPU1PEID_CNT_U32 | 1 | uint32 | 0x01U
CODFLSTOCRCSPID_CNT_U32 | 1 | uint32 | 0x02U
CRCTOLCLRAMSPID_CNT_U32 | 1 | uint32 | 0x00U
USRMODDIS_CNT_U32 | 1 | uint32 | 0x00U
FLSBLKLEN_CNT_U32 | 1 | uint32 | 0x0003FFFCU
DTSDATALEN_CNT_U32 | 1 | uint32 | 4U
CRCCHKMAXALLWDTI_CNT_U32 | 1 | uint32 | 2000
MAXNROFDTSCH_CNT_U32 | 1 | uint32 | 32
 |  |  | 
 |  |  | 
 |  |  | 
 |  |  | 
Typedef Name | Element Name | User Defined Type | Legal Range
(min) | Legal Range
(max)
FlsCrcCfgBlkRec | CrcFlsBlkStrtAdr | uint32 | 0 | 0xFFFFFFFFH
 | CrcFlsBlkLen | uint32 | 0 | 0xFFFFFFFFH
 | PreCalcnCrcFlsAdr | uint32* | 0 | 0xFFFFFFFFH
Enum  Name | Element Name | Value
<(Name given for the user defined typdef of type struct/union)
(Variable name qualified in refer[2])> | <(Variable name qualified Refer[2])> | <Define the value >
