---
title: "Assist High Frequency — AssiHiFrq MDD"
description: "Converted Design / Integration Document from AssiHiFrq_MDD.docx (DOCX, 96 KB)."
---

:::note
Converted from `SF028A_AssiHiFrq_Impl/doc/AssiHiFrq_MDD.docx` (Design / Integration Document; original DOCX, about 96 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF028A_AssiHiFrq_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

AssiHiFrq

August 04, 2015

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Kathleen Creager,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	AssiHiFrq High-Level Description	4

2	Design details of software module	5

2.1	Graphical representation of AssiHiFrq	5

2.2	Data Flow Diagram	5

2.2.1	Component level DFD	5

2.2.2	Function level DFD	5

3	Constant Data Dictionary	6

3.1	Program (fixed) Constants	6

3.1.1	Embedded Constants	6

4	Software Component Implementation	7

4.1	Sub-Module Functions	7

4.1.1	Init: AssiHiFrqInit1	7

4.1.1.1	Design Rationale	7

4.1.1.2	Module Outputs	7

4.1.2	Per: AssiHiFrqPer1	7

4.1.2.1	Design Rationale	7

4.1.2.2	Store Module Inputs to Local copies	7

4.1.2.3	(Processing of function)………	7

4.1.2.4	Store Local copy of outputs into Module Outputs	7

4.2	Server Runables	7

4.3	Interrupt Functions	8

4.4	Module Internal (Local) Functions	8

4.5	GLOBAL Function/Macro Definitions	8

5	Known Limitations with Design	9

6	UNIT TEST CONSIDERATION	10

Appendix A	Abbreviations and Acronyms	11

Appendix B	Glossary	12

Appendix C	References	13

AssiHiFrq High-Level Description

Implements the SF028A_AssiHiFrq_Design FDD. This function provides a means of compensating for system 

inertia and road feedback. It is tunable over both vehicle speed and handwheel torque to obtain the desired 

level of disturbance rejection under various operating conditions. It passes handwheel torque through a high-pass 

filter and multiplies the resulting signal by a tunable gain factor. The output is known as high-frequency assist 

and is simply added to the usual assist calculated elsewhere

Design details of software module

Graphical representation of AssiHiFrq

Data Flow Diagram

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: AssiHiFrqInit1

Design Rationale

Init function is present in DataDict.m file but not shown in FDD model, and no initialization logic is needed.  This is implemented as an empty function.

Module Outputs

None

Per: AssiHiFrqPer1

Design Rationale

FDD model does not contain a block named AssiHiFrqPer1; this function implements the AssiHiFrq block.

BilnrIntrpnWithRound_u16_u16MplXu16MplY function from NxtrIntrpn library used to implement the 2-D Lookup tables in the SF028A_AssiHiFrq/AssiHiFrq/AssiHiFrq/Determine Gain model block.

Blnd_f32 function from NxtrMath library used to implement the part of the model that computes GainVal_MtrNmpHwNm from the outputs of the three bilinear interpolation functions in the SF028A_AssiHiFrq/AssiHiFrq/AssiHiFrq/Determine Gain model block.

FilHpUpdGain  and FilHpUpdOutp_f32 functions from the NxtrFil library used to implement HP-CF Filter block in the SF028A_AssiHiFrq/AssiHiFrq/AssiHiFrq model block.

A note in the model mentions that the frequency lookup table for the high pass filter cutoff frequency could be converted to the filter gain values at initialization.  This was not done because the DataDict.m file did not contain the necessary IRV for the converted table, and the FilHpUpdGain library function expects frequency in Hz; if this throughput improvement (converting the frequency table once in initialization) is made in the future, a new version of FilHpUpdGain will be needed.  

LnrIntrpn_u16_u16VariXu16VariY function from NxtrIntrpn library used to implement the “freq lookup” block in the SF028A_AssiHiFrq/AssiHiFrq/AssiHiFrq model block.

Store Module Inputs to Local copies

See FDD

(Processing of function)………

See FDD, and design rationale noted above.

Store Local copy of outputs into Module Outputs

See FDD

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

None

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

Description | Author | Version | Date
Initial Version | Kathleen Creager | 01.00.00 | 04-Aug-2015
Constant Name | Resolution | Units | Value
None | <Refer MDD guidelines [1]> | <Refer MDD guidelines [1]> | <Refer MDD guidelines [1]>
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
