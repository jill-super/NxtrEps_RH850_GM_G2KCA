---
title: "Sensor Measurement Start — SnsrMeasStrt MDD"
description: "Converted Design / Integration Document from SnsrMeasStrt_MDD.docx (DOCX, 100 KB)."
---

:::note
Converted from `CM410B_SnsrMeasStrt_Impl/doc/SnsrMeasStrt_MDD.docx` (Design / Integration Document; original DOCX, about 100 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM410B_SnsrMeasStrt_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

SnsrMeasStrt

Nov 18, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Shruthi Raghavan,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

2	SnsrMeasStrt & High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of SnsrMeasStrt	6

3.2	Data Flow Diagram	6

3.2.1	Component level DFD	6

3.2.2	Function level DFD	6

4	Constant Data Dictionary	7

4.1	Program (fixed) Constants	7

4.1.1	Embedded Constants	7

5	Software Component Implementation	8

5.1	Sub-Module Functions	8

5.1.1	Init: SnsrMeasStrt_Init1	8

5.1.1.1	Design Rationale	8

5.1.1.2	Module Outputs	8

5.1.2	Per: SnsrMeasStrt_Per1	8

5.1.2.1	Design Rationale	8

5.1.2.2	Processing of function	8

5.2	Server Runnables	8

5.3	Interrupt Functions	9

5.3.1	SnsrMeasStrtIrq	9

5.3.1.1	Design Rationale	9

5.3.1.2	Processing of the ISR function	9

5.4	Module Internal (Local) Functions	9

5.5	GLOBAL Function/Macro Definitions	9

6	Known Limitations with Design	10

7	UNIT TEST CONSIDERATION	11

Appendix A	Abbreviations and Acronyms	12

Appendix B	Glossary	13

Appendix C	References	14

Introduction

Purpose

Module Design Document for CM410B SnsrMeasStrt

SnsrMeasStrt & High-Level Description

Torque Leg is critical factor in Feel issue. In order to minimize lag, it is required to synchronize trigger and time to read torque data should be just in time, so there will be minimum lag.

Design details of software module

Graphical representation of SnsrMeasStrt

Data Flow Diagram

Refer FDD

Component level DFD

Refer FDD

Function level DFD

Refer FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Refer to DataDict.m file for rest of the constants.

Software Component Implementation

Sub-Module Functions

Init: SnsrMeasStrt_Init1

Design Rationale

OSTM1 Timer has choosen for timing synchronization, because it was close to tied with OSTM0, same clock for accuracy Purpose, but TAUJ or TAUD any real time timer mechanism would work. Initialize OS Timer registers. Refer to CM410B_SnsrMeasStrt_PeripheralCfg.xlsx in the design package to see the specific register configurations. Unmask the OSTM1 EI-level mask able interrupt according to the instructions in Model for which both Os.h and osekext.h are required.

Module Outputs

Refer FDD

Per: SnsrMeasStrt_Per1

Design Rationale

OSTM0 is a free running counter for 2ms. OSTM0CNT is used to trigger torque measure sensor reads with a calibrated trigger delay to start this read (by setting a count value to OSTM1CMP for triggering its interval timer mode interrupt) before the periodic is called again.

 Processing of function

Refer to FDD

Server Runnables

None

Interrupt Functions

SnsrMeasStrtIrq

Design Rationale

PIMs belong to the RTE and so the corresponding header file is included in this file for the ISR to have TqMsgTrigCnt defined in scope. Client calls to Hw0TqMeas & Hw1TqMeas server runnables are possible from ISR because they are implemented as non-RTE also in the respective components.

Processing of the ISR function

ISR calls the HwTq0MeasTrigStrt_Oper, HwTq1MeasTrigStrt_Oper server runnables from CM650B and CM660B respectively. Each of these in turn triggers the TqSENT measurement from the corresponding Handwheel Torque Sensor.

Only client calls to server runnables are part of this ISR. Increments a PIM to capture how many timer triggers 	happen.

Module Internal (Local) Functions

None

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

ISR needs to execute in the same application region of the Torque Measurement Components.

DataDict.m file has known issues:

Context of ISR is wrong

The register given as input is OSTM0CMP whereas the one need is OSTM0CNT.

An anomaly has been submitted to fix this.

UNIT TEST CONSIDERATION

Overflow for the variable Rte_Pim_TqMsgTrigCnt is intentional as this is used as a rolling counter.

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
Initial Version | Shruthi Raghavan | EA4 01.00.01 | 11/18/16
Constant Name | Resolution | Units | Value
 |  |  | 
Abbreviation or Acronym | Description
DFD | Design functional diagram
MDD | Module design Document
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
