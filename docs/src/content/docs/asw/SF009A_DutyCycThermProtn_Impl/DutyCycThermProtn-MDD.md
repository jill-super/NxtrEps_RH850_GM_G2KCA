---
title: "Duty Cycle Thermal Protection — DutyCycThermProtn MDD"
description: "Converted Design / Integration Document from DutyCycThermProtn_MDD.docx (DOCX, 192 KB)."
---

:::note
Converted from `SF009A_DutyCycThermProtn_Impl/doc/DutyCycThermProtn_MDD.docx` (Design / Integration Document; original DOCX, about 192 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF009A_DutyCycThermProtn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

DutyCycThermProtn

Prepared By: 

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Change History

Table of Contents

DutyCycThermProtn & High-Level Description

The purpose of the Thermal Duty Cycle Protection is to limit and protect the system from excessive use, based on motor rotational velocity and system temperature. It also provides protection status information for use by other functions.

Design details of software module

Graphical representation of DutyCycThermProtn

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

Refer .m file

Software Component Implementation

Sub-Module Functions

Init: DutyCycThermProtn_Init1

Design Rationale

Refer FDD

Module Outputs

Refer FDD

Per: DutyCycThermProtn_Per1

Design Rationale

DutyCycThermProtn_Per1 function is divided into various functions to reduce the cyclomatic complexity.

The subsystems ‘Multiplier’ and ‘FilterPercMax’ are clubbed into ‘MultiFilterPercMax’ local function.

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

Name of local function matches with subsystem name from FDD

Processing

Local Function #2

Design Rationale

Name of local function matches with subsystem name from FDD

Note: The outputs of the function are Mult12Temp_DegCgrd_T_s15p0, Mult36Temp_DegCgrd_T_s15p0 and SlcTemp_DegCgrd_T_f32.

Processing

None

Local Function #3

Design Rationale

Name of local function matches with subsystem name from FDD

Processing

None

Local Function #4

Design Rationale

The subsystems ‘Multiplier’ and ‘FilterPercMax’ are clubbed into ‘MultiFilterPercMax’ local function.

Note: The outputs of the function are MaxOut_Uls_T_u16p0 and ThermLimSlowFilMax_Uls_T_f32.

Processing

None

Local Function #5

Design Rationale

Name of local function matches with subsystem name from FDD

Processing

None

Local Function #6

Design Rationale

Local Function #

Design Rationale

None.

Processing

None

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

Function UseInpLowr to be tested only as called by the component; input and output ranges will not be reached.

Function UseInpLowr’s TableX must have strictly increasing elements.

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
Initial Version | Sarika Natu(KPIT Technologies) | 1.0 | 02-Oct-2015
Updated to version 2.0.0 of FDD | Krishna Anne | 2.0 | 07-Apr-2016
Fix for anomaly EA4# 7558 | Krishna Anne | 3.0 | 29-Sep-2016
 |  |  | 
Constant Name | Value
 | 
THERMLOADLIMSIZE_CNT_U08 | 8
MULTFILTERSIZE_CNT_U08 | 6
Function Name | FiltSVReinit | Type | Min | Max
Arguments Passed | IgnTiOff_Cnt_T_u32 | uint32 | 0 | 1720000
 | VehTiVld_Cnt_T_Logl | Boolean | 0 | 1
Return Value | None |  |  | 
Function Name | TemperatureSelection | Type | Min | Max
Arguments Passed | DiagcStsLimdTPrfmnc_Cnt_T_Logl | boolean | 0 | 1
 | EcuTFild_DegCgrd_T_f32 | float32 | -50 | 150
 | MotFetT_DegCgrd_T_f32 | float32 | -50 | 200
 | MotMagT_DegCgrd_T_f32 | float32 | -50 | 150
 | MotWidgT_DegCgrd_T_f32 | float32 | -50 | 300
 | *Mult12Temp_DegCgrd_T_ s15p0 | Sint16 | -50 | 200
 | *Mult36Temp_DegCgrd_T_s15p0 | Sint16 | -50 | 300
Return Value | SlcTemp_DegCgrd_T_s15p0 | sint16 | -50 | 300
