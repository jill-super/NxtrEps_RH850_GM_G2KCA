---
title: "Guard Configuration and Diagnostic — CM107A GuardCfgAndDiagc"
description: "Converted Design / Integration Document from CM107A_GuardCfgAndDiagc.docx (DOCX, 2019 KB)."
---

:::note
Converted from `CM107A_GuardCfgAndDiagc_Design/Design/CM107A_GuardCfgAndDiagc.docx` (Design / Integration Document; original DOCX, about 2019 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM107A_GuardCfgAndDiagc_Design](./)

*Conversion method: automatic text extraction from the Word document.*

Guard Configuration And Diagnostics RH850

( GuardCfgAndDiagc )

FDD CM107A

1.	High Level Description	3

1.1. Overview	3

1.2. Slave Guards	3

1.2.1. IPG – Internal Peripheral Guard	4

1.2.2. PEG – PE Guard Function	4

2.	Sub-Functions in this Document	5

3.	Sub-functions	5

3.1	Sub-function: (GuardCfgAndDiagcInit1)	5

3.1.2.	Guard Configuration Section: PEG Slave Guard Configuration	6

3.1.3.	Guard Configuration Section: IPG Slave Guard Configuration	13

3.1.4.	Guard Configuration Section: PBG Slave Guard Configuration	19

4.1	Sub-Function (GuardCfgAndDiagcInit2)	28

4.2	Sub-Function: (GuardCfgAndDiagcInit3)	28

3.1.5.	NTCs	28

3.1.6.	SAN Linkage	28

3.1.7.	Description	29

3.1.8.	Rationale	29

3.1.9.	Implementation	30

3.1.10.	Reference	39

3.1.11.	Verification Method	50

4.	Revision Record & Change Approval	50

High Level Description

This document describes the microcontroller configuration for the micro slave guard function.  This function will selectively enable access to microcontroller resources.  On reset most of these resources are unprotected so the net behavior of the slave guard function is to constrain access.

Ref. Renesas’ Hardware User’s Manual  Ver 1.10  Dtd Feb 2016

1.1. Overview

The RH850 P1M MCU provides protection features to prevent erroneous access to memory and the control registers of the peripheral circuits using the slave guard function. 

1.2. Slave Guards

There are three sections to the guard function:

PEG – Processor Element Guard

IPG – Internal Peripheral Guard

PBG – Peripheral Bus Guard

Fig 4.1-1 from SAN 1.20 edited to correct the Flexray PROTSPID to match the value shown in the HWUM 1.1

1.2.1. IPG – Internal Peripheral Guard

The IPG section protects the CPU peripherals against illegal accesses by SW components running on the CPU itself. 

The IPG provides the following features: 

Detects violation of peripheral device protection.

Stores unauthorized access information

Blocks unauthorized access.

Notifies violation through an exception.

Invalidates subsequent access (post violation).

1.2.2. PEG – PE Guard Function

The PE guard system section prevents unauthorized access to the resources in the PE from an external master. This section protects access to the local RAM in the PE. 

The PEG provides the following features: 

Protects local RAM against illegal access from FlexRay and the DMA.

Detects PE access violation.

Blocks unauthorized access. 

Provides notification of an unauthorized access through the ECM.

Allows protection of up to 4 areas with 4K granularity.

1.2.3. PBG – Peripheral Bus Guards

The PBG protects the control registers in the peripheral circuits and memories from illegal access by the PE, Flexray and the DMA. The PBG module is divided into multiple PBG groups, each of which is provided a maximum of 16 protection channels. 

A single PBG channel can designate the access against which a single peripheral circuit should be protected.  Each PBG group can hold the information of the access that has been rejected.

The PBG provides the following features:

For protection against read access, an undefined value is read. 

For protection against write access, the write access is ignored. 

Provides notification of an unauthorized access through the ECM.

Stores unauthorized access information.

Sub-Functions in this Document

Below is a linked list of all sub-functions owned by this document.

Sub-functions

  Sub-function: (GuardCfgAndDiagcInit1)

      Return to subfunction list: return

NTCs

N/A

SAN Linkage

See the SAN Linkage paragraph of each of the sections which make up this sub-function.

Description

This sub-function configures the RH850/P1M.  This has been described in three sections which correspond to the portions of the guard hardware facilities which the microcontroller provides.    

