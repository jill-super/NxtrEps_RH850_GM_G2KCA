---
title: "Watchdog Manager — S-WdgM SafetyManual"
description: "Converted Safety Manual / Safety Case from S-WdgM_SafetyManual.pdf (PDF, 3764 KB)."
---

:::note
Converted from `WdgM/doc/S-WdgM_SafetyManual.pdf` (Safety Manual / Safety Case; original PDF, about 3764 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to WdgM](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
TTTech Automotive GmbH 
Schoenbrunner Str. 7, A-1040 Vienna, Austria, Tel. + 43 1 585 34 34-0, Fax +43 1 585 34 34-90, office@tttech-automotive.com 
 
No part of the document may be reproduced or transmitted in any form or by an y means, electronic or mechanical, for any purpose, without the written permission of TTTech 
Automotive GmbH. Company or product names mentioned in this document may be trademarks or registered trademarks of their resp ective companies. TTTech Automotive Gm bH 
undertakes no further obligation in relation to this document. 
 
© 2014, TTTech Automotive GmbH. All rights reserved.                                                                                                                                                Subject to changes and corrections 
TTTech Automotive GmbH Confidential and Proprietary Information 
 
Ensuring Reliable Networks 
Safe Watchdog Manager  
Safety Manual 
  
Author: TTTech Automotive GmbH 
Security: Company Confidential 
Document number: D-SAFEX-S-70-001 
Version: 2.3.28 
Date: 26.05.2014 
Status: ALM_Published 
MKS ID: 228403

--- Page 2 ---
Project Name: Safe Watchdog Manager Version: 2.3.28  
Doc. Name: Safety Manual Doc. No: D-SAFEX-S-70-001 Page 1 
Date: 26.05.2014 Author: TTTech Automotive GmbH © TTTech  Automotive GmbH 
TTTech  Automotive GmbH Confidential and Proprietary Information 
Ensuring Reliable Networks 
Revision History 
17.06.2011 V0.9.4 Draft 
15.07.2011 V1.0.0 Safe Watchdog Manager Series Release 
12.08.2011 V1.1.0 Safe Watchdog Manager Series Release 
07.09.2011 V1.2.0 Safe Watchdog Manager Series Release 
16.09.2011 V1.3.0 Safe Watchdog Manager Series Release 
16.11.2011 V1.3.1 Safe Watchdog Manager - separating S-Wdg drivers 
13.12.2011 V1.4.0 Safe Watchdog Manager - Series Release 
10.02.2012 V1.5.0 Safe Watchdog Manager - Series Release 
17.02.2012 V1.5.1 Safe Watchdog Manager - Series Release (Patch Release) 
09.03.2012 V1.6.0 Safe Watchdog Manager - Series Release 
13.04.2012 V1.7.0 Safe Watchdog Manager - Series Release 
08.05.2012 V1.7.1 Safe Watchdog Manager 
05.05.2012 V2.0.0 Copied from MKS 64019 to MKS 228043. Hierarchie restructured. Labeled for review.  
24.05.2012 V2.0.1 Labeled for review. 
25.05.2012 V2.0.2 Safe Watchdog Manager - Series Release V1.8.0 
27.06.2012 V2.1.0 Reviewed. Some information still open 
03.07.2012 V2.2.0 Added config generation and verification process 
03.07.2012 V2.2.1 Added timing constraints (issue47259) 
05.07.2012 V2.3.0 Added requirements from ETA and Check against System Specification  
06.07.2012 V2.3.1 Ready for Release 1.8.2 
07.08.2012 V2.3.2 Feedback from Hella-Audit, some texts more precise 
23.08.2012 V2.3.3 added system assumptions, S-WdgM requ., AUTOSAR 3.1 info, manual checks 
10.09.2012 V2.3.4 Traced requirements from ETA. Dissolved section "Requirements derived from ETA 
process" 
13.09.2012 V2.3.5 After walkthrough review 
13.09.2012 V2.3.6 Added manual tests 
15.09.2012 V2.3.7 Safe Watchdog Manager ASIL Release 
15.10.2012 V2.3.8 Added system assumption regarding critical sections (297946,297948), issue49890  
Added reentrancy, issue49459 (WDGM_E_REENTRANCY) 
05.12.2012 V2.3.9   228523 - Added Safety Manager 
313849 - Added the 'Safety related requirement' behavior 
315317, 315319 - Additional requirements (Safe Execution, Lock Step) 
230020 - Relation to the SEooC 
14.01.2013 V2.3.10 324187, XSLT processor, issue51325 
239057, 239065, 239067 corrected 
313849 'S-Wdg' corrected to 'S-WdgM' 
24.04.2013 V2.3.11 issue 53646: 358190 - Alive counter necessary 
07.11.2013 V2.3.12 In the item 230126 the missing ISO 'part 6' was added.  
02.04.2014 V2.3.13 Issue 59785 (partly): After discussion with customer following comments added: 542988, 
544495 
Issue 58655: 228813, 228815, 260615, 260617 (Win7 test) 
Issue 52760, 62290, 61812, 59931 
05.05.2014 V2.3.14 Changed points according EEB remarks, issue 52087  
05.05.2014 V2.3.15 Improvements base is the customer OIL list, issue 59785 
07.05.2014 V2.3.16 Issue 52087, 52760, 59785 : review points corrected 
13.05.2014 V2.3.17 Issue 52087, 52760 corrected 
14.05.2014 V2.3.18 Issue 59785 corrected 
14.05.2014 V2.3.19 Issue 62591 corrected 
14.05.2014 V2.3.20 Issue 62589 corrected

--- Page 3 ---
Project Name: Safe Watchdog Manager Version: 2.3.28  
Doc. Name: Safety Manual Doc. No: D-SAFEX-S-70-001 Page 2 
Date: 26.05.2014 Author: TTTech Automotive GmbH © TTTech  Automotive GmbH 
TTTech  Automotive GmbH Confidential and Proprietary Information 
Ensuring Reliable Networks 
15.05.2014 V2.3.21 Issue 62290 corrected 
15.05.2014 V2.3.22 Issue 53646 corrected 
15.05.2014 V2.3.23 Issue 62290 corrected 
15.05.2014 V2.3.24 Issue 59785, 62589, 62591corrected 
16.05.2014 V2.3.25 Issue 62724 corrected 
22.05.2014 V2.3.26 Issue 63131: Language Review 
23.05.2014 V2.3.27 Issue 62724 corrected 
26.05.2014 V2.3.28 Issues corrected:52168, 62591, 53646, 50833, 58842

--- Page 4 ---
Project Name: Safe Watchdog Manager Version: 2.3.28  
Doc. Name: Safety Manual Doc. No: D-SAFEX-S-70-001 Page 3 
Date: 26.05.2014 Author: TTTech Automotive GmbH © TTTech  Automotive GmbH 
TTTech  Automotive GmbH Confidential and Proprietary Information 
Ensuring Reliable Networks 
Table of Contents 
1 Purpose of this Document ........................................................................................................................... 7 
2 Introduction .................................................................................................................................................. 8 
2.1 Target Audience and Responsibilities ................................................................................................. 8 
2.2 Structure of this Document .................................................................................................................. 8 
3 Terms ........................................................................................................................................................ 10 
4 Notations ................................................................................................................................................... 13 
5 Abbreviations ............................................................................................................................................. 14 
6 Safe Watchdog Manager Overview ........................................................................................................... 15 
7 System Assumptions ................................................................................................................................. 16 
7.1 Assumptions in this Document .......................................................................................................... 19 
8 S-WdgM Function Requirements .............................................................................................................. 20 
9 S-WdgM Configuration .............................................................................................................................. 21 
9.1 Configuration Check-List ................................................................................................................... 21 
9.1.1 General Requirements ............................................................................................................... 21 
9.1.2 Pre-Compile Settings ................................................................................................................. 22 
9.1.3 Post Build Configuration and Application Settings .................................................................... 24 
9.1.3.1 Alive Monitoring ................................................................................................................... 26 
9.1.3.2 Deadline Monitoring ............................................................................................................. 27 
9.1.3.3 Program Flow Monitoring ..................................................................................................... 27 
9.1.3.4 Configuration Restrictions for S-WdgM AUTOSAR 3.1 Compatibility Mode ....................... 27 
9.1.4 S-WdgM Fault Detection Time and S-WdgM Fault Reaction Time Evaluation ......................... 28 
9.1.4.1 S-WdgM Fault Detection Time ............................................................................................. 28 
9.1.4.1.1 Alive Supervision ............................................................................................................. 29 
9.1.4.1.2 Deadline Supervision ...................................................................................................... 29 
9.1.4.1.3 Program Flow Supervision .............................................................................................. 30 
9.1.4.2 S-WdgM Fault Reaction Time .....................................................................

--- Page 5 ---
Project Name: Safe Watchdog Manager Ver

[… 89 further page(s) not extracted …]
