---
title: "Watchdog Manager — S-WdgM ReleaseNotes"
description: "Converted Release Notes from S-WdgM_ReleaseNotes.pdf (PDF, 457 KB)."
---

:::note
Converted from `WdgM/doc/S-WdgM_ReleaseNotes.pdf` (Release Notes; original PDF, about 457 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to WdgM](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
TTTech Automotive GmbH 
Schoenbrunner Str. 7, A-1040 Vienna, Austria, Tel. + 43 1 585 34 34-0, Fax +43 1 585 34 34-90, office@tttech-automotive.com 
No part of the document may be reproduced or transmitted in any from or by any means, electronic or mechanical, for any purpose, without the written permission of TTTech 
Automotive. Company or product names mentioned in this document may be trademarks or registered trademarks of their respective companies. TTTech Automotive undertakes no 
further obligation in relation to this document. 
Copyright © 2009, TTTech Automotive GmbH. All rights reserved.                                                                                                                                Subject to change and corrections 
Ensuring Reliable Networks 
 
Safe Watchdog Manager 
Release Notes 
  
Author: TTTech 
Security: Confidential 
Document number: D-SAFEX-RP-70-012 
Document Version: 3.4.6 
Date: 21.11.2014 
Status: released 
Review: JDU

--- Page 2 ---
2 
Project Name: Safe Watchdog Manager Version: 3.4.6 
Document Title: Release Notes Doc.No:  D-SAFEX-RP-70-012 Page 
Date:  21.11.2014 
Version:  3.4.6 
File name: S-WdgM_ReleaseNotes.doc 
Author: TTTech 
© TTTech-Automotive GmbH 
Ensuring Reliable Networks 
Approval 
Name  Function Signature 
PPU Project Manager  
TGA Head of Software Department  
MAL Quality Manager  
 
 
 
Revision Chart 
A revision is a new edition of the document and affects all sections of this document.  
 
Document 
Version  
Date Responsible Person Modification 
0.9.0 09.06.2011 PPU Version for Series Release 0.9 
0.9.1 17.06.2011 PPU Integration with DaVinci tool chain. 
1.0.0 15.07.2011 PPU Integration with DaVinci tool chain.  
1.1.0 19.08.2011 PPU Version for Series Release 1.1 
1.2.0 07.09.2011 PPU Version 1.2.0, TMP570LS3xx related release 
1.3.0 16.09.2011 PPU Version 1.3.0, MPC56xx (MPC5604B) release 
1.3.1 06.12.2011 PPU Version 1.3.1, Wdg_MPC56xx_bswmd.arxml 
changed only 
1.4.0 14.12.2011 PPU New software release and d ocument split. Watchdog 
Manager, Interface and Dri ver becomes own 
Release documents. 
1.5.0 10.02.2012 PPU Version 1.5.0 
1.6.0 08.03.2012 PPU Release 1.6.0 
1.7.0 13.04.2012 PPU Release 1.7.0 
1.8.0 21.11.2014 PPU Release 1.8.0 
1.8.1 12.06.2012 PPU Release 1.8.1 did  not contain WdgM  module. It 
contains the MPC56xx driver only. 
1.8.2 13.07.2012 PPU Release 1.8.2, BugFixes, Manager release only

--- Page 3 ---
3 
Project Name: Safe Watchdog Manager Version: 3.4.6 
Document Title: Release Notes Doc.No:  D-SAFEX-RP-70-012 Page 
Date:  21.11.2014 
Version:  3.4.6 
File name: S-WdgM_ReleaseNotes.doc 
Author: TTTech 
© TTTech-Automotive GmbH 
Ensuring Reliable Networks 
1.9.0 07.09.2012 PPU Release 1.9.0, Code only 
1.9.1 15.09.2012 PPU Release 1.9.1, Documentation only 
1.9.2 21.09.2012 PPU Release 1.9.2, Style sheet update 
1.9.3 02.10.2012 PPU Release 1.9.3, S-WdgM Verifier - update,  
S-WdgM_UserManual  - document update 
S-WdgM_Stack_SafetyCase - document new 
2.0.7 25.10.2012 PPU Test release  2.0.7 to check the delivery structure. 
This is NOT a customer release!  
3.0.3 16.11.2012 PPU Cumulative module update. 
(The major version changed to 3  because of the API 
change in function  (WdgIf_GetTickCounter()) 
3.1.0 11.01.2013 PPU Release 1.11.0, embedded code not changed 
3.1.1 27.02.2013 PPU Release 1.13.0, Verifier update only 
3.2.0 05.04.2013 JDU Release 1.14.0, generator update only 
3.3.2 29.11.2013 PPU Release 1.21.0, generator only 
3.4.0 19.02.2014 PPU Autosar 4 update and bug fixes, beta version 
3.4.1 21.03.2014 PPU Update and bug fix es for Autosar 4 environment 
compatibility. Backward compatibility to Autosar 3.1 
environment added too. 
3.4.2 10.04.2014 PPU Generator bug fix for Autosar compatible driver 
3.4.3 27.05.2014 PPU Release for the AUTOSAR 4.0 and AUTOSAR 3.1 
compatible S-WdgM module 
3.4.4 14.08.2014 PPU Safety Case document for previous version 3.4.3 
released only. 
3.4.5 04.11.2014 PPU S-WdgM Generator correction only 
3.4.6 21.11.2014 PPU S-WdgM Generator correction only

--- Page 4 ---
4 
Project Name: Safe Watchdog Manager Version: 3.4.6 
Document Title: Release Notes Doc.No:  D-SAFEX-RP-70-012 Page 
Date:  21.11.2014 
Version:  3.4.6 
File name: S-WdgM_ReleaseNotes.doc 
Author: TTTech 
© TTTech-Automotive GmbH 
Ensuring Reliable Networks 
Contents 
1 Overview .................................................................................................................................................. 6 
2 Content of the Module Release ............................................................................................................. 7 
3 Change history ........................................................................................................................................ 9 
3.1 Changes with version 3.4.6 .............................................................................................................. 9 
3.2 Changes with version 3.4.5 .............................................................................................................. 9 
3.3 Changes with version 3.4.4 ............................................................................................................ 10 
3.4 Changes with version 3.4.3 ............................................................................................................ 10 
3.5 Changes with version 3.4.2 ............................................................................................................ 10 
3.6 Changes with version 3.4.1 ............................................................................................................ 11 
3.7 Changes with version 3.4.0 ............................................................................................................ 11 
3.8 Changes with version 3.3.2 ............................................................................................................ 11 
3.9 Changes with version 3.2.0 ............................................................................................................ 11 
3.10 Changes with version 3.1.2 ............................................................................................................ 13 
3.11 Changes with version 3.1.1 ............................................................................................................ 13 
3.12 Changes with version 3.1.0 ............................................................................................................ 13 
3.13 Changes with version 3.0.3 ............................................................................................................ 14 
3.14 Changes with version 2.0.7 ............................................................................................................ 15 
3.15 Changes with TTTech Release 1.9.3: S-WdgM Subpackage 2.0.6 .............................................. 15 
3.16 Changes with TTTech Release 1.9.2: S-WdgM Subpackage 2.0.5 .............................................. 16 
3.17 Changes with Release 1.9.1: S-WdgM Subpackage 2.0.4 ............................................................ 17 
3.18 Changes with Release 1.9.0: S-WdgM Subpackage 2.0.3 ............................................................ 17 
3.19 Changes with Release 1.8.2: S-WdgM Subpackage 1.8.2 ............................................................ 20 
3.20 Changes with Release 1.8.0: S-WdgM Subpackage 1.8.0 ............................................................ 20 
3.21 Changes with Release 1.7.0: S-WdgM Subpackage 1.7.0 ............................................................ 20 
3.22 Changes with Release 1.6.0: S-WdgM Subpackage 1.6.0 ............................................................ 20 
3.23 Changes with Release 1.5.0: S-WdgM Subpackage 1.5.0 ............................................................ 21 
3.24 Changes with Release 1.4.0: S-WdgM Subpackage 1.4.0 ............................................................ 21 
3.25 Changes with Release 1.3.1: WdgM 

--- Page 5 ---
5 
Project Name: Safe Watchdog Manager Version: 3.4.6 
Document Title: Release Notes Doc.No:  D-SAFEX-RP-70-012 Page 
Date:  21.11.2014 
Version:  3.4.6 
File name: S-WdgM_ReleaseNotes.doc 
Author: TTTech 
© TTTech-Automotive GmbH 
Ensuring Reliable Networks

--- Page 6 ---
6 
Project Name: Safe Watchdog Manager Version: 3.4.6 
Document Title: Release Notes Doc.No:  D-SAFEX-RP-70-012 Page 
Date:  21.11.2014 
Version:  3.4.6 
File name: S-WdgM_ReleaseNotes.doc 
Author: TTTech 
© TTTech-Automotive GmbH 
Ensuring Reliable Networks 
1 Overview 
The Safe Watchdog Manager (S-WdgM) is upper software layer of the Safe Watchdog Manager Stack. 
The S-WdgM Stack is part of the service layer of the AUTOSAR architecture. The S-WdgM monitors the 
program flow and timing constrains of so-called Supervised Entities. When it detects a violation of the pre-
configured program flow and ti

[… 20 further page(s) not extracted …]
