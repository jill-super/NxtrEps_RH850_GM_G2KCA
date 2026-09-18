---
title: "Assist Path Firewall — AssiPahFwl MDD"
description: "Converted Design / Integration Document from AssiPahFwl_MDD.docx (DOCX, 111 KB)."
---

:::note
Converted from `SF034A_AssiPahFwl_Impl/doc/AssiPahFwl_MDD.docx` (Design / Integration Document; original DOCX, about 111 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF034A_AssiPahFwl_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

AssiPahFwl

Feb 05, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Sarika Natu,

KPIT Technologies,

India

Change History

Table of Contents

1	AssiPahFwl & High-Level Description	5

2	Design details of software module	6

2.1	Graphical representation of AssiPahFwl	6

2.2	Data Flow Diagram	6

2.2.1	Component level DFD	6

2.2.2	Function level DFD	6

3	Constant Data Dictionary	7

3.1	Program (fixed) Constants	7

3.1.1	Embedded Constants	7

4	Software Component Implementation	8

4.1	Sub-Module Functions	8

4.1.1	Init: AssiPahFwl_Init1	8

4.1.1.1	Design Rationale	8

4.1.1.2	Module Outputs	8

4.1.2	Per: AssiPahFwl_Per1	8

4.1.2.1	Design Rationale	8

4.1.2.2	Store Module Inputs to Local copies	8

4.1.2.3	(Processing of function)………	8

4.1.2.4	Store Local copy of outputs into Module Outputs	8

4.2	Server Runables	8

4.3	Interrupt Functions	8

4.4	Module Internal (Local) Functions	8

4.4.1	Local Function #1	8

4.4.1.1	Design Rationale	9

4.4.1.2	Processing	9

4.4.2	Local Function #2	9

4.4.2.1	Design Rationale	9

4.4.2.2	Processing	9

4.4.3	Local Function #3	9

4.4.3.1	Design Rationale	9

4.4.3.2	Processing	10

4.4.4	Local Function #4	10

4.4.4.1	Design Rationale	10

4.4.4.2	Processing	10

4.4.5	Local Function #5	10

4.4.5.1	Design Rationale	10

4.4.5.2	Processing	10

4.5	GLOBAL Function/Macro Definitions	11

5	Known Limitations with Design	12

6	UNIT TEST CONSIDERATION	13

Appendix A	Abbreviations and Acronyms	14

Appendix B	Glossary	15

Appendix C	References	16

AssiPahFwl & High-Level Description

Refer FDD

Design details of software module

Graphical representation of AssiPahFwl

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

Software Component Implementation

Sub-Module Functions

Init: AssiPahFwl_Init1

Design Rationale

Refer FDD

Module Outputs

Refer FDD

Per: AssiPahFwl_Per1

Design Rationale

Refer FDD

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runnables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

LowrBndLpFil_MotNwtMtr_T_f32  and UpprBndLpFil_MotNwtMtr_T_f32 will be updated in this function.

Processing

Refer to the subsystems 'Determine HiFreqAsst Boundaries' and 'Low pass filter boundaries' in FDD.

Local Function #2

Design Rationale

BasAssiLowrBnd_MotNwtMtr_T_f32 and BasAssiUpprBnd_MotNwtMtr_T_f32 will be updated in this function

Processing

Refer the subsystem ‘Determine_BaseAsst_Boundaries’ implementation in FDD.

Local Function #3

Design Rationale

HiFrqOverBnd_MotNwtMtr_T_Logl  and BasAssiOverBnd_MotNwtMtr_T_Logl will be updated in this function.

Processing

Refer to the section ‘Check both command paths for reaching boundary limits, if so begin de bounce counters’ in FDD.

Local Function #4

Design Rationale

 AssiPahLimrActv_Uls_T_f32 will be updated in this function

Processing

Refer to the section ‘Check Input commands vs. Fwl Output command for Assist Recovery Conditions’ in FDD.

Local Function #5

Design Rationale

None

Processing

Refer ‘Set_Faults’ subsystem in FDD.

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

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

Description | Author | Version | Date
Initial Version | Sarika Natu(KPIT Technologies) | 1.0 | 05-Feb-2016
Constant Name | Resolution | Units | Value
NODEBSTEP_CNT_U16 | NA | NA | 65535U
Function Name | Dynamic_Assi_Boundary | Type | Min | Max
Arguments Passed | VehSpd_Kph_T_u9p7 | Uint16 | 0 | 511
 | HwTq_HwNwtMtr_T_f32 | Float32 | -10.0 | 10.0
 | LoFrqInp_MotNwtMtr_T_f32 | Float32 | -16 | 16
 | *LowrBndLpFil_MotNwtMtr_T_f32 | Float32* | -16 | 16
 | *UpprBndLpFil_MotNwtMtr_T_f32 | Float32* | -16 | 16
Return Value | HiFrqAssiLimd_MotNwtMtr_T_f32 | Float32 | -16 | 16
Function Name | Base_Assi_Boundary | Type | Min | Max
Arguments Passed | HwTrq_HwNwtMtr_T_f32 | Float32 | -20.0 | 20.0
 | VehSpd_Kph_T_u9p7 | Uint16 | 0 | 511
 | AssiCmdBas_MotNwtMtr_T_f32 | Float32 | -8.8 | 8.8
 | BasAssiLowrBnd_MotNwtMtr_T_f32 | float32* | -16 | 16
 | BasAssiUpprBnd_MotNwtMtr_T_f32 | float32* | -16 | 16
Return Value | BasAssiLimd_MotNwtMtr_T_f32 | Float32 | -16 | 16
