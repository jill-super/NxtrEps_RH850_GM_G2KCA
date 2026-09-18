---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — SafetyManual"
description: "Converted Safety Manual / Safety Case from SafetyManual.pdf (PDF, 268 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/SafetyManuals/SafetyManual.pdf` (Safety Manual / Safety Case; original PDF, about 268 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Safety Manual
MICROSAR Safe

--- Page 2 ---
1  General Part
1.1  Introduction
1.1.1  Purpose
This document describes the assumptions made by Vector during the development of
MICROSAR  Safe  [2].  This  document  provides  information  on  how  to  integrate
MICROSAR Safe into your safety-related project. 
This document is intended for the use by the user of MICROSAR Safe. It should be
read by project managers, safety managers, and engineers to allow proper integration
of MICROSAR Safe.
1.1.2  Scope
This document covers aspects of components that are marked with an ASIL in the
delivery  description  provided  by  Vector.  Neither  QM  Vector  components,  nor
components by other venders are in the scope of this document.
1.1.3  Definitions
Term Definition
User of
MICROSAR Safe
Integrator of components provided by Vector.
MICROSAR Safe MICROSAR Safe comprises MICROSAR SafeBSW and
MICROSAR SafeRTE as Safety Element out of Context.
MICROSAR SafeBSW is a set of components, that are developed
according to ISO 26262 [1], and are provided by Vector in the
context of this delivery. The list of MICROSAR Safe components in
this delivery can be taken from the documentation of the delivery. 
Critical section A section of code that needs
Configuration
data
TBD
Generated code Source code that is generated as a result of the configuration in
DaVinci Configurator Pro
Partition A set of memory regions that is accessible by tasks and ISRs.
Synonym to OSApplication.
The words shall, shall not, should, can in this document are to be interpreted as
described here: 
1. Shall means that the definition is an absolute requirement of the specification.
2. Shall not means that the definition is an absolute prohibition of the specification.
3. Should means that there may exist valid reasons in particular circumstances to
ignore a particular definition, but the full implications must be understood and
carefully weighed before choosing a different course.
4. Can means that a definition is truly optional.
Safety Manual
© 2015, Vector Informatik GmbH Version: Draft 2 / 19

--- Page 3 ---
The user of MICROSAR Safe can deviate from all constraints and requirements in this
Safety  Manual  in  the  responsibility  of  the  user  of  MICROSAR  Safe,  if  equivalent
measures are used.
If  a  measure  is  equivalent  can  be  decided  in  the  responsibility  of  the  user  of
MICROSAR Safe. 
1.1.4  References
No. Source Title Version
[1] ISO ISO 26262 Road vehicles — Functional safety (all parts) 2011/2012
[2] Vector ISO 26262 Compliance Documentation TBD
[3] Vector Product Information MICROSAR Safe TBD
[4] Vector Technical Reference MICROSAR Safe Silence Verifier 1.4
1.1.5  Overview
This document is automatically generated. The content of this document depends on
the components and micro-controller of your delivery.
The structure of this document comprises:
▪> a general section that covers all assumptions and constraints that are always
applicable, and
▪> a micro-controller specific section that covers all aspects of the selected micro-
controller (only if micro-controller specific components are part of the delivery),
and
▪>
a section for each component that covers its constraints and necessary verification
steps.
Vector's assumptions on the environment of the MICROSAR Safe components as well
as the integration process are described.
1.2  Concept
MICROSAR Safe comprises a set of components developed according to ISO 26262.
These components can be combined - together with other measures - to build a safe
system according to ISO 26262.
Safety Manual
© 2015, Vector Informatik GmbH Version: Draft 3 / 19

