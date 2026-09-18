---
title: "Vector Basic Software Support Library — TechnicalReference VStdLib"
description: "Converted Technical Reference (vendor) from TechnicalReference_VStdLib.pdf (PDF, 431 KB)."
---

:::note
Converted from `VectorBswSuprt/doc/01.04.00_03.08.00/TechnicalReference_VStdLib.pdf` (Technical Reference (vendor); original PDF, about 431 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to VectorBswSuprt](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
VStdLib 
Technical Reference 
 
Vector Standard Library 
Version 1.6.2 
 
 
 
 
 
 
 
 
 
 
 
Authors Patrick Markl, Timo Vanoni 
Status Released

--- Page 2 ---
Technical Reference VStdLib   
2013, Vector Informatik GmbH Version: 1.6.2 
based on template version 3.7 
2 / 21 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Patrick Markl 2008-02-06 1.0 Creation, merge from Application Note 
Patrick Markl 2008-10-31 1.3 Fixed document version 
Patrick Markl 2008-11-07 1.4 Added information about mixed VStdLib versions 
Patrick Markl 2009-07-02 1.5 Updated assertion codes 
Added chapter about QNX OS 
Patrick Markl 2009-10-16 1.6 Described inclusion of OSEK OS header file 
Timo Vanoni 2013-05-10 1.6.2 ESCAN00067020: The interrupt lock functions 
do not work correctly for the user mode at 
specific controller 
Table 1-1  History of the Document 
 
 
 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference VStdLib   
2013, Vector Informatik GmbH Version: 1.6.2 
based on template version 3.7 
3 / 21 
Contents 
1 Document Information ................................ ................................ ................................ . 2 
1.1 History ................................ ................................ ................................ ............... 2 
2 Introduction................................ ................................ ................................ ................... 5 
3 Functional Description ................................ ................................ ................................ . 6 
4 Integration ................................ ................................ ................................ ..................... 8 
4.1 CANbedded Particularities ................................ ................................ ................. 8 
4.2 MICROSAR Particularities ................................ ................................ ................. 8 
4.3 Mixing VStdLib Versions ................................ ................................ .................... 8 
5 Configuration ................................ ................................ ................................ ................ 9 
5.1 Usage with OSEK OS ................................ ................................ ...................... 11 
5.2 Usage with QNX OS ................................ ................................ ........................ 11 
6 API Description ................................ ................................ ................................ ........... 13 
6.1 Initialization ................................ ................................ ................................ ...... 13 
6.2 Interrupt Control ................................ ................................ ...............................  14 
6.3 Memory Functions ................................ ................................ ........................... 15 
6.4 Callback Functions ................................ ................................ ........................... 17 
7 Assertions ................................ ................................ ................................ ................... 18 
8 Limitations ................................ ................................ ................................ .................. 19 
8.1 Interrupt control does not work correctly in user mode ................................ ..... 19 
9 Glossary and Abbreviations ................................ ................................ ...................... 20 
9.1 Glossary ................................ ................................ ................................ .......... 20 
9.2 Abbreviations ................................ ................................ ................................ ... 20 
10 Contact ................................ ................................ ................................ ........................ 21

--- Page 4 ---
Technical Reference VStdLib   
2013, Vector Informatik GmbH Version: 1.6.2 
based on template version 3.7 
4 / 21 
Illustrations 
Figure 5-1 VStdLib configuration dialog in GENy ................................ ......................... 9 
Figure 5-2 VStdLib configuration dialog in CANGen ................................ .................... 9 
Figure 5-3 Locking configuration in case CAN events are handled in an interrupt 
thread ................................ ................................ ................................ ....... 11 
Figure 5-4 Configuration of the VStdLib in case of handling CAN events on interrupt 
level ................................ ................................ ................................ .......... 12 
 
Tables 
Table 1-1  History of the Document ................................ ................................ ............. 2

--- Page 5 ---
Technical Reference VStdLib   
2013, Vector Informatik GmbH Version: 1.6.2 
based on template version 3.7 
5 / 21 
2 Introduction 
The basic idea of the VStdLib is to provide standard functionality to different Vector 
components. This includes memory copy and i nterrupt locking functions. The VStdLib is 
also a means to provide special memory copy functions , which are not available by 
compiler libraries to the communication components.  
The VStdLib is designed to be used by Vector communication components only. So  the 
customer integrating the communication stack will probably not notice the VStdLib at all. 
The VStdLib is highly hardware specific. This means some functions are only available on 
certain platforms. This includes special copy functions for far, near or  huge memory. A 
hardware specific VStdLib does not necessarily implement all possible copy function  for 
the corresponding  hardware platform , but only the functions required by the Vector 
software components. 
The VStdLib also provides interrupt lock functions. This feature depends on the 
CANbedded CAN driver’s Reference Implementation (RI). The RI defines a certain feature 
set to be supported by the CAN driver.  CAN drivers which implement RI1.5 and higher do 
not provide an interrupt locking mechanism as previously implementations did 
(CanGlobalInterruptDisable/CanGlobalInterruptRestore). These driver require a VStdLi b to 
provide this functionality, although the API CanGlobalInterruptDisable and 
CanGlobalInterruptRestore remains for compatibility. Please refer to the CANbedded CAN 
driver technical reference for more information about your specific CAN driver.

--- Page 6 ---
Technical Reference VStdLib   
2013, Vector Informatik GmbH Version: 1.6.2 
based on template version 3.7 
6 / 21 
3 Functional Description 
The VStdLib provides basically two main functionalities  to Vector communication stack 
components. 
> Functions to copy memory 
> Functions to lock/unlock interrupts 
Interrupt locking functionality is required for CAN drivers with a reference implementation 
1.5 or higher or MICROSAR stacks. Functions to copy memory are always provided.  The 
following table describes the API of the VStdLib which is used internally. 
 
API Function Description 
VStdMemSet Initializes default RAM memory to a certain 
character. 
VStdMemNearSet Initializes near RAM memory to a certain character.  
VStdMemFarSet Initializes far RAM memory to a certain character. 
VStdMemClr Clears default RAM to zero. 
VStdMemNearClr Clears near RAM to zero. 
VStdMemFarClr Clears far RAM to zero. 
VStdMemCpyRamToRam Copies default RAM to default RAM. 
VStdMemCpyRomToRam Copies default ROM to default RAM. 
VStdMemCpyRamToNearRam Copies default RAM to near RAM. 
VStdMemCpyRomToNearRam Copies default ROM to near RAM. 
VStdMemCpyRamToFarRam Copies default RAM to far RAM. 
VStdMemCpyRomToFarRam Copies default ROM to far RAM. 
VStdMemCpy16RamToRam Copies default RAM to default RAM. The copying is 
performed 16 bit wise. 
VStdMemCpy16RamToFarRam Copies default RAM to far RAM. The copying is 
performed 16 bit wise. 
VStdMemCpy16FarRamToRam Copies far RAM to default RAM. The copying is 
performed 16 bit wise. 
VStdMemCpy32RamToRam Copies default RAM to default RAM. The copying is 
performed 32 bit wise. 
VStdMemCpy32RamToFarRam Copies default RAM to far RAM. The copying is 
performed 32 bit wise. 
VStdMemCpy32FarRamToRam Copies far RAM to default RAM. The copying is 
performed 32 bit wise.

[… 15 further page(s) not extracted …]
