---
title: "Vehicle Signal Coding — VehSigCdng Module Design Document"
description: "Converted Design / Integration Document from VehSigCdng_Module Design Document.docx (DOCX, 132 KB)."
---

:::note
Converted from `SF033A_VehSigCdng_Impl/doc/VehSigCdng_Module Design Document.docx` (Design / Integration Document; original DOCX, about 132 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF033A_VehSigCdng_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

VehSigCdng

2, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Change History

Table of Contents

Introduction

Purpose

Scope

VehSigCdng High-Level Description

Refer to FDD

Design details of software module

Graphical representation of VehSigCdng

Data Flow Diagram

Component level DFD

Refer to FDD

Function level DFD

Refer to FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

See .m file

Software Component Implementation

Sub-Module Functions

Initialization sub-module VehSigCdngInit1()

Periodic sub-module VehSigCdngPer1()

Design Rationale - Fault Injection client call is conditional compiled based on “FLTINJENA” build constant.

Interrupt Service Routines

None

Server Runnable Functions

None

Module Internal (Local) Functions

Local Function #1

Refer to VehSpd block in the model

Notes: VehSpd_Kph_T_f32,  VehSpdVld_Cnt_T_logl are the outputs of the function

Local Function #2

Refer to VehLgtA block in the model

Notes: VehLgtA_KphpS_T_f32, VehLgtAVld_Cnt_T_logl are the outputs of the function

Local Function #3

Refer to VehLatA block in the model

Notes: VehLatA_MpSecSq_T_f32, VehLatAVld_Cnt_T_logl are the outputs of the function

Local Function #4

Refer to VehYawRate block in the model

Notes: VehYawRate_DegpS_T_f32, VehYawRateVld_Cnt_T_logl are the outputs of the function

Local Function #5

Refer to “Lateral Acceleration Estimation” block in the model

Notes: VehLatAEstimd_MtrPerSecSqd_T_f32, VehLatAEstimdVld_Cnt_T_logl  are the outputs of the function

Transition Functions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

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

 |  |  | 
 |  |  | 
 |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
 |  |  |  | 
Function Name | VehSigCdng_VehSpd | Type | Min | Max
Arguments Passed | VehSpdSerlCom_Kph_T_f32 | Float32 | 0 | 511
 | VehSpdVldSerlCom_Cnt_T_lgc | Boolean | FALSE | TRUE
 | VehSpdOvrd_Kph_T_f32 | Float32 | 0 | 511
 | VehSpdOvrdVld_Cnt_T_logl | Boolean | FALSE | TRUE
 | VehSpd_Kph_T_f32 | Float32 | 0 | 511
 | VehSpdVld_Cnt_T_logl | Boolean | FALSE | TRUE
Return Value | N/A |  |  | 
Function Name | VehSigCdng_VehLgtA | Type | Min | Max
Arguments Passed | VehLgtASerlCom_MpSecSq_T_f32 | Float32 | -180 | 180
 | VehLgtAVldSerlCom_Cnt_T_lgc | Boolean | FALSE | TRUE
 | VehLgtA_KphpS_T_f32 | Float32 | -50 | 50
 | VehLgtAVld_Cnt_T_logl | Boolean | FALSE | TRUE
Return Value | (if no value returned, write N/A) |  |  | 
