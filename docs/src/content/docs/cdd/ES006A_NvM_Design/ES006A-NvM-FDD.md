---
title: "Non-Volatile M — ES006A NvM FDD"
description: "Converted Design / Integration Document from ES006A_NvM_FDD.docx (DOCX, 442 KB)."
---

:::note
Converted from `ES006A_NvM_Design/Doc/ES006A_NvM_FDD.docx` (Design / Integration Document; original DOCX, about 442 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES006A_NvM_Design](./)

*Conversion method: automatic text extraction from the Word document.*

Non Volatile RAM Manager And 

Non Volatile RAM Manager Proxy

FDD #ES-006A

Contents

1.	High Level Description	4

2.	Derived Requirements	4

3.	Sub-Function Data Flow	4

4.	Design Rationale	5

5.	Components	6

5.1.	NvM: Non Volatile Memory (AUTOSAR BSW)	6

5.1.1.	BSW Configuration	6

5.1.1.1.	NvMCommon	6

5.1.2.	Periodic Functions	7

5.1.2.1.	NvM_MainFunction	7

5.1.2.1.1.	Function Definition	7

5.1.3.	Service Sub-Functions	8

5.1.3.1.	API Configuration Class 1	9

5.1.3.1.1.	Sub-Function: NvM_Init	9

5.1.3.1.2.	Sub-Function: NvM_ReadAll	10

5.1.3.1.3.	Sub-Function: NvM_WriteAll	11

5.1.3.1.4.	Sub-Function: NvM_GetErrorStatus	12

5.1.3.1.5.	Sub-Function: NvM_SetRamBlockStatus	13

5.1.3.1.6.	Sub-Function: NvM_CancelWriteAll	14

5.1.3.2.	API Configuration Class 2	15

5.1.3.2.1.	Sub-Function: NvM_SetDataIndex	15

5.1.3.2.2.	Sub-Function: NvM_GetDataIndex	16

5.1.3.2.3.	Sub-Function: NvM_ReadBlock	17

5.1.3.2.4.	Sub-Function: NvM_WriteBlock	18

5.1.3.2.5.	Sub-Function: NvM_RestoreBlockDefaults	19

5.1.3.2.6.	Sub-Function: NvM_CancelJobs	20

5.1.3.3.	API Configuration Class 3	21

5.1.3.3.1.	Sub-Function: NvM_SetBlockProtection	21

5.1.3.3.2.	Sub-Function: NvM_EraseNvBlock	22

5.1.3.3.3.	Sub-Function: NvM_InvalidateNvBlock	23

5.1.4.	Type Definitions	24

5.1.4.1.	Std_ReturnType	24

5.1.4.2.	NvM_RequestResultType	24

5.1.4.3.	NvM_BlockIdType	25

5.2.	NvM_Proxy: Non Volatile Memory Proxy (Nexteer CDD)	26

5.2.1.	Design Rationale	26

5.2.2.	Sub-Functions	26

5.2.2.1.	Sub-Function: NvMProxy_Init	26

5.2.2.1.1.	Hardware Related Design	26

5.2.2.1.2.	Software Related Design	26

6.	Timing / Execution Constraints	27

6.1.	Rationale / Comments	27

6.2.	Rates and State Execution: NvM	27

6.3.	Rates and State Execution: NvMProxy	28

7.	Serial Communications Interfaces	28

8.	Additional Information	29

8.1.	NvM block definition Considerations	29

8.1.1.	Scenario 1	29

8.1.2.	Scenario 2	29

8.2.	Software Component Design Considerations	30

8.2.1.	API Port Selection	30

9.	Revision Record & Change Approval	31

High Level Description

This design document describes the functionality, API, and the configuration of the AUTOSAR basic software (BSW) module NVRAM Manager (NvM) and the NvM Proxy (NvMProxy). 

The NvM provides services to ensure the data storage and maintenance of NV (non-volatile) data. The NvM module is able to administrate the NV data for an EEPROM and/or a Flash EEPROM Emulation (FEE) device. 

The NvMProxy provides an interface for software components outside of the application of the NvM to communicate with the NvM component.

Derived Requirements

None

 Sub-Function Data Flow

None

Design Rationale

The NvM and NvMProxy components are integrated below the application layer in the basic software layer of the AUTOSAR model. 

NvMProxy was designed so that all software components can send their NvM requests to the proxy interface, which will communicate the request to the NvM and report the results back to the calling component. This simplifies the design of software components by only requiring one interface for defining NvM needs and providing the needed functionality to switch the OS context in the event the calling application is different than the application NvM is integrated. 

Components

The following sections describe the NvM and NvM proxy components.

NvM: Non Volatile Memory (AUTOSAR BSW)

BSW Configuration

NvMCommon

Periodic Functions

NvM_MainFunction

This function has to be called cyclically. It is the entry point for the NvM component. In this function processing of all asynchronous jobs are handled (read/write/erase/invalidate/CRC calculation). 

