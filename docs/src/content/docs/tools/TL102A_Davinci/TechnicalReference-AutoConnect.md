---
title: "DaVinci Configuration Support — TechnicalReference AutoConnect"
description: "Converted Technical Reference (vendor) from TechnicalReference_AutoConnect.pdf (PDF, 442 KB)."
---

:::note
Converted from `TL102A_Davinci/tools/Developer/Docs/TechnicalReference_AutoConnect.pdf` (Technical Reference (vendor); original PDF, about 442 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL102A_Davinci](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Auto-Connect Port Prototypes 
Technical Reference 
 
  
Version 1.0 
 
 
 
 
 
 
 
 
 
 
Authors Pavol Gramblicka 
Status Released

--- Page 2 ---
Technical Reference Auto-Connect Port Prototypes 
2015, Vector Informatik GmbH Version: 1.0 
based on template version 5.2.0 
2 / 13 
Document Information 
History 
Author Date Version Remarks 
Pavol Gramblicka 2015-04-28 0.1.0 Initial version 
Pavol Gramblicka 2015-04-28 1.0.0 Final version

--- Page 3 ---
Technical Reference Auto-Connect Port Prototypes 
2015, Vector Informatik GmbH Version: 1.0 
based on template version 5.2.0 
3 / 13 
Contents 
1 Overview ................................ ................................ ................................ ....................... 5 
1.1 Intended Audience ................................ ................................ ............................. 5 
1.2 Terms and Acronyms ................................ ................................ ......................... 5 
2 Input Port Prototypes ................................ ................................ ................................ ... 6 
3 Auto-Connect ................................ ................................ ................................ ................ 7 
3.1 Auto-Connect – simple pattern ................................ ................................ ........... 7 
3.2 Auto-Connect – enhanced patterns ................................ ................................ .... 9 
3.2.1 Prefix, Postfix ................................ ................................ ..................... 9 
3.2.2 Complex patterns using the component prototype name .................. 10 
4 Contact ................................ ................................ ................................ ........................ 13

--- Page 4 ---
Technical Reference Auto-Connect Port Prototypes 
2015, Vector Informatik GmbH Version: 1.0 
based on template version 5.2.0 
4 / 13 
Illustrations 
Figure 2-1 Start the contextless auto-connecting ................................ ......................... 6 
Figure 2-2 Start the context dependent auto-connecting ................................ .............. 6 
Figure 3-1 Simple auto-connect scenario ................................ ................................ ..... 7 
Figure 3-2 List of proposed connections ................................ ................................ ...... 8 
Figure 3-3 Context dependent auto-connecting of a prefixed port prototype ................ 9 
Figure 3-4 Context dependent auto-connecting with a prefixed naming  pattern ........ 10 
Figure 3-5 Context dependent auto-connecting of a port prototype without the 
component restriction ................................ ................................ ............... 11 
Figure 3-6 Context dependent auto-connecting of port prototypes with the 
component restriction ................................ ................................ ............... 12 
 
Tables 
Table 1-1  Terms and Acronyms ................................ ................................ .................. 5

--- Page 5 ---
Technical Reference Auto-Connect Port Prototypes 
2015, Vector Informatik GmbH Version: 1.0 
based on template version 5.2.0 
5 / 13 
1 Overview 
DaVinci Developer is part of Vector’s solution for AUTOSAR compatible software design. It 
is used to design and configure software components and provides various concepts to 
support this process. 
This document describes a part of the design process related to DaVinci Developer from a 
technical point of view, trying to give the user a better understanding of the internal 
processes and how the tool reacts in different situations. 
1.1  Intended Audience 
This document aims at developers who are involved in the AUTOSAR design process and 
use DaVinci Developer to integrate various software components. 
1.2 Terms and Acronyms 
Term Definition 
DEV DaVinci Developer 
Table 1-1  Terms and Acronyms

--- Page 6 ---
Technical Reference Auto-Connect Port Prototypes 
2015, Vector Informatik GmbH Version: 1.0 
based on template version 5.2.0 
6 / 13 
2 Input Port Prototypes 
The auto -connect functionality may b e started contextless from the Software Design  
toolbar (Figure 2-1) or from the context menu of the graphic view (Figure 2-2). 
 
Figure 2-1 Start the contextless auto-connecting 
 
Figure 2-2 Start the context dependent auto-connecting 
1. In case of the contextless connecting, all port prototypes of the parent composition are 
considered. 
2. In case of the context dependent connecting, the connections are created according to 
the provided selection. 
> no selection – all port prototypes within the composition are considered 
> a component is selected – all port prototypes of the component are considered 
> single port prototype selection – only these port prototypes are considered to 
be the source resp. destination of a proposed connector prototype

[… 7 further page(s) not extracted …]
