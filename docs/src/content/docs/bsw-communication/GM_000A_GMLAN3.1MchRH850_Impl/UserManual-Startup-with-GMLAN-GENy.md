---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — UserManual Startup with GMLAN GENy"
description: "Converted User Manual / User Guide from UserManual_Startup_with_GMLAN_GENy.pdf (PDF, 760 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/UserManual_Startup_with_GMLAN_GENy.pdf` (User Manual / User Guide; original PDF, about 760 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Vector Informatik GmbH, Ingerheimer Str. 24, 70499 Stuttgart 
  Tel. 0711/80670-0, Fax 0711/80670-399, Email can@vector-informatik.de 
  Internet http:\\www.vector-informatik.de 
 
 
 
 
 
 
 
 
 
 
 
 Startup with GMLAN and   
  GENy 
  User Manual 
  (Your First Steps) 
 
 
  Version 1.0.1

--- Page 2 ---
User Manual  Startup with GMLAN  
2011, Vector Informatik GmbH  Version: 1.0.1 
 based of template version 2.0 
1 / 32 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
Authors: Klaus Emmert 
Version: 1.0.1 
Status: in preparation (in preparation/completed/inspected/released)

--- Page 3 ---
User Manual  Startup with GMLAN  
2011, Vector Informatik GmbH  Version: 1.0.1 
 based of template version 2.0 
2 / 32 
History 
Author Date Version Remarks 
Klaus Emmert 2008-03-10 1.0 Created 
Klaus Emmert 2011-11-11 1.0.1 Improved Understandability

--- Page 4 ---
User Manual  Startup with GMLAN  
2011, Vector Informatik GmbH  Version: 1.0.1 
 based of template version 2.0 
3 / 32 
Motivation For This Work 
You want to read a document and follow its installation hints and as a result the 
software is basically running? Then continue reading this user manual.  
It is a guide through the installation of the GMLAN components, helps you to 
configure you application for the needs of GMLAN and gives you precious hints for 
the different requirements an ECU using GMLAN has to fulfill (PowerTrain, 
SingleWire CAN…). 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
WARNING 
All application code in any of the Vector User Manuals are for training 
purposes only. They are slightly tested and designed to understand the basic 
idea of using a certain component or a set of components.

--- Page 5 ---
User Manual  Startup with GMLAN  
2011, Vector Informatik GmbH  Version: 1.0.1 
 based of template version 2.0 
4 / 32 
Contents 
1 About this Document ...................................................................................... 7 
1.1 Legend and Explanation of Symbols .................................................. 7 
2 What is GMLAN ................................................................................................ 8 
2.1 Virtual Networks .............................................................................. 10 
3 Your ECU ........................................................................................................ 12 
3.1 Body Bus ECU ................................................................................. 12 
3.2 Infotainment ECU ............................................................................ 13 
3.3 PowerTrain ECU (or Chassis expansion or Powertrain 
expansion) ....................................................................................... 13 
4 GMLAN In 6 Steps ......................................................................................... 14 
4.1 STEP 1   Prepare Your Software Project ......................................... 15 
4.2 STEP 2   Configuration Tool GENy and DBC File ............................ 16 
4.2.1 Setting of Generation Paths ............................................................. 18 
4.2.2 Component Selection ...................................................................... 18 
4.2.3 Tree view – A List of all selected components .................................  18 
4.2.4 HW_<microcontroller> ..................................................................... 19 
4.2.5 Nm_Gmlan_Gm ............................................................................... 19 
4.2.6 Tp_Iso15765.................................................................................... 20 
4.2.7 Diagnostics – Diag_CanDesc_KWP ................................................ 20 
4.2.8 DrvCan_<microcontroller> ...............................................................  21 
4.2.9 Settings are Finished ....................................................................... 23 
4.3 STEP 3   Add Files to Your Application ............................................ 24 
4.4 STEP 4  Adaptations For Your Application ...................................... 24 
4.4.1 Includes ........................................................................................... 24 
4.4.2 Initialization ...................................................................................... 24 
4.4.3 Cyclic calls to keep the components running ................................... 25 
4.4.4 Provide Callback functions ...............................................................  25 
4.5 STEP 5  Compile And Link .............................................................. 27 
4.6 STEP 6  Test the Software Component ........................................... 27 
5 Further Information ....................................................................................... 28 
5.1 Full CAN Message Transmission with Extended Ids ........................ 28 
5.2 Take care when working with VNs ................................................... 28 
5.3 Validity of Signals ............................................................................ 29 
5.4 Signals assigned to different VNs and located in one message ....... 29

--- Page 6 ---
User Manual  Startup with GMLAN  
2011, Vector Informatik GmbH  Version: 1.0.1 
 based of template version 2.0 
5 / 32 
5.5 Source Learning for Single Wire CAN with Mixed Identifiers (11 
bit and 29 bit) ................................................................................... 30 
5.6 Activation and deactivation of VNs ................................................... 30 
5.6.1 IlNwmActivateVN( channel, VN) ...................................................... 30 
5.7 llNwmDeactivateVN ......................................................................... 30 
6 Index ................................................................................................................. 1

[… 26 further page(s) not extracted …]
