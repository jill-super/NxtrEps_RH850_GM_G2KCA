---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — AN-ISC-2-1052 CANbedded and Operating Systems"
description: "Converted Portable Document (vendor or generated report) from AN-ISC-2-1052_CANbedded_and_Operating_Systems.pdf (PDF, 177 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/AN-ISC-2-1052_CANbedded_and_Operating_Systems.pdf` (Portable Document (vendor or generated report); original PDF, about 177 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
CANbedded and Operating Systems 
Version 1.0 
2007-01-18 
 
Application Note  AN-ISC-2-1052 
 
 
 
Author(s) Hartmut Hö rner, Patrick Markl 
Restrictions Restricted Membership 
Abstract The Vector CANbedded software component s have some requirements for the run-time 
environment. These requirements are described in this application note.  
 
 
Table of Contents 
 
 1  
Copyright © 2007 - Vector Informatik GmbH 
Contact Information:   www.vector-informatik.com   or ++49-711-80 670-0 
1.0 Overview ..........................................................................................................................................................1 
2.0 General Requirements.....................................................................................................................................1 
3.0 Interrupt Handling ............................................................................................................................................2 
3.1 Interrupt Service Routines (ISRs) .................................................................................................................2 
3.2 Access to interrupt control registers..............................................................................................................2 
4.0 Data consistency..............................................................................................................................................3 
5.0 Memory protection and virtual memory management .....................................................................................3 
6.0 Privilege modes ...............................................................................................................................................4 
7.0 Operating systems with stringent driver models..............................................................................................4 
8.0 Startup Time ....................................................................................................................................................5 
9.0 Contacts...........................................................................................................................................................5 
 
  
1.0 Overview 
The Vector CANbedded components have some requirements for the run-time environment. Some of these might 
impact the usage of the operating system elements as well as the real-time design. 
Two run-time environments are explicitly supported by CANbedded: 
• A system without operating system 
• An OSEK Operating System (version 2. 1r1 onwards) such as Vector osCAN 
 
In the following chapters the requirements are listed and for some cases where no explicitly support exists 
workarounds are described. 
2.0 General Requirements 
Higher layer CANbedded components require an initialization function and one or more cyclic functions. 
CANbedded hardware drivers have an initialization function, ISRs in interrupt driven mode and cyclic functions in 
polling mode. The initialization function must be called before the cyclic function is called for the first time and 
before the first ISR occurs. 
The CANbedded stack requires a shared address space with the application since some functionalities such as 
signal and flag access are implemented by macros. 
There are no requirements for dynamic memory management. All not constant global variables are explicitly 
initialized in the initialization functions. There are no requirements for memory initialization in the start-up code 
unless constant data is located in RAM.

--- Page 2 ---
CANbedded and Operating Systems  
 
   
 
 2 
Application Note  AN-ISC-2-1052 
 
Since the CANbedded components have to interface directly with the communication hardware adequate access 
privileges are required. 
3.0 Interrupt Handling 
3.1 Interrupt Service Routines (ISRs) 
If the CAN Driver is used in an interrupt driven mode one or more ISRs must be installed. 
Two categories of ISRs are supported: 
• ISR implemented with the related compiler pragma or qualifier. This is used in a system without operating 
system and for OSEK-OS ISRs of category 1. 
• OSEK-OS ISR category 2. 
 
If an operating system other than OSEK is used the following workaround is possible:  
If OSEK-OS and OSEK-OS category 2 ISR support are selected in the generation tool the ISR has the following C 
syntax: 
 
ISR(CanInterrupt) 
{ 
  … 
} 
 
Supply a header file osek.h with the following macro, to make the ISR available in other modules as a void-void 
function. 
 
#define ISR(x) void x(void) 
 
Example for an operating system which provides a service OSRegisterISR to register an ISR: 
 
OSRegisterISR(CanInterrupt, 10);     /* second parameter is interrupt vector number */ 
 
If the prototype of the ISR required by the OS is not of the kind void x(void) an intermediate function must be used 
to circumvent type conflicts. 
3.2 Access to interrupt control registers 
To achieve its own data consistency and to export such services to the application the CANbedded components 
require access to the interrupt control registers of the communication controller and to interrupt control registers of 
the interrupt controller or the CPU which allow to disable interrupts globally or up to a certain level. 
If it is not desirable or possible that the CANbedded components access the global interrupt directly this 
functionality can be replaced by other mechanisms (“interrupt control by application”, supported in CAN driver RI 
version 1.4 onwards).  
If a resource locking mechanism of the operating system is used it must support nested critical sections.

--- Page 3 ---
CANbedded and Operating Systems  
 
   
 
 3 
Application Note  AN-ISC-2-1052 
 
4.0 Data consistency 
For efficiency reasons some services of the CANbedded components are implemented as macros with  
unprotected critical sections. If these macros are used in multiple full-preemptive tasks or in multiple ISRs data 
consistency problems can be caused. One of the following solutions is possible: 
• Use these services only in non-preemptable tasks 
• Use these services only in one cooperative task group (OSEK: internal resource concept) 
• Supply critical section in the application code 
 
Some CANbedded components have specific requirements concerning processing priorities and reentrancy. These 
requirements are described in the technical reference of the individual component. 
 
5.0 Memory protection and virtual memory management 
This chapter is only applicable if the processor and the run-time environment support such mechanisms. 
Since some CANbedded services are implemented as macros which access to global variables the application part 
which uses the CANbedded services and the complete CANbedded stack must reside in one address space.  
In addition all CANbedded tasks and ISRs must be able to access the peripheral address space of the 
communication hardware. 
The following figure shows a possible configuration with three different applications with an own address space. 
Two applications perform application tasks (drawn in green), one application is responsible for the communication 
(drawn in red). 
Application 1 Application 2
CANbedded stack
Communication hardware
Communication application
 
Figure 1 Different applications with own address space 
 
To move data between the applications operating system services are required which have the capability to tunnel 
the address barrier (drawn with blue arrows)..

--- Page 4 ---
CANbedded and Operating Systems  
 
   
 
 4 
Application Note  AN-ISC-2-1052 
 
6.0 Privilege modes  
This chapter is only applicable if the processor and the run-time environment support such mechanisms. 
In some architectures different privilege modes such as user and supervisor mode are defined. If a task or ISR is 
running in user mode the access to peripheral hardware and global resources such as interrupt control registers 
may be restricted.  
It must be possible to assign all tasks and ISRs which provide or use CANbedded services a sufficient privilege 
level to allow for: 
• Access to communication hardware 
• Access to communication related interrupt control 
• Access to global interrupt control registers including the capability to execute inst ructions related to global 
interrupt control registers unless interrupt control by application is used (s. chapter 3.2). 
 
If such a privilege level is not possible for tasks but only for ISRs a cyclic timer ISR can be used to perform all 
required CANbedded cyclic processing. Note that such an ISR must have a lower interrupt level than the ISRs of 
the CANbedded drivers. 
7.0 Operating systems with stringent driver models 
This chapter is only applicable if the run-time environment supports such mechanisms. 
In some operating systems hardware access is only allowed for specific hardware drivers which have to follow a 
predefined implementation model. When a hardware d
