---
title: "Operating System — Os Module Design Document"
description: "Converted Design / Integration Document from Os Module Design Document.docx (DOCX, 283 KB)."
---

:::note
Converted from `Os/doc/Os Module Design Document.docx` (Design / Integration Document; original DOCX, about 283 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Os](./)

*Conversion method: automatic text extraction from the Word document.*

For

Os

1/6/16

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

1.1	Purpose	5

1.2	Scope	5

2	Os & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of Os	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: Os_Init<n>	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: Os_Per<n>	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.2.1	<Server Runable Name>	9

5.2.1.1	Design Rationale	9

5.2.1.2	(Processing of function)………	10

5.3	Interrupt Functions	10

5.3.1	Interrupt Function Name	10

5.3.1.1	Design Rationale	10

5.3.1.2	(Processing of the ISR function)…..	10

5.4	Module Internal (Local) Functions	10

5.4.1	Local Function #1	10

5.4.1.1	Design Rationale	10

5.4.1.2	Processing	10

5.5	GLOBAL Function/Macro Definitions	10

5.5.1	GLOBAL Function #1	10

5.5.1.1	Design Rationale	11

5.5.1.2	processing	11

6	Known Limitations with Design	12

7	UNIT TEST CONSIDERATION	13

Appendix A	Abbreviations and Acronyms	14

Appendix B	Glossary	15

Appendix C	References	16

Introduction

Purpose

This design document will capture the design of the Nexteer Os Error Handling (NxtrOsErrHndlg) functionality.  This is the only portion of this component that is designed by Nexteer rather than a 3rd party.

Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance. 

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.  

May: indicates an optional action.

High-Level Description

The Nexteer designed portions of the Os component consist of the Os error processing.  This Nexteer specific design was embedded within the Os component itself since this functionality is specifically tied to the errors and names that this particular Os supports.  This error handling is expected to be called by the Os protection and error callout functions in any given project.  It interfaces with the Exception Handler that is created to react to the different categories of Os errors.

Design details of software module

<The Data Flow Diagrams should be created in the absence of this representation with the FDD.>

Graphical representation of NxtrOsErrHndlg (Expected External Intefaces)

Data Flow Diagram

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: 

None

Per: 

None

Server Runables 

NxtrOsErrHndlg

Design Rationale

This runnable will parse through the different Os errors that can be detected and interface into the Exception Handler component for handling of the different categories of errors.  This runnable is expected to be called by both the Os ErrorHook and the Os ProtectionHook as it handles all categories of Os errors.

 Processing

