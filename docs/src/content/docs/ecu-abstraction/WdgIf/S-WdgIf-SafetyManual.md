---
title: "Watchdog Interface — S-WdgIf SafetyManual"
description: "Converted Safety Manual / Safety Case from S-WdgIf_SafetyManual.pdf (PDF, 1794 KB)."
---

:::note
Converted from `WdgIf/doc/S-WdgIf_SafetyManual.pdf` (Safety Manual / Safety Case; original PDF, about 1794 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to WdgIf](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
TTTech Automotive GmbH 
Schoenbrunner Str. 7, A-1040 Vienna, Austria, Tel. + 43 1 585 34 34-0, Fax +43 1 585 34 34-90, office@tttech-automotive.com 
 
No part of the document may be reproduced or transmitted in any form or by any means, electronic or mechanical, for any purpo se, without the written permission of TTTech 
Automotive GmbH. Company or product names mentioned in  this document may be trademarks or registered trademarks of their respective companies. TTTech Automotive GmbH 
undertakes no further obligation in relation to this document. 
 
© 2014, TTTech Automotive GmbH. All rights reserved.                                                                                                                                                Subject to changes and corrections 
TTTech Automotive GmbH Confidential and Proprietary Information 
 
Ensuring Reliable Networks 
Safe Watchdog Interface 
Safety Manual 
  
Author: TTTech Automotive GmbH 
Security: Company Confidential 
Document number: D-SAFEX-S-70-005 
Version: 1.8.9 
Date: 22.05.2014 
Status: ALM_Published 
MKS ID: 232906

--- Page 2 ---
Project Name: Safe Watchdog Interface Version: 1.8.9  
Doc. Name: Safety Manual Doc. No: D-SAFEX-S-70-005 Page 1 
Date: 26.05.2014 Author: TTTech Automotive GmbH © TTTech  Automotive GmbH 
TTTech  Automotive GmbH Confidential and Proprietary Information 
Ensuring Reliable Networks 
Revision History 
30.05.2012 V1.0.0 Creation (based on MKS 185841) 
27.06.2012 V1.1.0 Reviewed. Some information still open. 
03.07.2012 V1.2.0 Added config generation and verification process 
05.07.2012 V1.3.0 Added requirements from ETA and Check against System Spec ification 
06.07.2012 V1.3.1 Ready for Release 1.8.2 
13.08.2012 V1.3.2 Feedback from Hella-Audit, some texts more precise 
10.09.2012 V1.3.3 Added chapter "S-WdgIf Generator - Verification". 
13.09.2012 V1.3.4 Dissolved ETA section. Corrected review findings. 
15.09.2012 V1.3.5 Safe Watchdog Interface ASIL Release 
17.09.2012 V1.8.1 issue48784 (new version) 
06.11.2012 V1.8.2 updated according to WdgIf_GetTickCounter() (issue49948)  
07.11.2012 V1.8.3 updated after review (issue49948) 
03.04.2014 V1.8.4 Update after customer review, changes summarised in the issue52277 
24.04.2014 V1.8.5 Updated parts related to AS driver compatibility (issue62032:msg467581, issue59785)  
Updated 240758: parameter WdgIfUseAutosarDrvApi 
Updated 260205: added vendor ID (WD driver function names) 
Added 555654: parameter WDGIF_USE_AUTOSAR_DRV_API 
Updated 289398: API differences (WDGIF_USE_AUTOSAR_DRV_API) 
Updated 234584, 235159, 283153: API compatibility 
(WDGIF_USE_AUTOSAR_DRV_API) 
Added 556326, changed 289394, 289398, 289412, 289455: Description of the <drv> 
shortcut 
Changed 233039, 234584, 235159, 283153: added vendor-id string 
08.05.2014 V1.8.6 Updated according to the review remarks (issue62032:msg469458, 
issue62032:msg469460) 
12.05.2014 V1.8.7 Updated according to the review remarks (issue62032:msg472152) 
14.05.2014 V1.8.8 Updated according to the review remarks (issue62032:msg473209)  
22.05.2014 V1.8.9 Language Review (issue63157)

--- Page 3 ---
Project Name: Safe Watchdog Interface Version: 1.8.9  
Doc. Name: Safety Manual Doc. No: D-SAFEX-S-70-005 Page 2 
Date: 26.05.2014 Author: TTTech Automotive GmbH © TTTech  Automotive GmbH 
TTTech  Automotive GmbH Confidential and Proprietary Information 
Ensuring Reliable Networks 
Table of Contents 
1 Introduction .................................................................................................................................................. 6 
1.1 Purpose of this Document ................................................................................................................... 6 
1.1.1 Target Audience and Responsibilities ......................................................................................... 6 
1.1.2 Structure of this Document .......................................................................................................... 7 
2 Terms .......................................................................................................................................................... 9 
3 Notations ................................................................................................................................................... 10 
4 Abbreviations ............................................................................................................................................. 11 
5 Safe Watchdog Interface Overview ........................................................................................................... 12 
6 System Assumptions ................................................................................................................................. 13 
6.1 Assumptions in this Document .......................................................................................................... 13 
7 S-WdgIf Function Requirements ............................................................................................................... 14 
8 S-WdgIf Configuration ............................................................................................................................... 15 
8.1 Configuration Check-List ................................................................................................................... 15 
8.1.1 General Requirements ............................................................................................................... 15 
8.1.2 Compiler Settings ....................................................................................................................... 16 
8.1.3 Post Build Configuration and Application Settings .................................................................... 16 
9 S-WdgIf Configuration Generator .............................................................................................................. 18 
9.1 S-WdgIf Generator - Installation ........................................................................................................ 18 
9.2 S-WdgIf Generator - Application ....................................................................................................... 18 
9.3 S-WdgIf Generator - Verification ....................................................................................................... 19 
9.3.1 Check of WdgIf_Cfg_Features.h ............................................................................................... 19 
9.3.2 Check of WdgIf_Lcfg.h ............................................................................................................... 20 
9.3.3 Check of WdgIf_Lcfg.c ............................................................................................................... 20 
10 Safe Watchdog Interface ........................................................................................................................... 23 
10.1 API Specification..............................................................................................................

--- Page 4 ---
Project Name: Safe Watchdog Interface Version: 1.8.9  
Doc. Name: Safety Manual Doc. No: D-SAFEX-S-70-005 Page 3 
Date: 26.05.2014 Author: TTTech Automotive GmbH © TTTech  Automotive GmbH 
TTTech  Automotive GmbH Confidential and Proprietary Information 
Ensuring Reliable Networks

--- Page 5 ---
Project Name: Safe Watchdog Interface Version: 1.8.9  
Doc. Name: Safety Manual Doc. No: D-SAFEX-S-70-005 Page 4 
Date: 26.05.2014 Author: TTTech Automotive GmbH © TTTech  Automotive GmbH 
TTTech  Automotive GmbH Confidential and Proprietary Information 
Ensuring Reliable Networks 
- 
Category: Comment Keywords:  ID: 552152 
LEGAL DISCLAIMER 
THE INFORMATION GIVEN IN THIS SAFETY MANUAL IS GIVEN AS SUPPORT FOR THE 
INTEGRATION OF THE TTTECH SAFETY MODULE INTO A SYSTEM ONLY AND SHALL NOT BE 
REGARDED AS ANY DESCRIPTION OR WARRANTY OF A CERTAIN FUNCTIONALITY, CONDITION 
OR QUALITY OF THE TTTECH SAFETY MODULE. THE RECIPIENT OF THIS SAFETY MANUAL MUST 
VERIFY ANY FUNCTION DESCRIBED HEREIN IN THE REAL APPLICATION.  
 
TTTECH PROVIDES THE SAFETY MANUAL FOR THE SAFETY MODULE "AS IS" AND WITH ALL 
FAULTS AND HEREBY DISCLAIMS ALL WARRANTIES OF ANY KIND, EITHER EXPRESSED OR 
IMPLIED, INCLUDING BUT NOT LIMITED TO THE IMPLIED WARRANTIES OF MERCHANTABILITY 
AND FITNESS FOR A PARTICULAR PURPOSE, ACCURACY OR COMPLETENESS, OR OF RESULTS 
TO THE EXTENT PERMITTED BY APPLICABLE LAW. THE ENTIRE RISK, AS TO THE QUALITY, USE 
OR PERFORMANCE OF THE SAFETY MANUAL, REMAINS WITH THE RECIPIENT. TO THE MAXIMUM 
EXTENT PERMITTED BY APPLICABLE LAW TTTECH SHALL IN NO EVENT BE LIABLE FOR ANY 
SPECIAL, INCIDENTAL, INDIRECT OR CONSEQUENTIAL DAMAGES WHATSOEVER (INCLUDING BUT 
NOT LIMITED TO LOSS OF DATA, DATA BEING RENDERED INACCURATE, BUSINESS 
INTERRUPTION OR ANY OTHER PECUNIARY OR OTHER LOSS WHATSOEVER) ARISING OUT OF 
THE USE OR INABILITY 

[… 42 further page(s) not extracted …]
