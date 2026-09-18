---
title: "Powerpack Compatibility Check — PwrpkCmpbltyChk MDD"
description: "Converted Design / Integration Document from PwrpkCmpbltyChk_MDD.docx (DOCX, 98 KB)."
---

:::note
Converted from `SF054A_PwrpkCmpbltyChk_Impl/doc/PwrpkCmpbltyChk_MDD.docx` (Design / Integration Document; original DOCX, about 98 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF054A_PwrpkCmpbltyChk_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

PwrpkCmpbltyChk

Apr 12, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Sankardu Varadapureddi,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	PwrpkCmpbltyChk High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of PwrpkCmpbltyChk	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: PwrpkCmpbltyChkInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: PwrpkCmpbltyChkPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.4.1	Local Function #1	9

5.4.1.1	Description	10

5.5	GLOBAL Function/Macro Definitions	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

Introduction

Purpose

Scope

PwrpkCmpbltyChk High-Level Description

Refer to FDD

Design details of software module

Graphical representation of PwrpkCmpbltyChk

Data Flow Diagram

Refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Refer .m file.

Local Constants

Software Component Implementation

Sub-Module Functions

Init: PwrpkCmpbltyChkInit1

Design Rationale

Refer FDD 

Module Outputs

Refer FDD

Per: PwrpkCmpbltyChkPer1

Design Rationale

Refer FDD 

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

Description

If both 'GearIdn1VldStat' and 'GearIdn2VldStat' are TRUE then return TRUE, else return FALSE. This function is created to reduce cyclomatic complexity.

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
Initial Version | Sankardu Varadapureddi | 1 | 12-Apr-2016
Function Name | GearIdnVldStatChk | Type | Min | Min | Max
Arguments Passed | GearIdn1VldStat_Cnt_T_lgc | boolean | FALSE | TRUE | TRUE
 | GearIdn2VldStat_Cnt_T_lgc | boolean | FALSE | TRUE | TRUE
Return Value | GearIdnVldStat_Cnt_T_lgc | boolean | FALSE | TRUE | TRUE
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