switch (OSErrorGetosCANError())

	case osdErrUEUnhandledException:

	case osdErrUEUnhandledCoreException:

	case osdErrUEUnhandledDirectBranch:

		/* Unhandled Exceptions */

		ProcUkwnExcpnErr(OSErrorGetosCANError())

	break

	case osdErrEXMemoryViolation:

		/* MPU Violations */

		ProcMpuExcpnErr(OSErrorGetosCANError());

	break

	case osdErrEXPrivilegedInstruction:

		/* Privileged Instruction Exceptions */

		ProcPrvlgdInstrExcpnErr(OSErrorGetosCANError());

	break

	case osdErrATWrongTaskPrio:

	case osdErrTTNotActivated:

	case osdErrTTNoImmediateTaskSwitch:

	case osdErrTTWrongActiveTaskID:

	case osdErrHTNotActivated:

	case osdErrHTNoImmediateTaskSwitch:

	case osdErrHTWrongActiveTaskID:

	case osdErrSHScheduleNotAllowed:

	case osdErrSHWrongActiveTaskID:

	case osdErrGSOddInvocation:

	case osdErrGIOddInvocation:

	case osdErrMTMissingTerminateTask:

	case osdErrEAIntAPIWrongSequence:

	case osdErrDAIntAPIDisabled:

	case osdErrSDWrongCounter:

	case osdErrREWrongCounter:

	case osdErrSGWrongCounter:

	case osdErrRGWrongCounter:

	case osdErrGRPriorityOccupied:

	case osdErrGRNoAccessRights:

	case osdErrGRWrongTaskID:

	case osdErrRRCeilingPriorityNotSet:

	case osdErrRRWrongTask:

	case osdErrRRNoReadyTaskFound:

	case osdErrRRWrongTaskID:

	case osdErrRRWrongHighRdyPrio:

	case osdErrSEWrongTaskPrio:

	case osdErrGEOddInvocation:

	case osdErrCAAlarmInternal:

	case osdErrWAWrongIDonHeap:

	case osdErrWAHeapOverflow:

	case osdErrWAUnknownAction:

	case osdErrWAWrongCounterID:

	case osdErrSOStackOverflow:

	case osdErrSUWrongTaskID:

	case osdErrCLWrongLibrary:

	case osdErrEHInterruptsEnabled:

	case osdErrSTMemoryError:

	case osdErrSTNoImmediateTaskSwitch:

	case osdErrSTWrongAppMode:

	case osdErrSTConfigCRCError:

	case osdErrSTConfigMagicNrError:

	case osdErrSTInvalidMajorVersion:

	case osdErrSTInvalidMinorVersion:

	case osdErrSTInvalidSTCfg:

	case osdErrQIWrongTaskPrio:

	case osdErrQRInterruptsEnabled:

	case osdErrQRWrongTaskID:

	case osdErrQRWrongTaskPrio:

	case osdErrQRWrongHighRdyPrio:

	case osdErrQSInterruptsEnabled:

	case osdErrQSNoReadyTaskFound:

	case osdErrQSWrongPriority:

	case osdErrQOWrongTaskID:

	case osdErrSPUnknownCase:

	case osdErrSGOddInvocation:

	case osdErrWSUnknownAction:

	case osdErrWSUnknownReaction:

	case osdErrWSWrongID:

	case osdErrGCOddInvocation:

	case osdErrBMResAlreadyMeasured:

	case osdErrBMInvalidProcessInStart:

	case osdErrBMInvalidProcessInStop:

	case osdErrBMInvalidResource:

	case osdErrETNoCurrentProcess:

	case osdErrASOddInvocation:

	case osdErrTAInvalidTaskState:

	case osdErrRSWrongTaskPrio:

	case osdErrPAInvalidAreaIndex:

	case osdErrPANoAccessRight:

	case osdErrPAInvalidAddress:

	case osdErrYOSystemStackOverflow:

	case osdErrYOTaskStackOverflow:

	case osdErrYOISRStackOverflow:

	case osdErrSCWrongSysCallParameter:

	case osdErrDPStartValidContext:

	case osdErrDPResumeInvalidContext:

	case osdErrDPInvalidTaskIndex:

	case osdErrDPInvalidApplicationID:

	case osdErrSUInvalidTaskIndex:

	case osdErrSUInvalidIsrIndex:

	case osdErrSUInvalidIsrPrioLevel:

	case osdErrCIInvalidIsrIndex:

	case osdErrCIInvalidIsrPrioLevel:

	case osdErrCIInvalidApplicationID:

	case osdErrCIMissingIntRequest:

	case osdErrCIInterruptIsMasked:

	case osdErrCIWrongIntPriority:

	case osdErrPIGetIMRInvalidIndex:

	case osdErrPISetIMRInvalidIndex:

	case osdErrPIClearIMRInvalidIndex:

	case osdErrPIWriteIMR8InvalidAddr:

	case osdErrPIWriteIMR16InvalidAddr:

	case osdErrPIWriteIMR32InvalidAddr:

	case osdErrPISetICRMaskInvalidAddr:

	case osdErrPIClearICRMaskInvalidAddr:

	case osdErrPIS

Description | Author | Version | Date
Initial Version | Lucas Wendling | 1 | 1/6/16
Constant Name | Resolution | Units | Value
None |  |  | 
Function Name |  | Type | Min | Max
Arguments Passed |  |  |  | 
 |  |  |  | 
Return Value |  |  |  | 
Function Name |  | Type | Min | Max
Arguments Passed |  |  |  | 
 |  |  |  | 
Return Value |  |  |  | 
