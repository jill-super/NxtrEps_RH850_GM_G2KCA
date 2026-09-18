---
title: "End of Travel Protection — EotProtn MDD"
description: "Converted Design / Integration Document from EotProtn_MDD.docx (DOCX, 154 KB)."
---

:::note
Converted from `SF018A_EotProtn_Impl/doc/EotProtn_MDD.docx` (Design / Integration Document; original DOCX, about 154 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF018A_EotProtn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

EotProtn

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

,

Change History

Table of Contents

EotProtn & High-Level Description

The End of Travel Protection function specifies performance attributes as the steering system approaches the mechanical end of travel of the steering gear. 

Design details of software module

Graphical representation of EotProtn

Data Flow Diagram

See FDD

Component level DFD

See FDD

Function level DFD

See FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: EotProtn_Init1

Design Rationale

Refer FDD

Module Outputs

Refer FDD

Per: EotProtn_Per1

Design Rationale

EotProtn_Per1 function is divided into various functions to reduce the cyclomatic complexity.

The limiting of ‘EotAssiSca’ output is performed in SoftEndStop subsystem in FDD. But in code it is limiting calculations are done where the output is calculated i.e. FildEotGain function.

Store Module Inputs to Local copies

Refer FDD

 (Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

None

Note: Outputs of “EotVelImpct” function is - EotMotTqLim_MotNwtMtr_T_f32.

Processing

Refer to the “EotVelImpct” subsystem of the Simulink model of the design

Local Function #2

Design Rationale

None

Note: Outputs of “LimPosnDetd” function is - LimPosn_HwDeg_T_f32.

Processing

Refer to the “LimPosnDetd” subsystem of the Simulink model of the design

Local Function #3

Design Rationale

None

Note: Outputs of “CalcEntrGain” function is - EntrGain_Uls_T_f32.

Processing

Refer to the “CalcEntrGain” subsystem of the Simulink model of the design

Local Function #4

Design Rationale

Calculation of Filtered Handwheel torque is done after ‘CalcExitGain’ function is executed.

Note: Outputs of “CalcExitGain” function is - FildHwTq_HwNwtMtr_T_f32

Processing

Refer to the “CalcExitGain” subsystem of the Simulink model of the design

Local Function #5

Design Rationale

None

Note: Outputs of “CalcEotGain” function is - EotGain_Uls_T_f32

Processing

Refer to the “CalcEotGain” subsystem of the Simulink model of the design

Local Function #6

Design Rationale

Limit of EotAssiSca is moved to local function FildEotGain.

Note: Outputs of “FildEotGain” function is - EotAssiSca_Uls_T_f32

Processing

Refer to the “FildEotGain” subsystem of the Simulink model of the design

Local Function #7

Design Rationale

None

Note: Outputs of “CalcEotDampg” function is - EotDampgCmd_MotNwtMtr_T_f32

Processing

Refer to the “CalcEotDampg” calculation of the Simulink model of the design

Local Function #8

Design Rationale

None

Note: Outputs of “EotActvCmdCalc” function is - EotActvCmd_MotNwtMtr_T_f32

Processing

Refer to the “EotActvCmdCalc” calculation of the Simulink model of the design

Local Function #9

Design Rationale

None

Processing

Refer to the “SoftEndStopStCtrl” calculation of the Simulink model of the design

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

None

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

 | Description | Author | Version | Date
 | Initial Version | Sarika Natu(KPIT Technologies) | 1.0 | 01-Oct-2015
 |  |  |  | 
Constant | Value
DAMPGPTSIZE_CNT_U08 | 2
DAMPGVEHSPDSIZE_CNT_U08 | 4
GAINVEHSPDSIZE_CNT_U08 | 5
Function Name | EotVelImpct | Type | Min | Max
Arguments Passed | HwAgEotCw_HwDeg_T_f32 | float32 | 360 | 900
 | HwAgEotCcw_HwDeg_T_f32 | float32 | -900 | -360
 | HwAg_HwDeg_T_f32 | float32 | -1440 | 1440
 | VehSpd_Kph_T_f32 | float32 | 0 | 511
 | HwAgAuthy_Uls_T_f32 | float32 | 0 | 1
 | MotVelCrf_MotRadPerSec_T_f32 | float32 | -1350 | 1350
Return Value | EotMotTqLim_MotNwtMtr_T_f32 | float32 | 0 | 8.8
Function Name | LimPosnDetd | Type | Min | Max
Arguments Passed |  |  |  | 
 |  |  |  | 
 | HwAgEotCcw_HwDeg_T_f32 | float32 | -900 | -360
 | HwAg_HwDeg_T_f32 | float32 | -1440 | 1440
Return Value | LimPosn_HwDeg_T_f32 | float32 | -1440 | 1440
