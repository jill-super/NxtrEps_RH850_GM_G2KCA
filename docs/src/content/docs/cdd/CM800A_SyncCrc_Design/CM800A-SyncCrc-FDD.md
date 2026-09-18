---
title: "Synchronous Cyclic Redundancy Check — CM800A SyncCrc FDD"
description: "Converted Design / Integration Document from CM800A_SyncCrc_FDD.docx (DOCX, 289 KB)."
---

:::note
Converted from `CM800A_SyncCrc_Design/Design/CM800A_SyncCrc_FDD.docx` (Design / Integration Document; original DOCX, about 289 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM800A_SyncCrc_Design](./)

*Conversion method: automatic text extraction from the Word document.*

Synchronous Cyclic Redundancy Check

FDD #CM-800A

1.	High Level Description	3

2.	Derived Requirements	3

3.	Sub-Function Data Flow	3

4.	Design Rationale	3

5.	Sub-Functions	4

5.1.	Management of CRC Hardware Units	4

5.1.1.	Initialization of Management RAM (SyncCrcInit0)	5

5.1.2.	RTE Initialization (SyncCrcInit1)	5

5.1.3.	Sub-Function: RelsCrcHwUnit	5

5.1.4.	Sub-Function: GetAvlCrcHwUnit	6

5.1.5.	Sub-Function: ResvCrcHwUnit	7

5.2.	SyncCrc API Functions	9

5.2.1.	Sub-Function: 32-Bit Ethernet CRC	10

5.2.1.1.	Hardware Related Design	10

5.2.1.2.	Software Related Design	10

5.2.1.2.1.	Calc32BitCrc_u08	10

5.2.1.2.2.	Calc32BitCrc_u16	11

5.2.1.2.3.	Calc32BitCrc_u32	11

5.2.2.	Sub-Function: 16-Bit CRC	12

5.2.2.1.	Hardware Related Design	12

5.2.2.2.	Software Related Design	12

5.2.2.2.1.	Calc16BitCrc_u08	12

5.2.2.2.2.	Calc16BitCrc_u16	12

5.2.3.	Sub-Function: 8-Bit SAE-J1850 CRC	13

5.2.3.1.	Hardware Related Design	13

5.2.3.2.	Software Related Design	13

5.2.3.2.1.	Calc8BitCrc	13

5.2.4.	Sub-Function: 8-Bit 0x2F CRC	14

5.2.4.1.	Hardware Related Design	14

5.2.4.2.	Software Related Design	14

5.2.4.2.1.	Calc8BitCrc0X2F	14

5.3.	Sub-Function: AUTOSAR API Wrapper	15

5.3.1.	Sub-Function: Crc_CalculateCRC32	15

5.3.2.	Sub-Function: Crc_CalculateCRC16	15

5.3.3.	Sub-Function: Crc_CalculateCRC8	15

5.3.4.	Sub-Function: Crc_CalculateCRC8H2F	15

6.	Timing / Execution Constraints	16

6.1.	Rationale / Comments	16

6.2.	Rates and State Execution	16

7.	Serial Communications Interfaces	16

8.	Additional Information	16

9.	Revision Record & Change Approval	17

High Level Description

This document describes the design of the application programming interface (API) to allow application software components (SWCs) to interact with the cyclic redundancy check (CRC) hardware peripheral included in the microcontroller in EA4 hardware.  

Derived Requirements

N/A

 Sub-Function Data Flow

The follow block diagram depicts how the data flow inside the microcontroller CRC peripheral.

 Design Rationale

The design of the API was intended to meet the AUTOSAR CRC API definition as closely as possible. This allows the software configuration to utilize the hardware instead of using software libraries to save on throughput for software calculations. While the direct API does not match the AUTOSAR API definitions, wrapper functions are included to interface with components using the AUTOSAR API with the SyncCRC API. 

Sub-Functions

Management of CRC Hardware Units

#REQ: The following requirement(s) are met by the design feature below: Requirement ID: CM800A_48, CM800A_49, CM800A_50, CM800A_67, CM800A_68, CM800A_69, CM800A_70, CM800A_81

The software implementation shall provide a mechanism to utilize one of the CRC hardware units for a synchronous CRC calculation from a software component calling one of the API functions. Upon completion of the job, the software shall release the hardware unit to be available by another software component. This management shall be implemented by a RAM table that has holds the task ID and the of the CRC hardware index. No periodic function is required to manage the RAM since the calculations are synchronous, released at the end of the API call, or permanently reserved. Furthermore, each API function will update the RAM after the job has been completed.

The implementation shall also provide a way to reserve one or more units to dedicate to a particular function if a program requires. The reservation shall be done by the pre-compile configuration or by a function call. The pre-compile configuration shall provide a permanent reservation of the CRC hardware unit. The reservation shall start from the highest hardware index. Any hardware CRC unit that is permanently reserved shall not be used by the SyncCRC API or a temporary reservation of a hardware CRC unit and should be considered as not enabled or available.  

