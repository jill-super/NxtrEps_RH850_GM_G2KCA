---
title: "Sensor Offset Learning — SnsrOffLrng MDD"
description: "Converted Design / Integration Document from SnsrOffLrng_MDD.docx (DOCX, 184 KB)."
---

:::note
Converted from `SF051A_SnsrOffsLrng_Impl/doc/SnsrOffLrng_MDD.docx` (Design / Integration Document; original DOCX, about 184 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF051A_SnsrOffsLrng_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

Sensor Offset Learning

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

SEPG,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents1	Introduction	6

2	SnsrOffsLrng & High-Level Description	7

3	Design details of software module	8

3.1	Graphical representation of SnsrOffsLrng	9

4	Constant Data Dictionary	11

4.1	Program (fixed) Constants	11

4.1.1	Embedded Constants	11

5	Software Component Implementation	12

5.1	Sub-Module Functions	12

5.1.1	Init: SnsrOffsLrngInit1	12

5.1.1.1	Design Rationale	12

5.1.1.2	Module Outputs	12

5.1.2	Per: SnsrOffsLrngPer1	12

5.1.2.1	Design Rationale	12

5.1.2.2	Store Module Inputs to Local copies	12

5.1.2.3	(Processing of function)………	12

5.1.2.4	Store Local copy of outputs into Module Outputs	12

5.1.1	Per: SnsrOffsLrngPer2	12

5.1.1.1	Design Rationale	12

5.1.1.2	Store Module Inputs to Local copies	12

5.1.1.3	(Processing of function)………	12

5.1.1.4	Store Local copy of outputs into Module Outputs	12

5.2	Server Runables	13

5.2.1	SnsrOffsLrng_RstHwTq	13

5.2.1.1	Design Rationale	13

5.2.1.2	Store Module Inputs to Local copies	13

5.2.1.3	(Processing of function)………	13

5.2.1.4	Store Local copy of outputs into Module Outputs	13

5.2.2	SnsrOffsLrng_RstYawAndAg	13

5.2.2.1	Design Rationale	13

5.2.2.2	Store Module Inputs to Local copies	13

5.2.2.3	(Processing of function)………	13

5.2.2.4	Store Local copy of outputs into Module Outputs	13

5.2.3	SnsrOffsLrng_SetHwAgOffs	13

5.2.3.1	Design Rationale	13

5.2.3.2	Store Module Inputs to Local copies	13

5.2.3.3	(Processing of function)………	13

5.2.3.4	Store Local copy of outputs into Module Outputs	13

5.2.4	SnsrOffsLrng_GetHwAgOffs	14

5.2.4.1	Design Rationale	14

5.2.4.2	Store Module Inputs to Local copies	14

5.2.4.3	(Processing of function)………	14

5.2.4.4	Store Local copy of outputs into Module Outputs	14

5.2.5	SnsrOffsLrng_SetHwTqOffs	14

5.2.5.1	Design Rationale	14

5.2.5.2	Store Module Inputs to Local copies	14

5.2.5.3	(Processing of function)………	14

5.2.5.4	Store Local copy of outputs into Module Outputs	14

5.2.6	SnsrOffsLrng_GetHwTqOffs	14

5.2.6.1	Design Rationale	14

5.2.6.2	Store Module Inputs to Local copies	14

5.2.6.3	(Processing of function)………	14

5.2.6.4	Store Local copy of outputs into Module Outputs	14

5.2.7	SnsrOffsLrng_SetYawRateOffs	15

5.2.7.1	Design Rationale	15

5.2.7.2	Store Module Inputs to Local copies	15

5.2.7.3	(Processing of function)………	15

5.2.7.4	Store Local copy of outputs into Module Outputs	15

5.2.8	SnsrOffsLrng_GetYawRateOffs	15

5.2.8.1	Design Rationale	15

5.2.8.2	Store Module Inputs to Local copies	15

5.2.8.3	(Processing of function)………	15

5.2.8.4	Store Local copy of outputs into Module Outputs	15

5.3	Module Internal (Local) Functions	15

5.3.1	Module Internal (Local) Functions	15

6	Known Limitations with Design	19

7	UNIT TEST CONSIDERATION	20

Appendix A	Abbreviations and Acronyms	21

Appendix B	Glossary	22

Appendix C	References	23

Introduction

Refer the Design Subproject.

SnsrOffsLrng & High-Level Description

Refer the Design Subproject.

Design details of software module

Graphical representation of SnsrOffsLrng

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

Init: SnsrOffsLrngInit1

Design Rationale

Refer the Design. 

Module Outputs

Refer the Design. 

Per: SnsrOffsLrngPer1

Design Rationale

Refer the Design. 

Store Module Inputs to Local copies

Refer the Design. 

 (Processing of function)………

Refer the Design. 

Store Local copy of outputs into Module Outputs

Refer the Design. 

Per: SnsrOffsLrngPer2

Design Rationale

Refer the Design. 

Store Module Inputs to Local copies

Refer the Design. 

 (Processing of function)………

Refer the Design. 

Store Local copy of outputs into Module Outputs

Refer the Design. 

Server Runables 

SnsrOffsLrng_RstHwTq

Design Rationale

Refer the Design. 

Store Module Inputs to Local copies

Refer the Design. 

 (Processing of function)………

Refer the Design. 

Store Local copy of outputs into Module Outputs

Refer the Design. 

SnsrOffsLrng_RstYawAndAg

Design Rationale

Refer the Design. 

Store Module Inputs to Local copies

Refer the Design. 

 (Processing of function)………

Refer the Design. 

Store Local copy of outputs into Module Outputs

Refer the Design. 

SnsrOffsLrng_SetHwAgOffs

Design Rationale

Refer the Design. 

Store Module Inputs to Local copies

Refer the Design. 

 (Processing of function)………

Refer the Design. 

Store Local copy of outputs into Module Outputs

Refer the Design. 

SnsrOffsLrng_GetHwAgOffs

Design Rationale

Refer the Design. 

Store Module Inputs to Local copies

Refer the Design. 

 (Processing of function)………

Refer the Design. 

Store Local copy of outputs into Module Outputs

Refer the Design. 

SnsrOffsLrng_SetHwTqOffs

Design Rationale

Refer the Design. 

Store Module Inputs to Local copies

Refer the Design. 

 (Processing of function)………

Refer the Design. 

Store Local copy of outputs into Module Outputs

Refer the Design. 

SnsrOffsLrng_GetHwTqOffs

Design Rationale

Refer the Design. 

Store Module Inputs to Local copies

Refer the Design. 

 (Processing of function)………

Refer the Design. 

Store Local copy of outputs into Module Outputs

Refer the Design. 

SnsrOffsLrng_SetYawRateOffs

Design Rationale

Refer the Design. 

Store Module Inputs to Local copies

Refer the Design. 

 (Processing of function)………

Refer the Design. 

Store Local copy of outputs into Module Outputs

Refer the Design. 

SnsrOffsLrng_GetYawRateOffs

Design Rationale

Refer the Design. 

Store Module Inputs to Local copies

Refer the Design. 

 (Processing of function)………

Refer the Design. 

Store Local copy of outputs into Module Outputs

Refer the Design. 

Module Internal (Local) Functions

Module Internal (Local) Functions

Calculate LearnHwAg

Description

No flowchart added. For Unit test FDD should provide the information needed regarding function processing

Calculate SOaCHierarchyManager

Description

No flowchart added. For Unit test FDD should provide the information needed regarding function processing

Calculate Perform_TqInpDetn

Description

No flowchart added. For Unit test FDD should provide the information needed regarding function processing

Calculate EnableLearning

Description

No flowchart added. For Unit test FDD should provide the information needed regarding function processing

Calculate CalculateKVector

Description

No flowchart added. For Unit test FDD should provide the information needed regarding function processing

Calculate EnablePreProcessing

Description

No flowchart added. For Unit test FDD should provide the information needed regarding function processing

Calculate UpdateCovarianceMatrix

Description

No flowchart added. For Unit test FDD should provide the information needed regarding function processing

TblSize_Cnt_T_u16 is size of the single dimension of TqMd

Version | Description | Author | Date
1 | Initial Version | Selva Sengottaiyan | 07-Feb-2016
2 | Updated as per FDD v 1.2.0 | Krishna Anne | 07-Mar-2016
 |  |  | 
Constant Name | Resolution | Units | Value
HWTQOFFSHILIM_HWNWTMTR_F32 | Single precision float | HwNwtMtr | 4
HWTQOFFSLOLIM_HWNWTMTR_F32 | Single precision float | HwNwtMtr | -4
VEHYAWRATEOFFSHILIM_VEHDEGPERSEC_F32 | Single precision float | VehDegPerSec | 20
VEHYAWRATEOFFSLOLIM_VEHDEGPERSEC_F32 | Single precision float | VehDegPerSec | -20
HWAGOFFSHILIM_HWDEG_F32 | Single precision float | HwDeg | -30
HWAGOFFSLOLIM_HWDEG_F32 | Single precision float | HwDeg | -30
MTRXSIZE_CNT_U08 | 1 | Cnt | 3
Function Name | LearnHwAg | Type | Min | Max | UTP Tol.
Arguments Passed | HwAgLrngLrngCdnVld_Cnt_T_logl | Boolean | FALSE | TRUE | 
 | HwAgLrngEna_Cnt_T_logl | Boolean | FALSE | TRUE | 
 | SysTqFild_HwNm_T_f32 | float32 | -8.8 | 8.8 | 
 | HandwheelPosition_HwDeg_T_f32 | float32 | -1440 | 1440 | 
Return Value | None |  |  |  | 
Function Name | SOaCHierarchyManager | Type | Min | Max | UTP Tol.
Arguments Passed | *EnableYOC_Cnt_T_logl | Boolean | FALSE | TRUE | 
 | *HwAgLrngEna_Cnt_T_logl | Boolean | FALSE | TRUE | 
 | *HwAgLrngRst_Cnt_T_logl | Boolean | FALSE | TRUE | 
Return Value |  |  |  |  | 
