---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — TechnicalReference 3rdParty-MCAL-Integration"
description: "Converted Technical Reference (vendor) from TechnicalReference_3rdParty-MCAL-Integration.pdf (PDF, 836 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/TechnicalReferences/TechnicalReference_3rdParty-MCAL-Integration.pdf` (Technical Reference (vendor); original PDF, about 836 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MCAL Integration Package 
Technical Reference 
 
Basics and workflows 
Version 1.01.00 
 
 
 
 
 
 
 
 
 
 
Authors Andrej Gazvoda, Günther Piehler, Roland Süß, Ingo 
Wuttke 
Status Released

--- Page 2 ---
Technical Reference MCAL Integration Package 
2015, Vector Informatik GmbH Version: 1.01.00 
based on template version 5.2.0 
2 / 23 
Document Information 
History 
Author Date Version Remarks 
Roland Süß ; Ingo Wuttke 2015-02-27 1.00.00 Initial Ideas, usage as 
Application Note; Porting to 
Technical Reference 
template; adding detailed 
description about 3rd party 
tools etc. 
Günther Piehler 2015-04-24 1.00.01 Review; small changes to 
increase understandability; 
Known Issue for missing 
config items added  
released 
Andrej Gazvoda; Roland Süß 2015-06-30 1.00.02 5.4 / 5.5 - Added known 
issues regarding EB tresos™ 
tool 
Günther Piehler 2015-07-17 1.01.00 1.3 - Introduction of Mixed 
AUTOSAR use case 
2 ff - Extend description of 
MCAL preparation 
(prerequisits) 
3 - hint about recommended 
workflow added 
Reference Documents 
No. Source Title Version 
[1]  Vector Product Information MICROSAR Vector SLP4 1.03.02 
[2]  Vector Catalog – Product Information MICROSAR – Chapter MCAL V1.3 – 
2015-02 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference MCAL Integration Package 
2015, Vector Informatik GmbH Version: 1.01.00 
based on template version 5.2.0 
3 / 23 
Contents 
1 Introduction................................ ................................ ................................ ................... 6 
1.1 Responsibility ................................ ................................ ................................ ..... 6 
1.2 Support requests................................ ................................ ................................  6 
1.3 Mix between AUTOSAR specification versions ................................ .................. 7 
2 First Steps ................................ ................................ ................................ ..................... 8 
2.1 Delivery structure ................................ ................................ ...............................  8 
2.2 Starting up ................................ ................................ ................................ ......... 9 
2.2.1 MCAL delivered within Vector SIP ................................ ...................... 9 
2.2.2 MCAL not contained within Vector SIP ................................ ............... 9 
2.2.3 MCAL Update needed ................................ ................................ ...... 10 
3 Workflow ................................ ................................ ................................ ..................... 11 
3.1 Single configuration tool usage ................................ ................................ ........ 11 
3.2 Mixed configuration tool usage................................ ................................ ......... 12 
3.3 Split configuration tool usage ................................ ................................ ........... 13 
4 Configuration tools ................................ ................................ ................................ ..... 15 
4.1 Vector DaVinci Configurator ................................ ................................ ............. 15 
4.2 EB tresos™ ................................ ................................ ................................ ...... 15 
4.2.1 Setting up a new Configuration Project ................................ ............ 15 
4.2.2 Project Details ................................ ................................ .................. 16 
4.2.3 Selection of components ................................ ................................ .. 16 
4.2.4 Creation of importers and exporters ................................ ................. 17 
4.2.5 Configure the MCAL components ................................ .................... 18 
4.2.6 Generation of the 3rd party MCAL ................................ .................... 18 
4.3 Configuration hints for parallel usage of DaVinci Configurator and EB 
tresos™ ................................ ................................ ................................ ........... 18 
4.3.1 Vector DaVinci Configurator 5 ................................ .......................... 18 
4.3.2 EB tresos™ ................................ ................................ ...................... 19 
5 Known Issues ................................ ................................ ................................ ............. 20 
5.1 MCAL and SIP storage location using Vector Makesupport ..............................  20 
5.2 Long path names ................................ ................................ ............................. 20 
5.3 Missing configuration items within imported configuration ................................  20 
5.4 Configuration Export with EB tresos™ Version 13.0.0 ................................ ...... 21 
5.5 Error messages regarding CommonPublishedInformation with EB tresos™ .... 21 
6 Glossary and Abbreviations ................................ ................................ ...................... 22

--- Page 4 ---
Technical Reference MCAL Integration Package 
2015, Vector Informatik GmbH Version: 1.01.00 
based on template version 5.2.0 
4 / 23 
6.1 Glossary ................................ ................................ ................................ .......... 22 
6.2 Abbreviations ................................ ................................ ................................ ... 22 
7 Contact ................................ ................................ ................................ ........................ 23

--- Page 5 ---
Technical Reference MCAL Integration Package 
2015, Vector Informatik GmbH Version: 1.01.00 
based on template version 5.2.0 
5 / 23 
Illustrations 
Figure 3-1 Configuration workflow – Mixed configuration tool usage .......................... 12 
Figure 4-1 New Configuration Project ................................ ................................ ........ 15 
Figure 4-2 Configuration Project Data ................................ ................................ ........ 16 
Figure 4-3 Component Configurations ................................ ................................ ....... 17 
Figure 4-4 Create an exporter (step 1) ................................ ................................ ....... 17 
Figure 4-5 Create an exporter (step 2 – AUTOSAR options) ................................ ...... 17 
Figure 4-6 Generate Button ................................ ................................ ....................... 18 
Figure 4-7 DEM Path using DaVinci Configurator 5 ................................ ................... 18 
Figure 4-8 Settings within DaVinci Configurator 5 Pro................................ ................ 18 
Figure 4-9 DEM-Path in the Outline window of tresos™ ................................ ............ 19 
Figure 4-10 DEM-Path within tresos™ ................................ ................................ ......... 19 
Figure 4-11 Settings for DEM within tresos™ ................................ ..............................  19 
 
Tables 
Table 3-1  Guidance for single configuration tool usage ................................ ............ 11 
Table 3-2  Guidance for mixed configuration tool mode ................................ ............. 13 
Table 3-3  Guidance for split configuration tool usage ................................ ............... 14

--- Page 6 ---
Technical Reference MCAL Integration Package 
2015, Vector Informatik GmbH Version: 1.01.00 
based on template version 5.2.0 
6 / 23 
1 Introduction 
The MICROSAR MCAL Integration Package covers the integration of a 3rd party MCAL 
package into the Vector MICROSAR BSW stack. As part of this Vector performs a setup of 
the MCAL provided by the customer or the semiconductor vendor  and supplements it with 
items needed for the integration with the MICROSAR BSW. 
Typically the semiconductor vendor delivers the MCAL with its own configuration and 
generation tool chain. Vector provides solutions to deal with the dependencies and 
interfaces on embedded and on configuration level between the AUTOSAR BSW and the 
MCAL components (with AUTOSAR4.0.3 these configuration level based interfaces are 
about 10 parameters). 
This document support s the user by launching the delivery, setting up a project and 
serving the tool ing- and configuration -based interfaces between the Vector MICROSAR 
BSW and the 3rd party MCAL. The term “tooling” means Vector DaVinci Configurator o

[… 17 further page(s) not extracted …]
