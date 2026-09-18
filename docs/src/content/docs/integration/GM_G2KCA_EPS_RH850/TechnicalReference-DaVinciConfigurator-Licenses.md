---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — TechnicalReference DaVinciConfigurator Licenses"
description: "Converted Technical Reference (vendor) from TechnicalReference_DaVinciConfigurator_Licenses.pdf (PDF, 255 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/TechnicalReferences/TechnicalReference_DaVinciConfigurator_Licenses.pdf` (Technical Reference (vendor); original PDF, about 255 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
DaVinci Configurator License Handling 
Technical Reference 
 
 
Version 1.4 
 
 
 
 
 
 
 
 
 
 
 
Authors Michael Hoffmann 
Status Released

--- Page 2 ---
Technical Reference DaVinci Configurator License Handling 
2015, Vector Informatik GmbH Version: 1.4 
based on template version 4.11.3 
2 / 16 
Document Information 
History 
Author Date Version Remarks 
Michael Hoffmann 2014-01-02 1.0  
Michael Hoffmann 2014-02-14 1.1 Server Configuration in 3.1 
changed 
Michael Hoffmann 2015-02-10 1.2 Server Configuration in 3.1 
changed; VTT option added 
Michael Hoffmann 2015-04-27 1.3 DaVinci_CFG floating server 
option added 
Michael Hoffmann 2015-05-21 1.4 Pool based licenses added 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference DaVinci Configurator License Handling 
2015, Vector Informatik GmbH Version: 1.4 
based on template version 4.11.3 
3 / 16 
Contents 
1 Introduction ................................ ................................ ................................ .................... 5 
2 License Information ................................ ................................ ................................ ....... 6 
2.1 SIP Based License ................................ ................................ .......................... 6 
2.2 Software Based License ................................ ................................ .................. 6 
2.3 Hardware Based Licenses................................ ................................ ............... 6 
2.4 License Display ................................ ................................ ...............................  7 
2.5 Display of License Server Configuration and Options ................................ ...... 7 
3 License Server Configuration ................................ ................................ ....................... 8 
3.1 Server Configuration ................................ ................................ ....................... 8 
3.1.1 Settings ................................ ................................ ................................ ........... 9 
3.2 Server Option Usage Configuration ................................ ...............................  10 
3.3 Settings File Example ................................ ................................ .................... 10 
4 Pool Licence Handling ................................ ................................ ................................ . 12 
4.1 Standard Licenses ................................ ................................ ......................... 12 
4.1.1 Adding License Options ................................ ................................ ................ 12 
4.1.2 Return and Extend a Standard License ................................ ......................... 12 
4.2 Sporadic Licenses ................................ ................................ ......................... 12 
5 SIP License ................................ ................................ ................................ ................... 13 
6 DaVinci Developer License ................................ ................................ .......................... 14 
7 Abbreviations ................................ ................................ ................................ ............... 15 
7.1 Abbreviations ................................ ................................ ................................  15 
8 Contact ................................ ................................ ................................ .......................... 16

--- Page 4 ---
Technical Reference DaVinci Configurator License Handling 
2015, Vector Informatik GmbH Version: 1.4 
based on template version 4.11.3 
4 / 16 
Illustrations 
- 
Tables 
Table 2-1  License appearance ................................ ................................ ................... 7 
Table 3-1  Settings file locations ................................ ................................ .................. 8 
Table 3-2  License precedence................................ ................................ .................... 9 
Table 3-3  Server options ................................ ................................ .......................... 10

--- Page 5 ---
Technical Reference DaVinci Configurator License Handling 
2015, Vector Informatik GmbH Version: 1.4 
based on template version 4.11.3 
5 / 16 
1 Introduction 
The DaVinci Configurator  application can be activated by a SIP license and dongle or 
FlexNet based license. Both, the dongle and the  FlexNet based license, provide the .PRO 
option + supplemental options. These options activ ate additional  product functionality  
within the DaVinci Configurator.  
This document describes in which order the available licenses are applied and used by the 
DaVinci Configurator.

--- Page 6 ---
Technical Reference DaVinci Configurator License Handling 
2015, Vector Informatik GmbH Version: 1.4 
based on template version 4.11.3 
6 / 16 
2 License Information 
Detailed information about the current available an d used licenses can be obtained by 
starting the DaVinci Configurator  application and opening the ‘Licenses’ dialog (Help > 
Licenses). 
This dialog shows the current SIP license details (‘Show SIP License Details’ button) and 
the current tool license details (‘Show Tool License Details’). 
The tool license details dialog provides three sections: 
 SIP-based licenses 
 Software-based licenses 
 Hardware-based licenses (USB-dongle) 
2.1 SIP Based License 
This section shows the current ly available SIP license. A SIP license activates the BASE 
option of the DaVinci Configurator application. 
2.2 Software Based License 
This table lists all available FlexNet license inform ation ( server based  or local) that can 
potentially be used by the DaVinci Configurator application. 
For server based licenses the floating licensing and the pool licensing model is supported  
(see 3.1 for details).  
The actual used license model is shown in the label of the ‘License server’ property of the 
‘Licenses’ dialog. It can be ‘Pool’ or ‘Floating’, depending on which license model is 
defined within the server configuration file (see chapter 3 for details). 
2.3 Hardware Based Licenses 
This section contains all dongle based licenses detected by the application. 
  
 
Note 
Aladdin dongles (blue dongles) cannot be used in 64-Bit Windows with DaVinci 
Configurator executed in 64-Bit mode (which is the default on 64-Bit Windows). 
In that case the new Keyman dongles need to be used instead.

[… 10 further page(s) not extracted …]
