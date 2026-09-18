---
title: "Watchdog Interface — S-WdgIf ReleaseNotes"
description: "Converted Release Notes from S-WdgIf_ReleaseNotes.pdf (PDF, 309 KB)."
---

:::note
Converted from `WdgIf/doc/S-WdgIf_ReleaseNotes.pdf` (Release Notes; original PDF, about 309 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to WdgIf](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
TTTech Automotive GmbH 
Schoenbrunner Str. 7, A-1040 Vienna, Austria, Tel. + 43 1 585 34 34-0, Fax +43 1 585 34 34-90, office@tttech-automotive.com 
No part of the document may be reproduced or transmitted in any from or by any means, electronic or mechanical, for any purpose, without the written permission of TTTech 
Automotive. Company or product names mentioned in this document may be trademarks or registered trademarks of their respective companies. TTTech Automotive undertakes no 
further obligation in relation to this document. 
Copyright © 2009, TTTech Automotive GmbH. All rights reserved.                                                                                                                                Subject to change and corrections 
Ensuring Reliable Networks 
 
Safe Watchdog Interface 
Release Notes 
  
Author: TTTech 
Security: Confidential 
Document number: D-SAFEX-RP-70-014 
Document version: 3.3.6 
Date: 24.04.2015 
Status: released 
Review: VLE

--- Page 2 ---
2 
Project Name: Safe Watchdog Interface  
Document Title: Release Notes Ref.:  D-SAFEX-RP-70-014 Page 
Date:  24.04.2015 
Version:  3.3.6 
File name: S-WdgIf_ReleaseNotes.doc 
Author: TTTech 
© TTTech-Automotive GmbH 
Ensuring Reliable Networks 
 
 
 
Revision Chart 
A revision is a new edition of the document and affects all sections of this document.  
 
Document 
Version  
Date Responsible Person Modification 
1.0.0 14.12.2011 VLE Initial version for the S-WdgIf Subpackage 1.2.0 
1.0.1 09.02.2012 VLE Macro checks implemented 
1.0.2 09.03.2012 JDU Increased Subpackage version number (due to 
new config generator) 
1.0.3 13.04.2012 VLE Update due to Release 1.7.0 
1.0.4 25.05.2012 VLE Update due to Release 1.8.0 
1.0.5 07.09.2012 PPU Update due to Release 1.9.0 
2.0.3 25.10.2012 PPU Test release 2.0.3 to check the delivery 
structure. This is NOT a customer release! 
3.0.1 16.11.2012 PPU WdgIf_GetTickCounter() API changed therefore 
also the major version changed to 3. 
3.1.0 11.01.2013 PPU Generators works now with unsupported Wdg 
Drivers 
3.1.1 05.04.2013 JDU Configuration generator update 
3.1.5 29.11.2013 JDU Configuration generator update 
3.2.0 19.02.2014 PPU Autosar 4 update and bug fixes, beta version 
3.3.0 21.03.2014 PPU Update and bug fixes for Autosar 4 environment 
compatibility. Backward compatibility to Autosar 
3.1 environment added too. 
3.3.1 10.04.2014 PPU Generator bug fix for Autosar compatible driver 
3.3.2 27.05.2014 PPU Release for the AUTOSAR 4.0 and AUTOSAR 
3.1 compatible S-WdgIf module 
3.3.3 14.08.2014 PPU Safety Case document release 
3.3.4 24.11.2014 PPU Bugfix release for WdgIf embedded code 
3.3.5 20.02.2015 PPU Bugfix release, Generator only 
3.3.6 24.04.2015 PPU Bugfix release, Generator only

--- Page 3 ---
3 
Project Name: Safe Watchdog Interface  
Document Title: Release Notes Ref.:  D-SAFEX-RP-70-014 Page 
Date:  24.04.2015 
Version:  3.3.6 
File name: S-WdgIf_ReleaseNotes.doc 
Author: TTTech 
© TTTech-Automotive GmbH 
Ensuring Reliable Networks 
Contents 
1 Overview .................................................................................................................................................. 4 
2 Content of the Module Release ............................................................................................................. 5 
3 Quality level of current release.............................................................................................................. 6 
4 Change history ........................................................................................................................................ 7 
4.1 Changes with version 3.3.6 .............................................................................................................. 7 
4.2 Changes with version 3.3.5 .............................................................................................................. 7 
4.3 Changes with version 3.3.4 .............................................................................................................. 7 
4.4 Changes with version 3.3.3 .............................................................................................................. 8 
4.5 Changes with version 3.3.2 .............................................................................................................. 8 
4.6 Changes with version 3.3.1 .............................................................................................................. 8 
4.7 Changes with version 3.3.0 .............................................................................................................. 9 
4.8 Changes with version 3.2.0 .............................................................................................................. 9 
4.9 Changes with version 3.1.5 .............................................................................................................. 9 
4.10 Changes with version 3.1.1 .............................................................................................................. 9 
4.11 Changes with version 3.1.0 ............................................................................................................ 10 
4.12 Changes with version 3.0.1 ............................................................................................................ 10 
4.13 Changes with Release 1.9.0: S-WdgIf SubPackage 2.0.2 ............................................................. 11 
4.14 Changes with Release 1.8.0: S-WdgIf SubPackage 1.4.0 ............................................................. 11 
4.15 Changes with Release 1.7.0: S-WdgIf SubPackage 1.3.0 ............................................................. 11 
4.16 Changes with Release 1.6.0: S-WdgIf Subpackage 1.2.1 ............................................................. 11 
4.17 Changes with Release 1.5.0: S-WdgIf Subpackage 1.2.0 ............................................................. 11 
4.18 Changes with Release 1.2.0: S-WdgIf Subpackage ...................................................................... 11 
5 Test status ............................................................................................................................................. 12 
6 Known issues, limitations, updates .................................................................................................... 13 
7 Differences to AUTOSAR specification .............................................................................................. 14 
8 Abbreviation and glossary ................................................................................................................... 15

--- Page 4 ---
4 
Project Name: Safe Watchdog Interface  
Document Title: Release Notes Ref.:  D-SAFEX-RP-70-014 Page 
Date:  24.04.2015 
Version:  3.3.6 
File name: S-WdgIf_ReleaseNotes.doc 
Author: TTTech 
© TTTech-Automotive GmbH 
Ensuring Reliable Networks 
1 Overview 
The Safe Watchdog Interface (S-WdgIf) is the middle layer of the Safe Watchdog Manager Stack. The 
Safe Watchdog Manager Stack is part of the service layer of the AUTOSAR architecture. The Safe 
Watchdog Interface abstracts one or more Safe Watchdog Driver modules for the Safe Watchdog Manager 
module. 
 
The Safe Watchdog Interface consists of  
 embedded software module and 
 configuration generator. 
 
The Safe Watchdog Interface is compatible to the WdgIf module as specified in the AUTOSAR 4.0 and 
AUTOSAR 3.1 specifications but not fully compliant. For deviations and justifications please see the S -WdgIf 
User Manual.

--- Page 5 ---
5 
Project Name: Safe Watchdog Interface  
Document Title: Release Notes Ref.:  D-SAFEX-RP-70-014 Page 
Date:  24.04.2015 
Version:  3.3.6 
File name: S-WdgIf_ReleaseNotes.doc 
Author: TTTech 
© TTTech-Automotive GmbH 
Ensuring Reliable Networks 
2 Content of the Module Release 
 
Title Version*) Author Description 
WdgIf/ 3.3.6 TTTech S-WdgIf Module 
    S-WdgIf_ReleaseNotes.pdf    
    Description/ 3.3.6 TTTech  
        WdgIf_Bswmd_A4.arxml   AUTOSAR 4.x file 
        WdgIf_Bswmd.arxml   AUTOSAR 3.y file 
    Doc_SafetyCase/ 1.2.0   
        S-WdgIf_SafetyCase.pdf   Safety Case document 
    Doc_SafetyManual/ 1.8.9   
        S-WdgIf_SafetyManual.pdf    
    Doc_TechRef/ 1.9.4 TTTech  
        S-WdgIf_UserManual.pdf   User Manual 
    Generator/ 3.3.27 TTTech  
        LICENSE    
        Wdg_If_Cfg_Gen.exe   S-WdgIf Configuration Generator 
    GenTool_Ead/ 1.0.0 TTTech  
        Identifier.xml    
        Identifier_A4.xml    
    Implementation/ 3.3.6 TTTech  
        WdgIf.c   Watchdog Interface Code 
        WdgIf.h     Watchdog Interface Code 
        WdgIf_Cfg.h   Watchdog Interface Code 
        WdgIf_Types.h   Watchdog Interface Code 
*) Bold/blue version numbers are new artefacts delivered in this release. The non-bold artefacts are the 
previously released compatible artifacts. All artefacts listed her

[… 9 further page(s) not extracted …]
