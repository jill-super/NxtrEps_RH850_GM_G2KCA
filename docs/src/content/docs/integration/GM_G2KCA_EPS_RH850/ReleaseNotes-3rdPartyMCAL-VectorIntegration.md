---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — ReleaseNotes 3rdPartyMCAL VectorIntegration"
description: "Converted Release Notes from ReleaseNotes_3rdPartyMCAL_VectorIntegration.pdf (PDF, 206 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/ReleaseNotes/ReleaseNotes_3rdPartyMCAL_VectorIntegration.pdf` (Release Notes; original PDF, about 206 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
3rdParty MCAL Integration  
Release Notes 
Renesas RH850P1x 
 
 
Version 1.0.0 
 
 
 
 
 
 
 
 
 
 
 
Authors Roland Suess 
Status Released

--- Page 2 ---
Release Notes 3rdParty MCAL Integration 
2015, Vector Informatik GmbH Version: 1.0.0 
based on template version 5.9.0 
2 / 7 
Document Information 
History 
Author Date Version Remarks 
Roland Suess 2015-10-05 1.0.0 Integration of Renesas package 
AUTOSAR_RH850_P1x_MCAL_E4.03 
Reference Documents 
No. Source Title Version 
[1] Vector TechnicalReference_3rdParty-MCAL-Integration.pdf 1.01.00 
 
Scope of the Document 
This document  contains information about the integration of 3 rd Party MCAL into Vector 
software stack.

--- Page 3 ---
Release Notes 3rdParty MCAL Integration 
2015, Vector Informatik GmbH Version: 1.0.0 
based on template version 5.9.0 
3 / 7 
Contents 
1 MCAL Integration ................................ ................................ ................................ .......... 4 
1.1 Type of Integration ................................ ................................ ............................. 4 
1.2 MCAL Location within SIP ................................ ................................ .................. 4 
1.3 Supported µController ................................ ................................ ........................ 4 
1.4 Used MCAL Packages ................................ ................................ ....................... 4 
1.5 Configuration Tools ................................ ................................ ............................ 4 
1.6 Supported Compilers ................................ ................................ ......................... 4 
2 Vector Comment ................................ ................................ ................................ ........... 5 
2.1 Known Issues ................................ ................................ ................................ .... 5 
2.1.1 RamTst: Dem event parameter name not generated correctly ............ 5 
3 Glossary and Abbreviations ................................ ................................ ........................ 6 
3.1 Glossary ................................ ................................ ................................ ............ 6 
3.2 Abbreviations ................................ ................................ ................................ ..... 6 
4 Contact ................................ ................................ ................................ .......................... 7

--- Page 4 ---
Release Notes 3rdParty MCAL Integration 
2015, Vector Informatik GmbH Version: 1.0.0 
based on template version 5.9.0 
4 / 7 
1 MCAL Integration 
1.1 Type of Integration 
 
Comfort Integration 
Vector tool DaVinci Configurator 5 is used for configuration 
> as comfort editor for Mcu component 
> as generic editor for other MCAL modules 
 
Recommended workflow:  
Generation and changes in configuration are done in DaVinci Configurator. 
 
1.2 MCAL Location within SIP 
 
The 3rd Party MCAL is separated from the Vector parts within the SIP, furthermore, it might 
not be part of the delivery. Please refer to chapter ‘First Steps’ in document 
TechnicalReference_3rdParty-MCAL-Integration.pdf [1]. 
 
1.3 Supported µController 
This integration supports the Renesas RH850P1M  target with the devices R7F701310, 
R7F701311, R7F701312, R7F701314 and R7F701315. 
 
1.4 Used MCAL Packages 
> AUTOSAR_RH850_P1x_MCAL_E4.03 
> Mantis_0026358_HotFix_20150226 
 
1.5 Configuration Tools 
DaVinci Configurator 5 
 
1.6 Supported Compilers 
GreenHills (MULTI 6.1.4) and Compiler 2013.5.5

--- Page 5 ---
Release Notes 3rdParty MCAL Integration 
2015, Vector Informatik GmbH Version: 1.0.0 
based on template version 5.9.0 
5 / 7 
2 Vector Comment 
Please consider the attached TechnicalReference_3rdParty-MCAL-
Integration.pdf [1] for further information regarding Vector in tegration and setup of a 
project. 
 
2.1 Known Issues 
2.1.1 RamTst: Dem event parameter name not generated correctly 
 
The Dem event was  not generated correctly. Therefore Renesas provided hot fix package 
Mantis_0026358_HotFix_20150226 containing a new RamTst generator. This fix is part of 
the integration package.

--- Page 6 ---
Release Notes 3rdParty MCAL Integration 
2015, Vector Informatik GmbH Version: 1.0.0 
based on template version 5.9.0 
6 / 7 
3 Glossary and Abbreviations 
3.1 Glossary 
Term Description 
3rd party components 
/ MCAL 
BSW modules not provided by  Vector. Vector may have integrated the 
software within the SIP but does not take over any re sponsibility 
regarding functionality of these modules. 
DaVinci Configurator  Configuration and generation tool for Vector MICROSAR components 
EB tresos™  Configuration and generation tool for MCAL components 
 
Table 3-1  Glossary 
 
 
3.2 Abbreviations 
Abbreviation Description 
MCAL Microcontroller Abstraction Layer  
AUTOSAR Automotive Open System Architecture 
SIP  Software Integration Package (as provided by Vector) 
Table 3-2  Abbreviations

[… 1 further page(s) not extracted …]
