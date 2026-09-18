---
title: "General Motors Overall State Manager — GmOvrlStMgr MDD"
description: "Converted Design / Integration Document from GmOvrlStMgr_MDD.docx (DOCX, 211 KB)."
---

:::note
Converted from `CF009A_GmOvrlStMgr_Impl/doc/GmOvrlStMgr_MDD.docx` (Design / Integration Document; original DOCX, about 211 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CF009A_GmOvrlStMgr_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

GmOvrlStMgr

, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

GmOvrlStMgr High-Level Description

Refer to FDD

Design details of software module

Graphical representation of GmOvrlStMgr

Data Flow Diagram

Refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Refer .m file

Software Component Implementation

Sub-Module Functions

Init: GmOvrlStMgrInit1

Design Rationale

Refer FDD 

Module Outputs

Refer FDD

Per: GmOvrlStMgrPer1

Design Rationale

Refer FDD for the overall functionality. 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

 GetGmLoaIgnCntr_Oper

Design Rationale

Refer FDD for the overall functionality. 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

SetGmLoaIgnCntr_Oper

Design Rationale

Refer FDD for the overall functionality. 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Description

 "Timer for VehStandStill" block implementation.

Local Function #2

Description

 "Timer for ShiftLvrRvs" block implementation.

Local Function #3

Description

 "ApaIntv" block implementation.

Local Function #4

Description

 "Timer for HwHaptcEna" block implementation.

Local Function #5

Description

Determination of 'LkaFlt'. 

Local Function #6

Description

Determination of ' LkaInhb'. 

Local Function #7

Description

Determination of ‘ ApaRcvrlFlt’. 

Local Function #8

Description

 This function validates conditions for all state transitions from ‘ APA Temporarily Inhibited’ state. 

‘*ApaSt_Cnt_T_u08’ is an output of this function. 

Local Function #9

Description

 This function validates conditions for all state transitions from ‘ APA Active’ state. 

‘*ApaSt_Cnt_T_u08’ is an output of this function. 

Local Function #10

Description

 This function validates conditions for all state transitions from and within ‘APA Availability for Control’ state. 

‘*ApaSt_Cnt_T_u08 and *HaptcSt_Cnt_T_u08’ are outputs of this function. 

Local Function #11

Description

Implementation of all LKA state transitions. 

‘*LkaSt_Cnt_T_u08’ is the output of this function. 

Local Function #12

Description

Implementation of all ESC state transitions. 

‘*EscSt_Cnt_T_u08’ is the output of this function. 

Local Function #13

Description

Implementation of all ESC state transitions. 

‘*HwAgServoCmd_HwDeg_T_f32’ is the output of this function. 

Local Function #14

Description

Implementation of “InctIgnCntrOnce” block

Local Function #15

Description

Implementation of”HwTqFildIntlChk” block. 

Local Function #16

Description

Implementation of “LKAIntv” block. 

Local Function #17

Description

Calculates LkaPrmntFlt to be used in state transitions. 

Local Function #18

Description

Implementation of “HaptcStTranActvToWaitFlg” block. 

Local Function #19

Description

Implementation of TranHaptcWaitToApaStActvFlg_Cnt_T_logl block.

Local Function #20

Description

Implementation of “EnHaptcFb” block. 

‘*HwOscnEna_Cnt_T_logl , * HwOscnMotAmp_MotNwtMtr_T_f32, *HwOscnFrq_Hz_T_f32 are  the outputs of this function.

Local Function #21

Description

Implementation of "En Or Di HaptcFb After Checking At Start Up" block. 

‘*HwOscnEna_Cnt_T_logl , * HwOscnMotAmp_MotNwtMtr_T_f32, *HwOscnFrq_Hz_T_f32 are  the outputs of this function.

Local Function #22

Description

Determine ApaNrcvrlFlt status.

Local Function #23

Description

Determine EscFlt status.

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

DataDict.m includes a default value for GmLoaIgnCntr NVM. This is redundant because the design uses the NVM GetErrorStatus function call to determine if this NVM value should be set to its default value of 0. 

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
Initial Version | Sankardu Varadapureddi | 1 | 6-Oct-2015
Added HwTq based intervention for LKA, handwheel buzz based on LoA key cycles | Nick Saxton | 2 | 11-Feb-2016
Changed argument names of ESCFlt local function | Nick Saxton | 3 | 13-Jun-2016
Updated graphical representation and edited local function section | Nick Saxton | 4 | 24-Jun-2016
 |  |  | 
Function Name | VehStandStillTmrElpdChk | Type | Min | Min | Max
Arguments Passed | VehSpdSecurMax_Kph_T_f32 | float32 | 0 | 511 | 511
Return Value | VehStandStillTiExcdd_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
Function Name | ShiftLvrRvsTmrElpdChk | Type | Min | Min | Max
Arguments Passed | ShiftLvrRvs_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
Return Value | ShiftLvrRvsTiExcdd_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
Function Name | ApaIntv | Type | Min | Min | Max
Arguments Passed | HwTq_HwNwtMtr_T_f32 | float32 | -10 | 10 | 10
Return Value | ApaIntv_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