The function call shall provide a temporary allocation of one of the available, non-permanently reserved, CRC hardware units. This CRC hardware unit shall be reserved until the calling function releases it. The details of this function are described later in this document.

The management shall also provide protection from preemption of higher priority tasks by utilizing the OS task ID of the calling function as an authority to use that CRC hardware unit. 

An example of the RAM table is shown below. Hardware index 0 is temporarily reserved. Hardware index 1 is assigned to task ID 2 until the calculation has completed. Index 2 is available for the next caller. Hardware index 3 is permanently reserved and not available to software applications invoking the API, but is be available to a dedicated source if required by the program. 

Initialization of Management RAM (SyncCrcInit0)

#REQ: The following requirement(s) are met by the design feature below: Requirement ID: CM800A_71, CM800A_50

The RAM shall be initialized according to the following pseudo code. This allows the pre-compile configuration to block access to the CRC hardware units that are not available to the application software components. In order for this to be effective, the initialization is required to be scheduled before any software components invoke the API. This function shall be called from outside of the RTE during “cold init.”

For each CRC Hardware Unit: 

CrcHwSts[HwUnit].TaskId = Invalid Task ID

	If HwIdx < Number of Active Hardware Units:

		CrcHwSts[HwUnit].CrcHwSts = Available

	Else:

		CrcHwSts[HwUnit].CrcHwSts = Crc Not Enabled

	End If

End For Loop

RTE Initialization (SyncCrcInit1)

This function stub is required to properly place the SyncCrc component within the correct application within a program. This function is called by the RTE during initialization.

Sub-Function: RelsCrcHwUnit

#REQ: The following requirement(s) are met by the design feature below: Requirement ID: CM800A_48

This sub-function shall be used by the API to release a CRC hardware unit. This shall be called after the CRC calculation is complete for any of the API functions calls. The operation of the function shall meet the following pseudo code. 

Function Inputs: 

CrcHwIdx := This value represents which hardware index the action should go against. 

Function Outputs: 

Void

Function: 

CrcHwSts[CrcHwIdx].TaskId = Invalid Task ID

CrcHwSts[CrcHwIdx].CrcHwSts = Available

Sub-Function: GetAvlCrcHwUnit

#REQ: The following requirement(s) are met by the design feature below: Requirement ID: CM800A_48, CM800A_67, CM800A_81

This sub-function shall be used by the API to allocate a CRC hardware unit for the caller. This shall be called at the start of any of the CRC API functions calls. The operation of the function shall meet the following pseudo code. The ReserveTaskId is a set of four (4) known values that will be used for the task ID of a hardware unit that is temporarily reserved. 

Function Inputs: 

ResvCrcCall := Input to decide if the call is for a Crc unit reservation or a standard syn

Enumeration | CrcConfig (Enum Value) | DCRAnISZ | DCRAnPOL | Meaning
CRCHWRESVCFG_32BITCRC32BITWIDTH | 0 | 0 | 0 | 32-Bit CRC / 32-Bit Access Width
CRCHWRESVCFG_32BITCRC16BITWIDTH | 1 | 0 | 1 | 32-Bit CRC / 16-Bit Access Width
CRCHWRESVCFG_32BITCRC8BITWIDTH | 2 | 0 | 2 | 32-Bit CRC / 8-Bit Access Width
CRCHWRESVCFG_16BITCRC16BITWIDTH | 3 | 1 | 1 | 16-Bit CRC / 16-Bit Access Width
CRCHWRESVCFG_16BITCRC8BITWIDTH | 4 | 1 | 2 | 16-Bit CRC / 8-Bit Access Width
CRCHWRESVCFG_8BITCRC | 5 | 2 | 2 | 8-Bit CRC / 8-Bit Access Width (SAE-J 1850)
CRCHWRESVCFG_8BITCRCH2F | 6 | 3 | 2 | 8-Bit CRC / 8-Bit Access Width (Polynomial 0x2F)
CRC Result Width | 32 Bits
Polynomial | 0x04C11DB7
or
X32 + X26 + X23 + X22 + X16 + X12 + X11 + X10 + X8 + X7 + X5 + X4 + X2 + X1 + 1
or
Initial Value | 0xFFFFFFFF
Input Data Width | 8-Bit / 16-Bit / 32-Bit
Input Data Reflected | Yes
Result Data Reflected | Yes
XOR Value | 0xFFFFFFFF
Check | 0xCBF43926
Magic Check | 0xDEBB20E3
CRC Result Width | 16 Bits
Polynomial | 0x1021
or
X16 + X12 + X5 + 1
or
Initial Value | 0xFFFF
Input Data Width | 8-Bit / 16-Bit
Input Data Reflected | No
Result Data Reflected | No
XOR Value | 0x0000
Check | 0x29B1
Magic Check | 0x0000
CRC Result Width | 8 Bits
Polynomial | 0x1D
or
X8 + X4 + X3 + X2 + 1
or
Initial Value | 0xFF
Input Data Width | 8-Bits
Input Data Reflected | No
Result Data Reflected | No
XOR Value | 0xFF
Check | 0x4B
Magic Check | 0xC4
