---
title: "Flash EEPROM Emulation — AN-ISC-8-1161 FEE alignments to reduce data loss through ECC"
description: "Converted Portable Document (vendor or generated report) from AN-ISC-8-1161_FEE_alignments_to_reduce_data_loss_through_ECC.pdf (PDF, 1017 KB)."
---

:::note
Converted from `Fee/doc/AN-ISC-8-1161_FEE_alignments_to_reduce_data_loss_through_ECC.pdf` (Portable Document (vendor or generated report); original PDF, about 1017 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Fee](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
FEE alignments to reduce data loss through ECC 
Version 1.0 
2014-08-06 
Application Note AN-ISC-8-1161 
 
 
 
Author(s) Goß, Michael 
Restrictions Customer confidential - Vector decides 
Abstract Alignments and ECC handling of flash devices have to be considered with the MICROSAR FEE 
configuration 
 
Table of Contents 
 
 1  
Copyright © 2014 - Vector Informatik GmbH 
Contact Information:   www.vector.com   or +49-711-80 670-0 
1.0 Overview .......................................................................................................................................................... 1 
2.0 Hardware Alignment Problem .......................................................................................................................... 1 
3.0 FEE Alignment Configuration .......................................................................................................................... 4 
3.1 FEE Write Alignment ..................................................................................................................................... 4 
3.2 FEE Address Alignment ................................................................................................................................ 4 
3.3 Recommendation for FEE Alignment Configuration ..................................................................................... 5 
4.0 List of Affected Platforms ................................................................................................................................. 6 
5.0 Additional Resources ....................................................................................................................................... 6 
6.0 Contacts ........................................................................................................................................................... 6 
 
 
1.0 Overview 
This application note addresses a hardware dependent topic of microcontrollers which may lead to a corruption of 
data entities in the flash memory. This document describes alignment attributes and ECC (Error Correction Code) 
error handling of the flash memory hardware and how the MICROSAR Flash EEPROM Emulation (FEE) has to be 
configured in order to avoid problems. 
In section 2 the problem is illustrated on the basis of a particular microcontroller family, which is affected by this 
behavior. 
Section 3 describes the MICROSAR FEE alignment characteristics and points out configuration details, which have 
to be taken into account. 
In section 4 microcontroller families are listed which are known to show the described behavior. 
2.0 Hardware Alignment Problem 
The following hardware dependent problem is illustrated on basis of Freescale MPC560xB (Bolero) microcontroller 
family. Generally the characteristics of every microcontroller should be examined to the effect that the described 
problem is prevented. 
In some microcontrollers, for instance in Freescale’s MPC560xB family, the hardware specific write alignment 
differs from the read alignment. Particularly this can cause an issue if the read alignment is greater than the write 
alignment. In this case the treatment of ECC (Error Correction Code) errors by the microcontroller can result in 
corruption of data entities. 
By way of illustration and for further considerations the alignment properties of MPC560xB family are depicted in 
the following table: 
Write alignment 8 byte (64 Bit) 
Read alignment 16 byte (128 Bit) 
Table 1 – Write and read alignment of MPC560xB microcontrollers

--- Page 2 ---
FEE alignments to reduce data loss through ECC 
 
   
 
 2 
Application Note AN-ISC-8-1161 
 
 
In figure 1 the addressing schemes of this hardware is described in accordance with read-  or write-accesses to the 
flash memory. 
 
Figure 1 – Memory addressing 
 
For further considerations: The smallest writable unit in this flash is called a page with a size of 8 byte. 
The handling of programming (write) accesses differs from read accesses due to the alignment sizes. On the one 
hand, programming the flash memory is possible with a page size of 8 byte (64 Bit) and therefore the write 
addresses have to be aligned to 8 byte boundaries. On the other hand reading from the flash memory is hardware 
specifically aligned to 16 byte boundaries. In consequence, the data being read from the flash memory contains 
two pages of written data. It is required by AUTOSAR to provide memory abstraction and non-aligned memory 
access. Nevertheless when performing read jobs, this flash memory controller always accesses 16 byte-sized 
address spaces due to internal constraints. Therefore even if only one byte is requested by the application, the 
flash memory controller accesses 16 bytes of data. As a consequence misaligned read accesses to hardware may 
be accomplished by several 16 byte reads. The requested data then is extracted from the received packages and 
assembled correctly before passing it to the upper layer. 
For each written page (8 byte) one ECC is calculated to add some redundancy to a data set, which can be used to 
check its consistency, and to recover data determined to be corrupted. The ECC implemented within the flash 
memory module will correct single bit failures and detect double bit failures. Correction of single bit errors takes 
place within the flash memory controller whereas the flash cell content remains unchanged. Depending on the 
used platform, e.g. MPC560xB, ECC error handling varies. For further considerations the ECC error handling is 
evaluated with regard to the microcontroller family MPC560xB.  
If an uncorrectable ECC error occurs, an error response is signaled and the requested access is terminated with 
an error. This implies that an ECC error in one page results in an erroneous read operation which actually 
accesses two pages of written data. Hence reading from an address aligned to the 16 byte boundary fails if just 
one page therein contains an uncorrectable ECC error. As a result the second potentially error -free page within this 
read boundary will be treated as corrupted thereby as well. 
The reason for an uncorrectable ECC error in a flash page is for example an aborted programming access due to a 
reset. Figure 2 illustrates how one ECC error affects read operations.

--- Page 3 ---
FEE alignments to reduce data loss through ECC 
 
   
 
 3 
Application Note AN-ISC-8-1161 
 
 
Figure 2 – ECC error affects read operation 
 
Figure 2 depicts that one ECC error within a 16 byte address boundary leads to an unsuccessful reading. If one 
ECC error is received during read access, the flash memory controller does not update the read buffer. Thus 
reading from this address fails even if one of the two pages is consistent.  
This means the occurrence of one uncorrectable ECC error in a page treats the neighboring page within the 16 
byte address boundary also as corrupted. This situation is particularly problematic if the start addresses of two 
neighboring data blocks are not aligned to 16 byte address boundaries, as shown in figure 3. 
 
Figure 3 – Two data blocks not aligned to 16 Byte (128-bit) address boundaries 
 
As depicted in figure 3, an ECC error in one data block may result in the corruption of another data block. Either 
the first page of data block 2 (left diagram) or the last page of data block 1 (right diagram) cannot be read in case 
of an ECC error in the other block. Usually the first and the last pages of a data block contain information (e.g. 
block id, block length) which is used for management purposes. If these pages cannot be read the entire data 
block may be corrupted.  
An application using the MICROSAR FEE with such insufficient alignment settings may run in data consistency 
issues as described in the following example: 
A (simplified) configuration contains one block with multiple instances. After writing this block several times, the 
programming access is aborted due to a reset while writing the first page of the block. In consequence the block 
with latest data was not written successfully and an uncorrectable ECC error occurs. Generally, when reading data 
of a specific block from flash memory, the MICROSAR FEE returns the content of the last written data. In case the

--- Page 4 ---
FEE alignments to reduce data loss through ECC 
 
   
 
 4 
Application Note AN-ISC-8-1161 
 
last written instance is corrupt, e.g. due to a write abort (reset), the MICROSAR FEE returns the second latest 
data. In this scenario the uncorrectable ECC error in the latest instance corrupts the second latest instance and 
thus the MICROSAR FEE returns the data of the third latest instance to the application. Thus it cannot be assured 
that the returned data is up-to-date. 
A worst case scenario would be a completely corrupted flash image caused by an uncorrectable ECC error at  
particular positions. As a result, neither read nor write accesses to the flash memory would b
