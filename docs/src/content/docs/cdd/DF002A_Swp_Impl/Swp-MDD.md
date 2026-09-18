---
title: "Software Programming Support — Swp MDD"
description: "Converted Design / Integration Document from Swp_MDD.docx (DOCX, 110 KB)."
---

:::note
Converted from `DF002A_Swp_Impl/doc/Swp_MDD.docx` (Design / Integration Document; original DOCX, about 110 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to DF002A_Swp_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

Swp

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Krishna Kanth Anne,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

1.2	Scope	4

2	PullCmpActv & High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of PullCmpActv	6

3.2	Data Flow Diagram	6

3.2.1	Component level DFD	6

3.2.2	Function level DFD	6

4	Constant Data Dictionary	7

4.1	Program (fixed) Constants	7

4.1.1	Embedded Constants	7

5	Software Component Implementation	8

5.1	Sub-Module Functions	8

5.1.1	Init: SwpInit1	8

5.1.2	Per: SwpPer1	8

5.1.3	Per: SwpPer2	8

5.2	Module Internal (Local) Functions	8

5.2.1	Local Function #1	8

5.2.1.1	Design Rationale	8

5.2.1.2	Processing	8

6	Known Limitations with Design	9

7	UNIT TEST CONSIDERATION	10

Appendix A	Abbreviations and Acronyms	11

Appendix B	Glossary	12

Appendix C	References	13

Introduction

Purpose

Scope

NA

 & High-Level Description

Please refer FDD.

Design details of software module

Please refer FDD.

Graphical representation of 

Data Flow Diagram

Please refer FDD.

Component level DFD

Please refer FDD.

Function level DFD

Please refer FDD.

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Please refer FDD.

Sub-Module Functions

Init: SwpInit1

Please refer FDD.

Design Rationale

Dummy Initialization function to correlate with the FDD (.m file)

Per: SwpPer1

Please refer FDD.

Design Rationale

For DFs, it was decided to use the module level variables in place of PIMs defined in the FDD (PIM section of .m file), This is a deviation from regular EA4 process.

All of the given PIMs from .m file are either defined as of Function level variables (if used in only one function) or Module level variables (if used in more than one function) in DFs.

Each of the Function level and Module level variables shall be volatile only when they are intended to be user modifiable as per the data dictionary .m file.

Deviations exist in the naming conventions for all of Function level and Module level variables from regular EA4 naming conventions.

Per: SwpPer2

Please refer FDD.

Design Rationale

For DFs, it was decided to use the module level variables in place of PIMs defined in the FDD (PIM section of .m file), This is a deviation from regular EA4 process.

All of the given PIMs from .m file are either defined as of Function level variables (if used in only one function) or Module level variables (if used in more than one function) in DFs.

Each of the Function level and Module level variables shall be volatile only when they are intended to be user modifiable as per the data dictionary .m file.

Deviations exist in the naming conventions for all of Function level and Module level variables from regular EA4 naming conventions.

Known Limitations with Design

None.

UNIT TEST CONSIDERATION

Please refer Init.txt file in the FDD design: DF002A_Swp_Design for initial values of Function level and Module level variables.

For DFs, it was decided to use the module level variables in place of PIMs defined in the FDD (PIM section of .m file), This is a deviation from regular EA4 process.

All of the given PIMs from .m file are either defined as of Function level variables (if used in only one function) or Module level variables (if used in more than one function) in DFs.

Each of the Function level and Module level variables shall be volatile only when they are intended to be user modifiable as per the data dictionary .m file.

Deviations exist in the naming conventions for all of Function level and Module level variables from regular EA4 naming conventions.

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
Initial Version | Krishna Kanth Anne | 1.0.0 | 20-Oct-2015
 |  |  | 
Constant Name | Resolution | Units | Value
Please refer DF002A_Swp_DataDict.m | NA | NA | NA
SWPSTRT_CNT_U16 | NA | NA | 0
SWPTRAN_CNT_U16 | NA | NA | 1
SWPDWELL_CNT_U16 | NA | NA | 2
SWPSTOP_CNT_U16 | NA | NA | 3
SWPRAMP_CNT_U16 | NA | NA | 4
SWPDONE_CNT_U16 | NA | NA | 5
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