Function Definition

Service Sub-Functions

The value of the API configuration class determines which API server ports are available to the system. The image below shows the breakdown of the functionality for each API Configuration Class. 

In the following sub sections, the APIs are defined for application software components (SWCs) and BSW components. The application function definition shall be used for components that sit above the RTE layer in the AUTOSAR model. The RTE generator will absorb some of the dynamic arguments, such as BlockId, and create a macro with the proper definition for the software component. Complex device drivers and other BSWs that sit below the RTE layer shall use the CDD function definition. 

API Configuration Class 1

The following sections contain a description of the functions provided by the AUTOSAR NvM basic software component with API Configuration Class 1 configured. 

Sub-Function: NvM_Init

Hardware Related Design

None

Software Related Design

Before the NvM component can be used, it has to be initialized. Depending on the program the NvM is integrated, the BSWs from lower levels shall be initialized prior to the NvM. The table below is an example of this strategy for Fee and Ea use cases for initialize modules from the low level components up to the NvM.

The NvM AUTOSAR component compliant with ASIL-D standards, NvM_Init shall be called as a trusted function. This will allow the NvM_Init function access to all the permanent RAM shadows defined in software, regardless of their ASIL rating. This reduces the RAM and throughput during start up to move data from application to another. 

Application Function Definition

None

CDD Function Definition

Sub-Function: NvM_ReadAll

Hardware Related Design

None

Software Related Design

This function shall only be called after NvM_Init has been executed. The request loads all the RAM blocks that have the option NVM_SELECT_BLOCK_FOR_READALL selected. 

Note: Non-permanent blocks and data set blocks are skipped during execution of this function and must be loaded manually by calling NvM_ReadBlock(). 

During the execution of NvM_ReadAll(), the value in the configuration ID (block 1) is compared with the compiled ID version in the NvM settings. With the Dynamic Configuration Handling option set to True, any NvM blocks with the option Resistant to Changed Software enabled will be processed and loaded into RAM as if the configuration IDs matched. If the option Resistant to Changed Software is not enabled, the blocks will be treated is if they were invalid or blank. 

Application Function Definition

None

CDD Function Definition

Sub-Function: NvM_WriteAll

Hardware Related Design

None

Software Related Design

Request to write all blocks with RAM data that has been changed and have the option NVM_SELECT_BLOCK_FOR_WRITEALL selected. 

Note: Non-permanent blocks and data set blocks are skipped during execution of this function and must be written manually by calling NvM_WriteBlock().

Application Function Definition

None

CDD Function Definition

Sub-Function: NvM_GetErrorStatus

Hardware Related Design

None

Software Related Design

The request reads the block dependent status/error information and writes it to the given address. The status/error information was set by a former or current asynchronous request. This API can also b

Configuration Parameter | Value | Rationale
API Configuration Class | MVM_API_CONFIG_CLASS_3 | Class 3 shall be used to provide all API options to software components. This is to prevent rework of existing components if use cases change and require API functions that may not have been available during component development under a different API class.
Compiled Configuration Id | 1 | Version of the NV memory layout, always shall start at 1 and be revised if the memory layout changes
Crc Number of Bytes | 64 | Dummy value, not used.
Dataset Selection Bits | 1 | Shall be set to 1 if the only block types are “native” and “redundant.” If a dataset is required, then the number needs to be set satisfy the following equation: 
2^(Selection Bits) >= max(dataset)
For example, if the largest dataset for all configured blocks was 30, the selection bits are required to be set to 5. 
2^5 = 32 >= 30
Development Error Detection | FALSE | Only should be true for early development. Shall not be used in production level software
Drivers Mode Switch | True | Disables processing of background sector switching from startup and shutdown events.
Dynamic Configuration Handling | True | Allows for adapting new FEE layouts over existing layouts. See section 5.1.3.2.2 for details on the impact of this setting.
Job Prioritization | False | No requirement for prioritization of any blocks
Maximum Number of Write Retries | 3 | Default setting
Multi Block Callback |  | 
Multi block Job Status Information | False | 
Polling Mode | True | Enabled to provide the application the ability to poll the status of the asynchronous request.
Repeat Mirror Operations | 0 | Default setting
SetRamBlockStatus API | True | Applications shall use SetRamBlockStatus API to indicate their RAM shadows have updated.
Size Of Immediate Status Information | N/A | Not used
Size Of Standard Job Queue | 8 | Default setting
Version Information API | False | N/A
Prototype
void NvM_MainFunction ( void )
Parameter
N/A
Return Code
N/A
Function Particularities | Function Particularities
Request Type | Synchronous
Re-entrant | Yes
Expected Caller Context | Shall only be called from ECU state manager or equivalent function.
 | Fee | Ea
Low level driver | Fls | SPI/EEP
Device Abstraction | FEE | EA
Non-Volatile Manager | NvM | NvM
