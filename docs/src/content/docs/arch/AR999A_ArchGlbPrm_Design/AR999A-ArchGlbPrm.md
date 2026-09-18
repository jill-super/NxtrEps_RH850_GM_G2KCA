---
title: "Architecture Global Parameters — AR999A ArchGlbPrm"
description: "Converted Design / Integration Document from AR999A ArchGlbPrm.docx (DOCX, 135 KB)."
---

:::note
Converted from `AR999A_ArchGlbPrm_Design/Doc/AR999A ArchGlbPrm.docx` (Design / Integration Document; original DOCX, about 135 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to AR999A_ArchGlbPrm_Design](./)

*Conversion method: automatic text extraction from the Word document.*

Functional Design Document

For

Architecture Global Parameters

VERSION: 1.0

DATE: 05-Mar-2015

Prepared By: 

Nexteer Automotive,

 Saginaw, MI, USA

Revision History

Table of Contents

1	Abbrevations And Acronyms	4

2	References	5

3	Purpose	6

4	ArchGlbPrm Design	7

4.1	constants	7

4.1.1	float32 Constant specification	7

Abbrevations And Acronyms

References

This section lists the title & version of all the documents that are referred for development of this document

Purpose

The purpose of this document is to describe the design of the Architecture Global Parameters component including the selection criteria for items to be included in the component and the method used for specifying the values of the items. 

ArchGlbPrm Design

constants

The ArchGlbPrm component contains global constants that are either “mathematical” (e.g. the value of pi) or software-oriented (e.g. the value to be used as the zero threshold for float32 comparisons) in nature.  The constants are defined in AR999A_ArchGlbPrm_DataDict.m and implemented as #define statements in “ArchGlbPrm.h”.

float32 Constant specification

For each float32 constant, the number of digits was chosen based on the smallest number of digits needed to give the same float32 representation as the value calculated by Excel.  Rationale: this gives the most accurate representation possible for float32, while not containing a misleading number of digits beyond the resolution actually possible with float32.

Example procedure for determining the number of digits to use:

Enter the desired constant in Excel as a formula, e.g. “=PI()/2”

Copy the cell and paste as value into another cell

Select the new cell and copy the displayed value to the clipboard

Paste this value in a IEEE floating point conversion tool; record the single precision floating point representation (in hex), both rounded and unrounded.

Val = the pasted Excel value

X = number of digits in Val

Y = X

Do:

	Y = Y - 1

	Val1 = Val rounded to Y digits

While ((rounded single float representation of Val == rounded single float representation of Val1) AND 
             (unrounded single float representation of Val == unrounded single float representation of Val1))

Val2 = Val rounded to Y + 1 digits

Use Val2 as the constant value in the .h and .m files

Version | Description | Author | Section Modified | Date
1.0 | Initial Version | Kathleen Creager | All | 05-Mar-2015
Abbreviation | Description
Sr. No. | Title | Version
 |  | 