--- Page 4 ---
1.2.1  Assumed technical safety requirements
1.2.2  Assumed environment
ID: SMI-1 
Vector assumes that hardware faults are adequately addressed by the user
of MICROSAR Safe. 
The components of MICROSAR Safe can support in the detection and handling
of some hardware faults.
MICROSAR Safe does not provide redundant data storage.
The user of MICROSAR Safe especially has to address faults in volatile random
access memory, non-volatile memory, e.g. flash or EEPROM, and the CPU.
See also SMI-14. 
ID: SMI-17 
Vector  assumes  that  hardware  and  compiler  manuals  are  correct  and
complete. 
Vector uses the hardware reference manuals and compiler manuals for the
development of MICROSAR Safe. Vector has no means to verify correctness or
completeness of the hardware and compiler manuals.
Example information that may be critical from these manuals is the register
assignment by compiler. This information is used to built up the context that is
saved and restored by the operating system. 
ID: SMI-2 
Vector assumes that the platform types selected by the user of MICROSAR
Safe adequately reflect the hardware and compiler environment. 
The user of MICROSAR Safe is responsible for selecting the correct platform
types (PlatformTypes.h). Especially the size of the predefined types must match
the target environment.
Example: A uint32 must be mapped to an unsigned integer type with a size of 32
bits.
The user of MICROSAR Safe can use the platform types provided by Vector.
Vector has created and verified the platform types mapping according to the
information provided by the user of MICROSAR Safe. 
ID: SMI-10 
Vector assumes that the reset or powerless state is a safe state of the
system. 
This assumption is added to this Safety Manual, because it is used in Vector's
safety analyses and development process.
ID: SMI-12 
Vector assumes that the user of MICROSAR Safe initializes all components
of MICROSAR Safe prior to using them. 
This constraint is required by AUTOSAR anyway. It is added to this Safety
Manual, because Vector assumes initialized components in its safety analyses
and development process.
Correct initialization can be verified, e.g. during integration testing. 
Safety Manual
© 2015, Vector Informatik GmbH Version: Draft 4 / 19

--- Page 5 ---
ID: SMI-16 
Vector  assumes  that  the  user  of  MICROSAR  Safe  only  passes  valid
pointers at all interfaces to MICROSAR Safe components. 
Plausibility checks on pointers are performed by MICROSAR Safe (see also
SMI-18), but they are limited.
Also  the  length  and  pointer  of  a  buffer  provided  to  a  MICROSAR  Safe
component need to be consistent.
This assumption also applies to QM as well as ASIL components.
This can e.g. be verified using static code analysis tools, reviews and integration
testing. 
ID: SMI-20 
Vector assumes that the user of MICROSAR Safe implements a timing
monitoring using e.g. a watchdog. 
The components of MICROSAR Safe do not provide mechanisms to monitor
their own timing behavior.
Vector's MICROSAR Safe.Watchdog can be used to fulfill this assumption.
If  the  functional  safety  concept  also  requires  a  logic  monitoring,  Vector's
MICROSAR Safe.Watchdog can be used to implement it.
See also SMI-14. 
ID: SMI-33 
Vector  assumes  that  the  user  of  MICROSAR  Safe  provides  sufficient
resources in RAM, ROM, stack and CPU runtime for MICROSAR Safe. 
Selection of the micro-controller and memory capacities as well as dimensioning
of the stacks is in the responsibility of the user of MICROSAR Safe.
If  MICROSAR  Safe  components  have  specific  requirements,  these  are
documented in the respective Technical Reference document. 
ID: SMI-9 
Vector assumes that for one AUTOSAR functional cluster (e.g. System
Services,  Operating  System,  CAN,  COM,  etc.)  only  components  from
Vector are used. 
This assumption is required because of dependencies within the development
process of Vector.
This assumption does not apply to the MCAL or the EXT cluster.
Vector may have requirements on MCAL or EXT components depending on the
upper layers that are used and provided by Vector. For example, the watchdog
driver is considered to have safety requirements allocated to its initialization and
triggering services. Details are described in the component specific parts of this
safety manual.
The only exception to this assumption is the Flash EEPROM Emulation (FEE)
for Infineon micro-controllers. Vector does not provide a FEE for Infineon micro-
controllers. 
Safety Manual
© 2015, Vector Informatik GmbH Version: Draft 5 / 19

--- Page 6 ---
ID: SMI-32 
The user of MICROSAR Safe shall provide an argument for coexistence for
software  that  resides  in  the  same  partition  as  components  from
MICROSAR Safe. 
Vector considers an ISO 26262-compliant development process for the software
as an argument for coexistence (see [1] Part 9 Clause 6). 
Redundant  data  storage  as  the  only  measure  by  the  other  software  is  not
considered a sufficient measure.
If ASIL components provided by Vector are used, this requirement is fulfilled. 
1.2.3  Assumed process
ID: SMI-14 
The user of MICROSAR Safe shall be responsible for the functional safety
concept. 
The  overall  functional  safety  concept  is  in  the  responsibility  of  the  user  of
MICROSAR Safe. MICROSAR Safe can only provide pa

[… 13 further page(s) not extracted …]
