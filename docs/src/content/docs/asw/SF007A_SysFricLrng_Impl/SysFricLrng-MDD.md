---
title: "System Friction Learning — SysFricLrng MDD"
description: "Converted Design / Integration Document from SysFricLrng_MDD.docx (DOCX, 197 KB)."
---

:::note
Converted from `SF007A_SysFricLrng_Impl/doc/SysFricLrng_MDD.docx` (Design / Integration Document; original DOCX, about 197 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF007A_SysFricLrng_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

SysFricLrng

 , 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

Introduction

Purpose

Scope

SysFricLrng High-Level Description

Refer FDD

Design details of software module

Refer FDD

Graphical representation of SysFricLrng

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

For rest of the constants, please refer Data Dictionary

Software Component Implementation

The detailed design of the function is provided in the FDD. 

Sub-Module Functions

Init: SysFricLrngInit1

Design Rationale

In MDD, filters are initialized inside the for loop using switch case but in code filters are initialized one by one without any conditions.	

In model, filters are initialized twice as it is not possible to use a variable for the filter initialization in the model. This is redundancy is not present in the code as variables are used for initializing the filters.

Module Outputs

Refer FDD

Per: SysFricLrngPer1

Design Rationale

Refer FDD

Store Module Inputs to Local copies

Refer FDD

 (Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runnables 

Server Runnable Name

ClrFricLrngOperMod

Design Rationale

Refer FDD

 (Processing of function)………

On server invocation call

Server Runnables 

Server Runnable Name

GetFricLrngData

Design Rationale

Refer FDD

 (Processing of function)………

On server invocation call

Server Runnable Name

GetFricOffsOutpDi

Design Rationale

Refer FDD

 (Processing of function)………

On server invocation call

Server Runnable Name

InitFricLrngTbl

Design Rationale

Refer FDD

 (Processing of function)………

On server invocation call

Server Runnable Name

SetFricLrngDatal

Design Rationale

Refer FDD

 (Processing of function)………

On server invocation call

Server Runnable Name

SetFricOffsOutpDi

Design Rationale

Refer FDD

 (Processing of function)………

On server invocation call

Interrupt Functions

None	

Interrupt Function Name

None

Design Rationale

NA

(Processing of the ISR function)…..

NA

Module Internal (Local) Functions

Local Function #1

Design Rationale

Processing

Refer to ‘FricLearning’ subsystem in FDD. 

Following per instance data is updated.

Also writes the outputs SysFricEstimd and SysSatnFricEstimd

Local Function #2

Design Rationale

Processing

Following PIMs are updated; refer to ‘RunningAndCalibrationModes’ subsystem in the FDD. FricOffs_HwNwtMtr_T_f32 is the output of this function

Also updates the input argument, *FricOffs_HwNwtMtr_T_f32.

Local Function #3

Design Rationale

Processing

Refer to ‘Raw Average Calculation’ subsystem in FDD.

Following per instance data is updated.

Local Function #4

Design Rationale

Processing

Refer to ‘Raw Average Calculation’ subsystem in FDD.

Following per instance data is updated.

Local Function #5

Design Rationale

Processing

Refer to ‘Range counter manager’ subsystem in FDD.

Following per instance data is updated.

Local Function #6

Design Rationale

Processing

Refer to ‘NTC_Pass’ and ‘NTC_Fail’ subsystem in FDD

Sets or resets the NTCNR_0X0A2

Local Function #7

Design Rationale

Processing

Refer to ‘Clearing Mode’ subsystem in FDD.

Following per instance data is updated.

Local Function #8

Design Rationale

Processing

Refer to ‘ResettingMode’ subsystem in FDD.

Following per instance data is updated. Also updates the input argument ‘*FricOffs_HwNwtMtr_T_f32’.

Local Function #9

Design Rationale

Processing

Refer to ‘HwAngConstraint‘ subsystem in FDD. Updates the input arguments, *HwAgOK_Cnt_T_Logl  and *SelHwAg_HwDeg_T_f32

Local Function #10

Design Rationale

Processing

Refer to ‘HwVelConstraint’ subsystem in FDD.

Local Function #11

Design Rationale

Code is optimized due to limitation with the model; hence code completely won’t match the model. There won’t be any impact on the functionality. 

In the model as it is not possible to break the for loop until the loop iterator reaches the configured constant threshold value, index corresponding to the position in ‘SysFricLrngVehSpd’ which breaches the conditions mentioned in ‘VehSpdIdxCalcn’ subsystem is calculated by successively adding the index value after multiplying it with either the condition true or false based on whether the vehicle speed value breaches the threshold mentioned in the FDD. In code as it is possible to exit the for loop as soon as a value in ‘VehSpdIdxCalcn’ breaches thresholds as mentioned in FDD, no such successive addition of loop counter is required.

Processing

Refer to ‘VehSpdConstraint’ subsystem in FDD. 

Local Function #12

Design Rationale

Processing

Refer to ‘ColTqconstraint’ subsystem in FDD.  Updates the *SelColTq_HwNwtMtr_T_f32.

GLOBAL Function/Macro Definitions

NA

Known Limitations with Design

None

UNIT TEST CONSIDERATION

In model, one based indexing is used but in code 0 based indexing is used.

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
Initial Version | Basavaraja Ganeshappa | 1.0 | 24th Mar 2016
Re base lined by pulling 1.3.1 | Basavaraja Ganeshappa | 2.0 | 25th Jul 2016
 |  |  | 
Constant Name | Resolution | Units | Value
INDEX0_CNT_U08 | 1 | CNT | 0U
INDEX1_CNT_U08 | 1 | CNT | 1U
INDEX2_CNT_U08 | 1 | CNT | 2U
INDEX3_CNT_U08 | 1 | CNT | 3U
SYSSATNFRICESTIMDMIN_HWNWMTR_F32 | 1 | HwNwMtr | 0.0F
SYSSATNFRICESTIMDMAX_HWNWMTR_F32 2 | 1 | HwNwMtr | 20.0F
SYSFRICESTIMDMIN_HWNWMTR_F32 | 1 | HwNwMtr | 0.0F
SYSFRICESTIMDMAX_HWNWMTR_F32 | 1 | HwNwMtr | 20.0F
SYSFRICOFFSMIN_HWNWMTR_F32 | 1 | HwNwMtr | -5.0F
SYSFRICOFFSMAX_HWNWMTR_F32 | 1 | HwNwMtr | 5.0F
Function Name | FricLearning | Type | Min | Max
Arguments Passed | SelHwAg_HwDeg_T_f32 | Float32 | -1440.0 | 1440.0
Arguments Passed | SelColTq_HwNwtMtr_T_f32 | Float32 | -10 | 10
Arguments Passed | VehSpdIdx_Cnt_T_u16 | Uint16 | 0 | 3
Arguments Passed | HwVelDir_Cnt_T_u08 | Uint8 | 0 | 1
 |  |  |  | 
Return Value | NA | NA | NA | NA
*Rte_Pim_RawAvrg() (Min:0, Max:20)
Rte_Pim_SatnAvrgFric()[VehSpdIdx_Cnt_T_u16] (Min:0, Max:20)
