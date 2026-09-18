---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — TechnicalReference SipModificationChecker"
description: "Converted Technical Reference (vendor) from TechnicalReference_SipModificationChecker.pdf (PDF, 436 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/TechnicalReferences/TechnicalReference_SipModificationChecker.pdf` (Technical Reference (vendor); original PDF, about 436 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
SIP Modification Checker 
Technical Reference 
 
 
Version 1.00.00 
 
 
 
 
 
 
 
 
 
 
 
Authors Markus Schwarz 
Status Released

--- Page 2 ---
Technical Reference SIP Modification Checker 
2014, Vector Informatik GmbH Version: 1.00.00 
based on template version 5.7.1 
2 / 11 
Document Information 
History 
Author Date Version Remarks 
Markus Schwarz 2014-05-07 1.00.00 Initial version 
    
Reference Documents 
No. Source Title Version 
[1]     
Scope of the Document  
This technical reference describes the general use of the tool SipModificationChecker.

--- Page 3 ---
Technical Reference SIP Modification Checker 
2014, Vector Informatik GmbH Version: 1.00.00 
based on template version 5.7.1 
3 / 11 
Contents 
1 Component History ................................ ................................ ................................ ...... 5 
2 Introduction................................ ................................ ................................ ................... 6 
2.1 Overview ................................ ................................ ................................ ............ 6 
2.2 Background ................................ ................................ ................................ ........ 6 
2.3 Workflow ................................ ................................ ................................ ............ 7 
2.3.1 At Vector ................................ ................................ ............................ 7 
2.3.2 At Tier1/OEM ................................ ................................ ..................... 7 
3 Functional Description ................................ ................................ ................................ . 8 
3.1 Command Line Usage ................................ ................................ ....................... 8 
3.1.1 Console Output ................................ ................................ .................. 8 
3.1.2 Return Error Codes ................................ ................................ ............ 8 
3.1.3 Report Creation ................................ ................................ .................. 9 
3.2 Integration ................................ ................................ ................................ .......... 9 
4 Glossary and Abbreviations ................................ ................................ ...................... 10 
4.1 Glossary ................................ ................................ ................................ .......... 10 
4.2 Abbreviations ................................ ................................ ................................ ... 10 
5 Contact ................................ ................................ ................................ ........................ 11

--- Page 4 ---
Technical Reference SIP Modification Checker 
2014, Vector Informatik GmbH Version: 1.00.00 
based on template version 5.7.1 
4 / 11 
Illustrations 
Figure 2-1 Workflow at Vector ................................ ................................ ...................... 7 
Figure 2-2 Workflow at Tier1/OEM ................................ ................................ ............... 7 
 
Tables 
Table 1-1  Component history................................ ................................ ...................... 5 
Table 3-1  Command Line ErrorCodes ................................ ................................ ........ 8 
Table 7-1  Glossary ................................ ................................ ................................ ... 10 
Table 7-2  Abbreviations ................................ ................................ ............................ 10

--- Page 5 ---
Technical Reference SIP Modification Checker 
2014, Vector Informatik GmbH Version: 1.00.00 
based on template version 5.7.1 
5 / 11 
1 Component History 
The component history gives an overview over the important milestones that are 
supported in the different versions of the component.  
Component Version New Features 
1.00.00  Initial Version 
  
Table 1-1  Component history

--- Page 6 ---
Technical Reference SIP Modification Checker 
2014, Vector Informatik GmbH Version: 1.00.00 
based on template version 5.7.1 
6 / 11 
2 Introduction 
This document describes the functionality of the tool SipModifcationChecker. 
2.1 Overview 
The SipModifcationChecker is a tool that supports the Tier1 and OEM to determine if and 
where the (source code) files delivered from Vector were unintentionally changed.  
The SipModifcationChecker  
> is a command line based tool. 
> checks sources below a user-selectable root directory against information given in a 
reference file. 
> checks if and which of the relevant delivered files are contained below that directory. 
> checks if and which files have been modified. 
> reports the “modification state” as ERRORLEVEL and within a HTML report. 
2.2 Background 
This tool aims to find changes that were unintendedly introduced by the customer in the 
delivered Vector source code.

[… 5 further page(s) not extracted …]
