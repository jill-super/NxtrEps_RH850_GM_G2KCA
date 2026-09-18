---
title: "Vector Basic Software Support Library — AN-ISC-2-1081 Interrupt Control VStdLib"
description: "Converted Portable Document (vendor or generated report) from AN-ISC-2-1081_Interrupt_Control_VStdLib.pdf (PDF, 188 KB)."
---

:::note
Converted from `VectorBswSuprt/doc/01.04.00_03.08.00/AN-ISC-2-1081_Interrupt_Control_VStdLib.pdf` (Portable Document (vendor or generated report); original PDF, about 188 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to VectorBswSuprt](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Application Interrupt Control with VStdLib 
Version 1.0 
2008-08-06 
Application Note  AN-ISC-2-1081 
 
 
 
Author(s) Patrick Markl 
Restrictions Restricted Membership 
Abstract This application note explains how the application can control interrupt handling via the 
VStdLib and which constraints apply. 
 
 
Table of Contents 
 
 1  
Copyright © 2008 - Vector Informatik GmbH 
Contact Information:   www.vector-informatik.com   or ++49-711-80 670-0 
1.0 Overview ..........................................................................................................................................................1 
1.1 Introduction....................................................................................................................................................1 
2.0 Interrupt Control by Application .......................................................................................................................3 
2.1 Constraints ....................................................................................................................................................3 
2.1.1 Constraint 1: Nested Calls ..........................................................................................................................3 
2.1.2 Constraint 2: Recursive Calls when Disabling CAN Interrupts...................................................................3 
2.1.3 Constraint 3: No Locking when Disabling CAN Interrupts..........................................................................3 
3.0 Solution ............................................................................................................................................................6 
3.1.1 Nested Calls................................................................................................................................................6 
3.1.2 No Locking of Interrupts..............................................................................................................................7 
4.0 Referenced Documents .................................................................................................................................12 
5.0 Contacts.........................................................................................................................................................13 
 
  
1.0 Overview 
This application note describes how the user can configure the interrupt control options of the VStdLib. Some 
applications provide their own lock/unlock functions, which better fulfill the application’s needs. Because of this the 
VStdLib provides a means which allows the application to use it’s own lock/unlock functions, instead of the 
implementation provided by the VStdLib.  
This application note describes the handling of this use case in more detail. 
1.1 Introduction 
The VStdLib provides functions to lock/unlock interrupts. There are three options to be set in the configuration tool, 
as shown in figure1. The first  option (Default) lets the VStdLib lock global interrupts. Depending on the hardware 
plattform it is also possible to lock interrupts to a certain level. The lock is implemented by the VStdLib itself.  
 
 
Figure 1: Possible configuration options for VStdLib interrupt control

--- Page 2 ---
Application Interrupt Control with VStdLib 
 
   
 
 2 
Application Note  AN-ISC-2-1081 
 
 
The second option (OSEK) is to configure the VStdLib in a way that locking of interrupts is done by means of 
OSEK OS functions. The third and last option (User defined) requires the application to perform the 
locking/unlocking functionality within callback functions. 
This application note focusses mainly on the third option. It describes the way the application has to implement the 
callback functions required by the VStdLib.  
 
 
Figure 2: Configuration of interrupt control by application 
 
Figure 2 shows the VStdLib configuration dialog, if interrupt control by application is configured. The user has to 
enter the names of two functions in the dialog, which will be called by the VStdLib in order to lock/unlock interrupts. 
If the user has specified the callback function names as shown in figure 2, the application must provide the 
implementations of these two two functions. The prototypes are: 
 
void ApplNestedDisable(void); 
void ApplNestedRestore(void); 
 
From now on these two function names will be used within this application note. 
These two functions are called by the VStdLib, in case any Vector component requests a lock for a critical section. 
The user has to make sure that the locking mechanism within these two functions is sufficient to protect data. This 
depends heavily on the architecture of the application. The more priority levels exists, which call Vector functions, 
the more restrictive the lock must be. 
 
 
Please check the technical references of the other Vector components for restrictions regarding the call 
context of the API functions.

--- Page 3 ---
Application Interrupt Control with VStdLib 
 
   
 
 3 
Application Note  AN-ISC-2-1081 
 
2.0 Interrupt Control by Application 
This configuration option is usually used, if a global lock is not desired by the user or special lock mechanisms are 
used. Once this option is configured, there are two functions to be provided by the application. The user can 
specify the names of these functions in the configuration dialog of the VStdLib. The VStdLib calls these functions 
instead of directly locking/unlocking interrupts. This means, if any Vector component requests an interrupt lock, it is 
finally performed by the application provided functions. 
The first function is called, in order to perform a lock operation. It is expected, that the application function stores 
the current interrupt state(or any other), in order to restore it later. The second function is to restore the previously 
saved lock state.  
The implementation of these two functions is up to the user. The user may lock just certain interrupt sources or set 
a mutex, semaphore or whatever ensures consistent data and fulfills the call context requirements, described in the 
Vector component specific technical references. 
2.1 Constraints 
The usage of Interrupt Control by Application has some constraints, which have to be taken into account. The 
following chapters describe them. 
2.1.1 Constraint 1: Nested Calls 
It is expected that the two callback functions (ApplNestedDisable()/-Restore()) are implemented in a way that 
nested calls are possible. This means if the function ApplNestedDisable() was called by some software component 
it may happen that this function is called again from somewhere else. This has to be taken into account when 
saving and restoring the interrupt state! The implementer of these two function can assume that the number of lock 
and unlock calls is identical and nesting is balanced. 
2.1.2 Constraint 2: Recursive Calls when Disabling CAN Interrupts 
Instead of implementing an own lock mechanism, the user could configure interrupt control by application and call 
the CAN driver’s CanCanInterruptDisable()/-Restore() functions. These two function simply disable CAN interrupts 
for the given CAN channel. These two CAN driver functions protect the access to their state variables by means of 
the VStdLib’s lock mechanism, which would again be implemented by the callbacks provided by the application. 
This would cause an indirect recursion. 
 
 
Please note that CanCanInterruptDisable()/Restore() shall not be called from 
ApplNestedDisable()/Restore(). This application note does not provide a solution for this use case! 
 
2.1.3 Constraint 3: No Locking when Disabling CAN Interrupts 
One could think of letting the application directly modify the interrupt flags of the CAN controller, to overcome the 
recursion, described in the previous chapter. But this would cause the CAN interrupts to be never locked, when 
CanCanInterruptDisable() is called, by any component. The reason is that the application’s interrupt lock code 
would interfere with the code in the CAN driver’s function CanCanInterruptDisable(). The following pseudo code 
shows the way CanCanInterruptDisable() is implemented. It is assumed that ApplNestedDisable()/-Restore() are 
implemented to allow nested calls.

--- Page 4 ---
Application Interrupt Control with VStdLib 
 
   
 
 4 
Application Note  AN-ISC-2-1081 
 
 
/* CAN Interrupt will be never locked in this example!!! */ 
void CanCanInterruptDisable(CAN_CHANNEL_CANTYPE_ONLY) 
{ 
  ApplNestedDisable(); 
  Lock CAN interrupts 
  ApplNestedRestore(); 
} 
 
void ApplNestedDisable(void) 
{ 
  Save current CAN interrupt state(); 
  Lock CAN Interrupts(); 
} 
 
void ApplNestedRestore(void) 
{ 
  Restore CAN interrupts to previous state(); 
} 
 
Figure 3 shows what happens in this case. The function CanCanInterruptDisable() calls ApplNestedDisable() in 
order to protect an internal counter. This lock fun

[… 7 further page(s) not extracted …]