Rationale

This sub-function has been defined in terms of the sections which correspond to the hardware resources.  This seems to have helped to organize the information but what was thought to be an additional benefit, supporting distinct initialization times for the different guard hardware, has not been used and has not been maintained.

Implementation

See the Implementation paragraph of each of the sections which make up this sub-function.

Initialization (GuardCfgAndDiagcInit1)

   PegInin();

   IpgInin();

   PbgInin();

Reference

See the Reference paragraph of each of the sections which make up this sub-function.

Verification Method

See the Verification Method paragraph of each of the sections which make up this sub-function.

Guard Configuration Section: PEG Slave Guard Configuration

Return to sub-function list link: return

Provides notification of an unauthorized access to the ECM.

NTCs

N/A

SAN Linkage

SAN-169: After reset, the access to the local RAM by bus masters other than the PE (CPU) itself is disabled. Thus, protection- setting registers shall be configured to authorize desired accesses by the DMA and FlexRay. These registers are not protected by PEG and can be thus protected by means of the MPU or the IPG.

Description

This sub-function configures the RH850/P1M for the PEG.  The PEG provides and limits access of masters other than the PE (the Flexray and DMA channels) to LRAM.

Rationale

Using the 4Kbyte resolution of the PEGG memory protection capability, the external masters (Flexray and DMA channels) have write access to the same one 4K block of LRAM and may read all 128Kbytes.  PEG0 registers define and control the writable 4Kbyte memory block in the highest 4K addresses of LRAM: 0xFEBFF000 through 0xFEBFFFFF.  PEGG1 registers define and control the readable 128Kbyte memory block which is all of LRAM: 0xFEBE0000 through 0xFEBFFFFF.   Two PEGG register sets remain unused.

DMA channels which move data from peripheral to LRAM, from LRAM to peripheral, or from LRAM to LRAM will have different SPIDs.  Their access rights will be determined by the SPIDs.

Implementation

PEG Protection Targets – Following access types are allowed or restricted for bus masters of each SPID:

SPID 0 – Read access allowed, Write access allowed.

SPID 1 – Read access restricted, Write access restricted.  

SPID 2 – Read access allowed, Write access restricted. 

SPID 3 – Read access allowed, Write access allowed.

Per the IPG setup in section 4.1, the PEG registers cannot be changed in user mode.

DMA channels will be assigned SPIDs corresponding to their respective LRAM and peripheral access requirements (SPID 2 or 3). 

Flexray uses SPID 3.  Currently, the intent is to make no use of the Flexray’s memory access capability but the SPID 3 ability to write to only the special 4K block and to read the entire LRAM matches well with possible future designs. 

The CPU is, thus far, only using the Reset initialized SPID value of 1.

The “CAUTION” note following Table 3.63 of the HWUM states “PEGGnBA.GnEN is cleared by writing to the PEGGnMK register.”  Therefore, the PEGGnMK must be written before PEGGnB

