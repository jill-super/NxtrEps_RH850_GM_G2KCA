---
title: "Nexteer Interpolation Library — NxtrIntrpn FDD"
description: "Converted Design / Integration Document from NxtrIntrpn FDD.docx (DOCX, 302 KB)."
---

:::note
Converted from `AR101A_NxtrIntrpn_Design/Doc/NxtrIntrpn FDD.docx` (Design / Integration Document; original DOCX, about 302 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to AR101A_NxtrIntrpn_Design](./)

*Conversion method: automatic text extraction from the Word document.*

Functional Design Document

For

NxtrIntrpn

VERSION: 1.0

DATE: 20-Feb-2015

Prepared By: 

Nexteer Automotive,

 Saginaw, MI, USA

Revision History

Table of Contents

1	Abbrevations And Acronyms	4

2	References	5

3	Purpose	6

4	Interpolation Design	7

4.1	Linear Interpolation	7

4.1.1	Linear Interpoliation Accuracy	8

4.2	Fixed X-Axis Linear Interpolation Functions	9

4.2.1	API	9

4.2.1.1	Truncating Functions	9

4.2.1.2	Rounding Functions	9

4.3	Variable X-Axis Linear Interpolation Functions	10

4.3.1	API	10

4.3.1.1	Truncating Functions	10

4.3.1.2	Rounding Functions	12

4.4	Bilinear Interpolation	14

4.4.1	Common X Axis Bilinear Interpolation Functions	16

4.4.1.1	API	16

4.4.2	Variable X Axis Bilinear Interpolation Functions	19

4.4.2.1	API	19

5	Know Limitations With Design	22

6	Appendix A	23

7	Appendix B	24

7.1	Truncating Linear Interpolation Functions	24

7.1.1	Fixed X-Axis Interpolation Function	24

7.1.2	Variable X-Axis Interpolation Function	24

7.2	Rounding Linear Interpolation Functions	24

7.2.1	Fixed X-Axis Interpolation Function	24

7.2.2	Variable X-Axis Interpolation Function	24

8	Appendix C	25

Abbrevations And Acronyms

References

This section lists the title & version of all the documents that are referred for development of this document

Purpose

The purpose of this document is to describe the functions contained within the Nexteer interpolation library and as an API reference in designing functional requirements, models, and software components. 

Interpolation Design

Linear Interpolation

Linear interpolation is used to determine an output value between a set of known data points for a given input. In the image below, the input point (x) is between the known points (x0,y0) and (x1,y1). 

The linear interpolant is defined as the straight line between the two known points (x0,y0) and (x1,y1) and is defined in equation (1). 

Solving equation (1) for the desired output (y) is described below in equation (2).

If the delta between neighboring points on the X-axis is the same, equation (2) can be modified with that delta as shown in equation (3). 

Linear Interpoliation Accuracy

The operations required to perform equations (2) and (3) shall be implemented using fixed point math. This is to save on execution time to perform the interpolation compared to using floating point math functions (See Appendix C). This also means that there can be information loss because the operations can produce results that have more bits than the operands. In order to keep the same number of bits as the operands, the answer must be rounded or truncated. 

The interpolation library shall support both truncation and rounding methods in all linear interpolation functions. These methods are described in Appendix B. The error produced by the truncated function results can be +/- one count. Depending on the resolution of the calibration and the resolution required by the design, this may be negligible. The function designer shall use the truncation library functions in all cases where this error is acceptable in order to save on execution time. 

Fixed X-Axis Linear Interpolation Functions

The following functions are available for linear interpolation with a fixed X-axis and are based on equation (3). The table below defines each argument used in the API. Note that some functions require and/or return unsigned or signed values. It is up to the designer to pick the proper interpolation function for their design. 

API

The input and output variables are defined as uint16 or sint16 for purposes of min and max ranges. However, calibrations with different resolutions, for example u8p8, can be used because they are still represented as a 16-bit value within these functions. 

Truncating Functions

Rounding Functions

Variable X-Axis Linear Interpolation Functions

The following functions are available for linear interpolation with a variable X-axis and are based on equation (2). The table below defines each argument used in the API. Note that some functions require and/or return unsigned or signed values. It is up to the designer to pick the proper interpolation function for their design. 

API

The input and output variables are defined as uint16 or sint16 for purposes of min and max ranges. However, calibrations with different resolutions, for example u8p8, can be used because they are still represented as a 16-bit value within these functions.

Truncating Functions

Rounding Functions

Bilinear Interpolation

Bilinear interpolation is linear interpolation with expanded coverage into three dimensions. To calculate the result, three linear interpolations are required to be performed.  

The first two interpolations are between the two data sets (shown in red and green in the image) and are described with the equations (4) and (5). 

Equations (4) and (5) provide the endpoints for the interpolant between the two sets of data. The third interpolation determines how close the desired output is to each of the data sets. This is described in equation (6).

Since divisions are throughput intensive operations, equation (6) is not efficient for an embedded environment because it contains three division steps when substitutions are made for Y1 and Y2. However, the terms can be rearranged to reduce the amount of divisions for additional multiplications and additions, which typically are much less in throughput consumption. Staring with equations (4) and (5), the terms can be reordered into equations (7) and (8). 

Equations (7) and (8) can be substituted back in equation (6) and the simplified result is shown in equation (9). 

Finally, the numerator in equation (9) can also be rearranged and split into multiple terms. The steps taken between equations (9) and (10) are provided in Appendix A. The final equation, requiring only one division step, is shown in equation (10).

Common X Axis Bilinear Interpolation Functions

The following functions are available for bilinear interpolation with a common X-axis and are based on equation (10). The table below defines each argument used in the API. Note that some functions require and/or return unsigned or signed values. It is up to the designer to pick the proper interpolation function for their design.

API

The input and output variables are defined as uint16 or sint16 for purposes of min and max ranges. However, calibrations with different resolutions, for example u8p8, can be used because they are still represented as a 16-bit value within these functions.

Variable X Axis Bilinear Interpolation Functions

The following functions are available for bilinear interpolation with a variable X-axis and are based on equation (10). The table below defines each argument used in the API. Note that some functions require and/or return unsigned or signed values. It is up to the designer to pick the proper interpolation function for their design.

API

The input and output variables are defined as uint16 or sint16 for purposes of min and max rang

Version | Description | Author | Section Modified | Date | Approved By
1.0 | Initial Version | K. Smith | All | 20-Feb-2015 | Nexteer
Abbreviation | Description
BS | Bilinear Selection
API | Application Program Interface
Sr. No. | Title | Version
Appendix C | RH850/P1x Series User’s Manual: Software | 0.10 Jan, 2014
 |  | (1)
