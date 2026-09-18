---
title: "Torque Oscillation — TqOscn MDD"
description: "Converted Design / Integration Document from TqOscn_MDD.docx (DOCX, 109 KB)."
---

:::note
Converted from `SF043A_TqOscn_Impl/doc/TqOscn_MDD.docx` (Design / Integration Document; original DOCX, about 109 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF043A_TqOscn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

TqOscn

Feb 05, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Krishna Kanth Anne,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	3

1.1	Purpose	3

1.2	Scope	3

2	<Component Name> & High-Level Description	3

3	Design details of software module	3

3.1	Graphical representation of <Component Name>	3

3.2	Data Flow Diagram	3

3.2.1	Component level DFD	3

3.2.2	Function level DFD	3

4	Constant Data Dictionary	3

4.1	Program (fixed) Constants	3

4.1.1	Embedded Constants	3

5	Software Component Implementation	3

5.1	Sub-Module Functions	3

5.1.1	Init: <ModuleName>Init<n>	3

5.1.1.1	Design Rationale	3

5.1.1.2	Module Outputs	3

5.1.2	Per: <ModuleName>_Per<n>	3

5.1.2.1	Design Rationale	3

5.1.2.2	Store Module Inputs to Local copies	3

5.1.2.3	(Processing of function)………	3

5.1.2.4	Store Local copy of outputs into Module Outputs	3

5.2	Server Runables	3

5.2.1	<Server Runable Name>	3

5.2.1.1	Design Rationale	3

5.2.1.2	(Processing of function)………	3

5.3	Interrupt Functions	3

5.3.1	Interrupt Function Name	3

5.3.1.1	Design Rationale	3

5.3.1.2	(Processing of the ISR function)…..	3

5.4	Module Internal (Local) Functions	3

5.4.1	Local Function #1	3

5.4.1.1	Design Rationale	3

5.4.1.2	Processing	3

5.5	GLOBAL Function/Macro Definitions	3

5.5.1	GLOBAL Function #1	3

5.5.1.1	Design Rationale	3

5.5.1.2	processing	3

6	Known Limitations with Design	3

7	UNIT TEST CONSIDERATION	3

Appendix A	Abbreviations and Acronyms	3

Appendix B	Glossary	3

Appendix C	References	3

Introduction

Purpose

TqOscn & High-Level Description

Please refer FDD.

Design details of software module

Graphical representation of TqOscn

Data Flow Diagram

Please refer FDD

Component level DFD

Please refer FDD

Function level DFD

Please refer FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: TqOscnInit1

Design Rationale

None

Module Outputs

None

Per: TqOscnPer1

Design Rationale

None

Store Module Inputs to Local copies

None

 (Processing of function)………

Please refer FDD

Store Local copy of outputs into Module Outputs

Please refer FDD

Server Runnables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1 

Local Function #2

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

None.

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
Initial Version | Krishna Kanth Anne | 1.0 | 05-Feb-2016
Constant Name | Resolution | Units | Value
Please refer .m file |  |  | 
Function Name | AmpRateLim | Type | Min | Max
Arguments Passed | LimdAmp_MotNwtMtr_T_f32 | Float32 | 0.0F | 1.2F
 | HwOscnRisngRampRate_MotNwtMtrPerSec_T_f32 | Float32 | 0.1F | 4400.0F
 | HwOscnFallRampRate_MotNwtMtrPerSec_T_f32 | Float32 | -4400.0F | -0.1F
 | HwOscnEna_Cnt_T_logl | Boolean | FALSE | TRUE
 | *NonZeroAmpFlg_Cnt_T_logl | Boolean | FALSE | TRUE
Return Value | RateLimdAmp_MotNwtMtr_T_f32 | Float32 | 0.0002F | -8.8F
Function Name | ChkFlg | Type | Min | Max
Arguments Passed | PhaAg_MatRad_T_f32 | Float32 | 0.125F | 0.628F
Return Value | TqOscnPhaAg_MatRad_T_f32 | Float32 | 0.0F | 0.628F
