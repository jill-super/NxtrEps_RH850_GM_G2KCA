---
title: "DaVinci Configuration Support — TechnicalReference EcuConfigurationFiles"
description: "Converted Technical Reference (vendor) from TechnicalReference_EcuConfigurationFiles.pdf (PDF, 223 KB)."
---

:::note
Converted from `TL102A_Davinci/tools/Developer/Docs/TechnicalReference_EcuConfigurationFiles.pdf` (Technical Reference (vendor); original PDF, about 223 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL102A_Davinci](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
ECU-C File Handling 
Technical Reference 
 
 
 
 
Version 1.13 
 
 
 
 
 
 
Authors: Michael Schuele, Matthias Wernicke 
Version: 1.13 
Status: released (in preparation/completed/inspected/released)

--- Page 2 ---
ECU-C File Handling Technical Reference  
 2014, Vector Informatik GmbH Version: 1.13 
  
2 / 34  
History 
 
Author Date Version Remarks 
M. Schuele 2009-02-19 0.1.0 Initial version 
M. Schuele 2009-04-11 1.0.0 final version 
M. Wernicke  2009-04-17 1.1 Review and update 
M. Schuele 2009-08-03 1.2 Added description of difference dialog 
M. Schuele 2010-01-27 1.3 Added new ECU-C parameters for DaVinci 3.0 
M. Wernicke  2010-01-28 1.4 Review and update 
M. Schuele 2010-05-05 1.5 Introduced different but equivalent parameter values 
M. Schuele 2010-05-14 1.6 Added new ECU-C parameters for DaVinci 3.0 SP2 
M. Schuele 2010-07-20 1.7 Added new ECU-C parameters for DaVinci 3.0 SP3 
M. Schuele 2010-11-29 1.8 Added new ECU-C parameters for DaVinci 3.0 SP4 
M. Schuele 2011-05-06 1.9 ComTimeoutFactor synchronization is configurable 
M. Schuele 2012-02-02 1.10 Added new ECU-C parameters for DaVinci 3.0 SP5 and 3.1 
M. Schuele 2012-08-30 1.11 Added a note about AUTOSAR 4 
M. Schuele 2013-05-03 1.12 Added new ECU-C parameters for DaVinci 3.5 
M. Schuele 2014-03-27 1.13 Added SchM config to Rte section

--- Page 3 ---
ECU-C File Handling Technical Reference  
 2014, Vector Informatik GmbH Version: 1.13 
  
3 / 34  
Contents  
1 Overview ............................................................................................. ............................ 5 
1.1  Intended Audience .................................................................................... ...... 5 
1.2  Terms and Acronyms ................................................................................... .... 5 
2 The ECU-Configuration Process ........................................................................ ........... 7 
2.1  The ECU-Configuration File ........................................................................... . 8 
3 DaVinci DEV and the ECU-C file ....................................................................... ........... 11  
3.1  Project Assistant..................................................................................... ........ 11  
3.2  Initial synchronization (bi-directional update) .................................................. 11  
3.3  Automatic synchronization ............................................................................  12  
3.4  ECU-C file locking ................................................................................... ...... 12  
3.5  BSWMD files .......................................................................................... ....... 13  
3.5.1  Pre- and Recommended config sections ....................................................... 13  
3.6  Synchronizing an ECU-C file ......................................................................... 13  
3.6.1  Step 1: Analysis of the RTE configuration in the workspace .......................... 14  
3.6.2  Step 2: Comparison of workspace and ECU-C file ........................................ 15  
3.6.3  Synchronization direction “import” ................................................................. 16  
3.6.4  Synchronization direction “export” ................................................................. 16  
3.6.5  ECU-Configuration difference dialog ............................................................. 16  
4 ECU-Configuration parameters ......................................................................... .......... 18  
4.1  Vendor Specific Configuration Parameters .................................................... 18  
4.2  Rte module ........................................................................................... ........ 18  
4.2.1  Parameters ........................................................................................... ........ 18  
4.3  SchM module .......................................................................................... ...... 19  
4.3.1  General .............................................................................................. ........... 19  
4.3.2  Parameters ........................................................................................... ........ 20  
4.3.3  Rte .................................................................................................. .............. 20  
4.3.4  Os 20  
4.4  Com module............................................................................................ ...... 21  
4.4.1  Parameters ........................................................................................... ........ 21  
4.4.2  Equivalent parameter values ......................................................................... 22  
4.4.2.1  ComTimeoutFactor ..................................................................................... .. 23  
4.5  Os module ............................................................................................ ........ 23  
4.5.1  Parameters ........................................................................................... ........ 23  
4.5.2  Equivalent parameter values ......................................................................... 26  
4

--- Page 4 ---
ECU-C File Handling Technical Reference  
 2014, Vector Informatik GmbH Version: 1.13 
  
4 / 34  
4.6.2  Equivalent parameter values ......................................................................... 27  
4.7  Board ................................................................................................ ............ 27  
4.7.1  Parameters ........................................................................................... ........ 27  
4.7.2  Equivalent parameter values ......................................................................... 28  
4.8  ComSignals and ComSignalGroups .............................................................. 28  
4.8.1  dbc files ............................................................................................ ............. 28  
4.8.2  ECU-Extract .......................................................................................... ........ 28  
4.8.3  AUTOSAR 2.1 .......................................................................................... ..... 29  
4.8.4  AUTOSAR 3.x .......................................................................................... ..... 29  
4.8.5  Relevant ComSignals .................................................................................. .. 29  
4.8.6  Callbacks ............................................................................................ .......... 29  
5 Best practices ....................................................................................... ....................... 31  
5.1  Always work on the latest communication databases .................................... 31  
5.2  Do not edit the same module configuration in different tools at the same 
time ................................................................................................. .............. 31  
5.3  Ensure that all tools use the same max. SHORT-NAME length ..................... 32  
5.4  ECU-C files have to be valid according to the AUTOSAR schema ................ 32  
5.5  Configuration elements must have unique SHORT-NAMEs .......................... 33  
6 Contact .............................................................................................. ........................... 34

--- Page 5 ---
ECU-C File Handling Technical Reference  
 2014, Vector Informatik GmbH Version: 1.13 
  
5 / 34  
1  Overview 
DaVinci Developer is part of Vector’s solution for AUTOSAR compatible ECU 
development. It is used to configure and generate the Rte in AUTOSAR 3.x based projects 
and therefore interacts with other BSW configurators through the ECU-Configuration file. 
This document describes the configuration process r elated to DaVinci Developer from a 
technical point of view, trying to give the user a better understanding of the internal 
processes and how the tool reacts in different situations. 
 
  
 
Note 
Starting with DaVinci Developer 3.3, AUTOSAR 4.0 ba sed software designs can be 
created and edited. However, the configuration and generation of the AUTOSAR 4.0 
Rte has been moved from DaVinci Developer to DaVinc i Configurator Pro. Therefore 
this document is only relevant for AUTOSAR 3.x based projects. 
  
1.1  Intended Audience 
This document aims at ECU developers who are involv ed in the AUTOSAR compatible 
ECU-Configuration process and use DaVinci Developer to configure and generate the Rte 
module. 
As DaVinci DEV updates the ECU-Configuration file a utomatically during save and load of 
a workspace, the presented information is not essen tial when working with the tools but 
provides some additional information how the 

[… 28 further page(s) not extracted …]