Sub-Function Name | Link
GuardCfgAndDiagcInit1 | 4.1
GuardCfgAndDiagcInit2 | 4.2
GuardCfgAndDiagcInit3 | 4.3
Register | Value | Comments | Access | Access
Register | Value | Comments | SV | UM
PEGSP | 0x0001 | Enable detection of accesses by any external master with an enabled SPID. | RW | RW*
PEGG0BA | 0xFEBF F095
PEGG0BA.G0BASE = 0xFEBFF
PEGG0BA.G0SP3 = 1
PEGG0BA.G0SP2 = 0
PEGG0BA.G0SP1 = 0
PEGG0BA.G0SP0 = 1
PEGG0BA.G0WR = 1
PEGG0BA.G0RD = 0
PEGG0BA.G0EN = 1 | Initialized to Local RAM start address in high order 20 bits.  
Write access allowed for SPID 3 and SPID 0. Write Access not allowed for SPID 2 and 1. | RW | RW*
PEGG0MK | 0x0000 0000
PEGG0MK.G0MASK = 0x00000 | This memory region consists of one 4Kbyte block so a zero mask makes all 20 bits of the G0BASE field of PEGG0BA significant. | RW | RW*
PEGG1BA | 0xFEBE 00D3
PEGG1BA.G1BASE = 0xFEBE0
PEGG1BA.G1SP3 = 1
PEGG1BA.G1SP2 = 1
PEGG1BA.G1SP1 = 0
PEGG1BA.G1SP0 = 1
PEGG1BA.G1WR = 0
PEGG1BA.G1RD = 1
PEGG1BA.G1EN = 1 | Initialized to 128Kb Local RAM’s start address.  
Read access allowed for SPID 2, SPID 3 and SPID 0. Read Access not allowed for SPID 1. | RW | RW*
PEGG1MK | 0x0001 F000
PEGG1MK.G1MASK = 0x0001F | With five mask bits set to one, only fifteen of the 20 bits of the G1BASE field of PEGG1BA are compared.  The entire local RAM is made read accessible here since (32- 15 =) 17 bits addresses 128 Kbyte. | RW | RW*
PEGG2BA | 0 | Set to or allow to remain at the value of zero established by reset. | RW | RW*
PEGG2MK | 0 | Set to or allow to remain at the value of zero established by reset. | RW | RW*
PEGG3BA | 0 | Set to or allow to remain at the value of zero established by reset. | RW | RW*
PEGG3MK | 0 | Set to or allow to remain at the value of zero established by reset. | RW | RW*
Register | Value | Comments | Access | Access
Register | Value | Comments | SV | UM
IPGENUM | 0x03
IPGENUM.IRE = 1
IPGENUM.E = 1 | Enable storing of access violation information in IPGECRUM and IPGADRUM  and enable the peripheral device protection. | RW | *
IPGPMTUM0 | 0x33
IPGPMTUM0.X1 = 0
IPGPMTUM0.W1 = 1
IPGPMTUM0.R1 = 1
IPGPMTUM0.X0 = 0
IPGPMTUM0.W0 = 1
IPGPMTUM0.R0 = 1 | Allow user mode Read and Write access to P-bus groups 0 to 3 and 5 and to the H Bus and restrict user mode execute access to P-bus groups 0 to 3 and 5 and to the H-bus. | RW | *
IPGPMTUM2 | 0x11
IPGPMTUM2.W1 = 0
IPGPMTUM2.R1 = 1
IPGPMTUM2.W0 = 0
IPGPMTUM2.R0 = 1 | Allow user mode read access to COMPTEST and INTC1 and restrict user mode write access to COMPTEST and INTC1 | RW | *
IPGPMTUM3 | 0x10
IPGPMTUM3.W1 = 0
IPGPMTUM3.R1 = 1 | Allow user mode read access to SysErrGen and restrict user mode write access to SysErrGen | RW | *
IPGPMTUM4 | 0x01
IPGPMTUM4.W0 = 0
IPGPMTUM4.R0 = 1 | Allow user mode read access to own IPG and PEG in User Mode and restrict user mode write access to own IPG and PEG in User Mode. | RW | *
DMA Channel | SRC | DST | PBG RESOURCE | HW Manual 31.4.2 Group | HW Manual 31.4.2 Channel
0 | SPI Register (CSIH1) | Local RAM (Motor Control) | CSIH1 group B | PBG2A | 11
1 | ADC Register (ADCD0) | Local RAM (Motor Control) | ADCD0 | PBG3A | 10
2 | SPI Register (CSIH3) | Local RAM (Motor Control) | CSIH3 group B | PBG2A | 15
3 | Local RAM (Motor Control) | TSG3 (TSG31) | TSG31 | PBG1A | 8
4 | Local RAM (Motor Control) | TSG3 (TSG31) | TSG31 | PBG1A | 8
5 | none | none | none | unused | unused
6 | none | none | none | unused | unused
7 | none | none | none | unused | unused
8 | none | none | none | unused | unused
9 | Local RAM (Motor Control) | Local RAM | none | N/A | N/A
10 | Local RAM (Motor Control) | SPI Register (CSIH3) | CSIH3 group B | PBG2A | 15
12 | Local RAM (Motor Control) | SPI Register (CSIH1) | CSIH1 group B | PBG2A | 11
14 | ADC Register (ADCD1) | Local RAM (Motor Control) | ADCD1 | PBG3A | 11
15 | Local RAM (Motor Control) | Local RAM (Motor Control) | none | N/A | N/A
