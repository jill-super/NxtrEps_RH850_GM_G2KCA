---
title: "Universal Measurement and Calibration Protocol — UserManual XCP"
description: "Converted User Manual / User Guide from UserManual_XCP.pdf (PDF, 577 KB)."
---

:::note
Converted from `Xcp/doc/UserManual_XCP.pdf` (User Manual / User Guide; original PDF, about 577 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Xcp](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Vector Informatik GmbH, Ingerheimer Str. 24, 70499 Stuttgart 
Tel. 0711/80670-0, Fax 0711/80670-399, Email can@vector.com 
Internet http:\\www.vector.com 
 
 
 
 
 
 
 
 
 
 
 
XCP - Universal 
Measurement and 
Calibration Protocol 
User Manual 
(Your First Steps) 
 
 
Version 1.0.2

--- Page 2 ---
User Manual  XCP - Universal Measurement and Calibration Protocol  
©2011, Vector Informatik GmbH   Version: 1.0.2 
1/  2 7
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
Authors: Klaus Emmert 
Version: 1.0.2 
Status: Released (in preparation/completed/inspected/released)

--- Page 3 ---
User Manual  XCP - Universal Measurement and Calibration Protocol  
©2011, Vector Informatik GmbH   Version: 1.0.2 
2/  2 7
Motivation For This Work 
The motivation for using the XCP Software Component is very simple. XCP is the 
component that helps you to look in the E CU, to display values or set them. And 
that is all working just via the underly ing bus system as CA N, Ethernet, …you do 
not need any development environment. 
Together with CANape you ha ve a great choice of how the data could be 
displayed. 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
WARNING 
All application code in any of the V ector User Manuals are for training 
purposes only. They are slightly tested and designed to understand the basic 
idea of using a certain component or a set of components.

--- Page 4 ---
User Manual  XCP - Universal Measurement and Calibration Protocol  
©2011, Vector Informatik GmbH   Version: 1.0.2 
3/  2 7
Contents 
1 Welcome to the XCP User Manual ...............................................................6 
1.1 Beginners with XCP start here ? .....................................................6 
1.2 For Advanced Users ....................................................................... 6 
1.3 Special topics ..................................................................................6 
1.4 Documents this one refers to…....................................................... 6 
2 About This Document ...................................................................................7 
2.1 How This Documentation Is Set-Up ................................................7 
2.2 Legend and Explanation of Symbols............................................... 7 
3 XCP Software Component – An Overall View............................................. 8 
3.1 What Is XCP.................................................................................... 8 
3.2 What Is the XCP Component ..........................................................8 
3.3 Tools And Files – The Generation Tool .......................................... 8 
3.4 What The Component Does............................................................ 9 
4 XCP – A More Detailed View....................................................................... 11 
4.1 Basic Mechanism of the XCP........................................................ 11 
4.2 Measurement Modes .................................................................... 11 
4.2.1 Using XCP In Polling Mode........................................................... 11 
4.2.2 Using XCP For Data Acquisition / Event .......................................12 
5 XCP IN 8 STEPS........................................................................................... 13 
5.1 STEP 1  Installation Of The Tool................................................... 14 
5.2 STEP 2  Extract CANbedded Software Components ................... 14 
5.3 STEP 3  Configuration With The Generation Tool (GENy) ........... 15 
5.4 STEP 4  Generate Files ................................................................ 16 
5.5 STEP 5 Add CANbedded To Your Project.................................... 17 
5.6 STEP 6 Adapt Your Application Files............................................ 18 
5.6.1 Including, Initialization And Cyclic Calls ........................................18 
5.6.2 Connect your application to the XCP ............................................ 18 
5.7 STEP 7 Compile And Link Your Project........................................ 19 
5.8 STEP 8 Test It Via CANape ..........................................................20 
6 Further Information .....................................................................................22 
6.1 Settings For Using The Data Acquisition Mode / Events .............. 22 
7 List Of Experiences..................................................................................... 25 
7.1 Topic 1 .......................................................................................... 25

--- Page 5 ---
User Manual  XCP - Universal Measurement and Calibration Protocol  
©2011, Vector Informatik GmbH   Version: 1.0.2 
4/  2 7
8 Index ...............................................................................................................1

--- Page 6 ---
User Manual  XCP - Universal Measurement and Calibration Protocol  
©2011, Vector Informatik GmbH   Version: 1.0.2 
5/  2 7
Illustrations 
Figure 3-1 CANbedded Software Components Together With The XCP 
Component................................................................................................... 8 
Figure 3-2 Generation Process For Vector CANbedded Software Components .......... 9 
Figure 4-1 Visualization Of Data Using CANape......................................................... 11 
Figure 4-2 XCP Polling Mode Using Two Messages................................................... 12 
Figure 4-3 XCP Event Mode........................................................................................ 12 
Figure 5-1 8 Steps to CANdesc................................................................................... 13 
Figure 5-2 Configuration In The Generation Tool For Basic XCP Usage.................... 15 
Figure 5-3 Set Driver Configuration In CANape .......................................................... 20 
Figure 5-4 XCP Driver Settings ................................................................................... 20 
Figure 5-5 Settings For XCP On CAN ......................................................................... 21 
Figure 5-6 ECU Is Online ............................................................................................ 21 
Figure 6-1 Components / XCP .................................................................................... 22 
Figure 6-2 Components / XCP .................................................................................... 22 
Figure 6-3 Components / XCP .................................................................................... 23 
Figure 6-4 Edit Measurement List In CANape............................................................. 24

[… 21 further page(s) not extracted …]
