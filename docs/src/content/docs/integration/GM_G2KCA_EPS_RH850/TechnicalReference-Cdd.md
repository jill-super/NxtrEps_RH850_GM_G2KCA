---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — TechnicalReference Cdd"
description: "Converted Technical Reference (vendor) from TechnicalReference_Cdd.pdf (PDF, 725 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/TechnicalReferences/TechnicalReference_Cdd.pdf` (Technical Reference (vendor); original PDF, about 725 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR Complex Device Driver 
Technical Reference 
 
DaVinci Configurator 
Version 2.02.00 
 
 
 
 
 
 
 
 
 
 
 
Authors Safiulla Shakir, Gunnar Meiss, Markus Bart 
Status Released

--- Page 2 ---
Technical Reference MICROSAR Complex Device Driver 
2014, Vector Informatik GmbH Version: 2.02.00 
based on template version 5.2.0 
2 / 41 
Document Information 
History 
Author Date Version Remarks 
Safiulla Shakir 2012-03-23 1.00.00 Initial Version 
Gunnar Meiss 2012-08-08 2.00.00 Support AUTOSAR 4 
Gunnar Meiss 2013-05-13 2.00.01 performed review rework 
Markus Bart 2014-02-05 2.01.00 Support J1939Rm Contribution 
Markus Bart 2014-02-28 2.02.00 Support the StartOfReception API with the 
PduInfoType according to ASR4.1.2 
Gunnar Meiss 2014-05-07 2.02.00 AR4-769: ESCAN00075414 
AR4-744: Cdd shall support 
CddSoAdUpperLayerContribution as an 
extension to AR 4.0.3 (schema shall 
remain at AR 4.0.3) 
Reference Documents 
No. Source Title Version 
[1]  AUTOSAR AUTOSAR_TPS_ECUConfiguration.pdf 3.2.0 
[2]  AUTOSAR AUTOSAR_TR_BSWModuleList.pdf 1.6.0 
 
 
 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 
  
 
 
  
 
Caution 
This symbol calls your attention to warnings.

--- Page 3 ---
Technical Reference MICROSAR Complex Device Driver 
2014, Vector Informatik GmbH Version: 2.02.00 
based on template version 5.2.0 
3 / 41 
Contents 
1. Component History ................................ ................................ ................................ ........ 6 
2. Introduction ................................ ................................ ................................ .................... 7 
2.1 Architecture Overview ................................ ................................ ..............................  8 
3. Functional Description ................................ ................................ ................................ .. 9 
3.1 Features ................................ ................................ ................................ ................... 9 
4. Integration ................................ ................................ ................................ .................... 10 
4.1 Scope of Delivery ................................ ................................ ................................ ... 10 
4.1.1 Static Files ................................ ................................ ................................ .... 10 
4.1.2 Dynamic Files ................................ ................................ ...............................  10 
4.2 Compiler Abstraction and Memory Mapping ................................ ........................... 10 
5. API Description CddPduRUpperLayerContribution as IF ................................ .......... 11 
5.1 Services used by <CDD> ................................ ................................ ....................... 11 
5.2 Callback Functions ................................ ................................ ................................ . 11 
5.2.1 <CDD>_RxIndication................................ ................................ ..................... 11 
5.2.2 <CDD>_TxConfirmation ................................ ................................ ................ 12 
5.2.3 <CDD>_TriggerTransmit ................................ ................................ ............... 12 
6. API Description CddPduRUpperLayerContribution as TP ................................ ........ 14 
6.1 Services used by <CDD> ................................ ................................ ....................... 14 
6.2 Callback Functions ................................ ................................ ................................ . 14 
6.2.1 <CDD>_StartOfReception ................................ ................................ ............. 14 
6.2.2 <CDD>_CopyRxData ................................ ................................ .................... 15 
6.2.3 <CDD>_TpRxIndication ................................ ................................ ................ 15 
6.2.4 <CDD>_CopyTxData ................................ ................................ .................... 16 
6.2.5 <CDD>_TpTxConfirmation ................................ ................................ ............ 18 
7. API Description CddPduRLowerLayerContribution as IF ................................ ......... 19 
7.1 Services provided by <CDD> ................................ ................................ ................. 19 
7.1.1 <CDD>_Transmit ................................ ................................ .......................... 19 
7.1.2 <CDD>_CancelTransmit ................................ ................................ ............... 19 
7.2 Services used by <CDD> ................................ ................................ ....................... 20 
8. API Description CddPduRLowerLayerContribution as TP ................................ ........ 21 
8.1 Services provided by <CDD> ................................ ................................ ................. 21 
8.1.1 <CDD>_Transmit ................................ ................................ .......................... 21

--- Page 4 ---
Technical Reference MICROSAR Complex Device Driver 
2014, Vector Informatik GmbH Version: 2.02.00 
based on template version 5.2.0 
4 / 41 
8.1.2 <CDD>_CancelTransmit ................................ ................................ ............... 21 
8.1.3 <CDD>_CancelReceive ................................ ................................ ................ 22 
8.1.4 <CDD>_ChangeParameter ................................ ................................ ........... 22 
8.2 Services used by <CDD> ................................ ................................ ....................... 23 
9. API Description CddComIfUpperLayerContribution ................................ .................. 24 
9.1 Services used by <CDD> ................................ ................................ ....................... 24 
9.2 Callback Functions ................................ ................................ ................................ . 24 
9.2.1 <CDD>_RxIndication................................ ................................ ..................... 24 
9.2.2 <CDD>_TxConfirmation ................................ ................................ ................ 25 
9.2.3 <CDD>_TriggerTransmit ................................ ................................ ............... 25 
10. API Description CddJ1939RmContribution ................................ ................................  27 
10.1 Services used by <CDD> ................................ ................................ ....................... 27 
10.2 Callback Functions ................................ ................................ ................................ . 27 
10.2.1 <CDD>_RequestIndication ................................ ................................ ............ 27 
10.2.2 <CDD>_AckIndication ................................ ................................ ................... 28 
10.2.3 <CDD>_RequestTimeoutIndication ................................ ...............................  28 
11. Configuration................................ ................................ ................................ ................ 37 
11.1 Configuration Variants ................................ ................................ ............................ 37 
12. AUTOSAR Standard Compliance ................................ ................................ ................ 38 
12.1 Deviations ................................ ................................ ................................ .............. 38 
12.2 Additions/ Extensions ................................ ................................ ............................. 38 
12.3 Limitations ................................ ................................ ................................ .............. 38 
13. Glossary and Abbreviations ................................ ................................ ........................ 39 
13.1 Glossary ................................ ................................ ................................ ................. 39 
13.2 Abbreviations ................................ ................................ ................................ ......... 40 
14. Contact................................ ................................ ................................ .......................... 41

--- Page 5 ---
Technical Reference MICROSAR Complex Device Driver 
2014, Vector Informatik GmbH Version: 2.02.00 
based on template version 5.2.0 
5 / 41 
Illustrations 
Figure 2-1 

[… 35 further page(s) not extracted …]
