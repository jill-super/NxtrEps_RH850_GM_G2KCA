---
title: "Controller Area Network Driver — UserManual CanDriver"
description: "Converted User Manual / User Guide from UserManual_CanDriver.pdf (PDF, 696 KB)."
---

:::note
Converted from `Can/doc/UserManual_CanDriver.pdf` (User Manual / User Guide; original PDF, about 696 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Can](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Vector Informatik GmbH, Ingersheimer Str. 24, 70499 Stuttgart 
Tel. 0711/80670-0, Fax 0711/80670-399, Email can@vector-informatik.de 
Internet http:\\www.vector-informatik.de 
 
 
 
 
 
 
 
 
 
 
 
Vector CAN Driver 
User Manual 
(Your First Steps) 
 
 
Version 2.4

--- Page 2 ---
User Manual  Vector CAN Driver  
©2009, Vector Informatik GmbH  Version: 2.4 
 based of template version 1.7 
2/  5 6
 
 
 
 
 
 
CAN Driver
CAN Controller
Message Transmission - Reception
CAN
Transceiver
Higher layer components
 
 
 
 
 
 
 
 
 
Authors: Klaus Emmert 
Version: 2.4 
Status: released (in preparation/completed/inspected/released)

--- Page 3 ---
User Manual  Vector CAN Driver  
©2009, Vector Informatik GmbH  Version: 2.4 
 based of template version 1.7 
3/  5 6
History 
Author Date Version Remarks 
Klaus Emmert 2001-05-11 0.1 First version of the User Manual 
Klaus Emmert 2001-08-11 0.4 Technical and linguistic revision 
Klaus Emmert 2001-09.21 0.6 Revision (pretransmit) 
Klaus Emmert 2001-10-10 0.6a Error in description of a mes-
sage, how to enter the manufac-
turer type to the example data 
base. 
Klaus Emmert 2001-12-14 1.0 Linguistic revision 
Klaus Emmert 2002-09-25 1.4 Linguistic corrections and little 
adaptations 
Klaus Emmert 2003-07-16 1.5 Warning added for example code 
usage 
Klaus Emmert 2004-10-26 1.6 New Layout, example dbc file 
deleted and description modified, 
description for CANgen and the 
new Generation Tool GENy, new 
Symbols 
Klaus Emmert 2006-05-30 1.7 Updated dialog for bus timing 
register setup 
Klaus Emmert 2006-09-08 1.8 Page number of Index, headline 
numbering 
Klaus Emmert 2007-02-20 1.9 Issues in Word Hyperlinks 
Klaus Emmert 2007-07-26 2.0 Issues in steps introduction, 
some typos. 
Klaus Emmert 2007-09-06 2.1 Typos and reference in TOC 
Klaus Emmert 2007-10-29 2.2 Baudrate setting description 
Klaus Emmert 2008-09-04 2.3 Include file for CAN Driver and  
GENy 
Klaus Emmert 2009-08-26 2.4 Fix: v_inc.h must not be changed 
manually.

--- Page 4 ---
User Manual  Vector CAN Driver  
©2009, Vector Informatik GmbH  Version: 2.4 
 based of template version 1.7 
4/  5 6
Motivation For This Work 
The CAN Driver is the only component  among the CANbedded Software Compo-
nents that is directly connec ted with the CAN Controller hardware. It is the founda-
tion for all other CANbedded Software Components. 
The first target for you is to get the CAN Driver running, to see receive and transmit 
messages on the bus.  
 
 
 
 
 
 
 
 
 
 
 
 
 
WARNING 
All application code in any of the Vect or User Manuals is for training pur-
poses only. They are slightly tested and designed to understand the basic 
idea of using a certain component or a set of components.

--- Page 5 ---
User Manual  Vector CAN Driver  
©2009, Vector Informatik GmbH  Version: 2.4 
 based of template version 1.7 
5/  5 6
Contents 
1 Welcome to the CAN Driver User Manual ....................................................... 8 
1.1 Beginners with the CAN Driver start here ? ........................................8 
1.2 For Advanced Users ........................................................................... 8 
1.3 Special topics ......................................................................................8 
1.4 Documents this one refers to…........................................................... 8 
2 About This Document .......................................................................................9 
2.1 How This Documentation Is Set-Up ....................................................9 
2.2 Legend and Explanation of Symbols................................................. 10 
3 ECUs and Vector CANbedded Components – An Overall View.................. 11 
3.1 Network Data Base File (DBC) ......................................................... 11 
4 CANbedded Software Components............................................................... 12 
4.1 Generation Tool ................................................................................ 13 
4.2 The Vector CAN Driver ..................................................................... 14 
4.2.1 Tasks of The Vector CAN Driver....................................................... 14 
4.2.2 Vector CAN Driver Files ....................................................................14 
4.2.2.1 Component Files ...............................................................................14 
4.2.2.2 Generated Files................................................................................. 14 
4.2.2.3 Configurable files .............................................................................. 15 
4.2.3 Include The CAN Driver Into Your Application ..................................15 
5 Vector CAN Driver– A More Detailed View.................................................... 16 
5.1 Information Package on the CAN Bus .............................................. 16 
5.2 Storing Information Packages ...........................................................17 
5.2.1 The Registers of the CAN Controller................................................. 18 
5.2.2 The Data Structure Generated by the Generation Tool for 
Storing Message Data....................................................................... 18 
5.2.3 Memory the Application Reserved for Signals. .................................19 
6 CAN Driver in 9 Steps ..................................................................................... 20 
6.1 STEP 1  Unpack the Delivery............................................................ 21 
6.2 STEP 2  Generation Tool and dbc File ............................................. 22 
6.2.1 Using CANgen as Generation Tool................................................... 22 
6.2.2 Using GENy, the new Generation Tool .............................................30 
6.3 STEP 3  Generate Files ....................................................................33 
6.3.1 Using CANgen Generation Tool........................................................ 33 
6.3.2 Using GENy ...................................................................................... 33

--- Page 6 ---
User Manual  Vector CAN Driver  
©2009, Vector Informatik GmbH  Version: 2.4 
 based of template version 1.7 
6/  5 6
6.4 STEP 4  Add Files to your Application ..............................................35 
6.5 STEP 5 Adaptations for your Application ..........................................36 
6.6 STEP 6 Compile, Link and Download ...............................................40 
6.7 STEP 7 Receiving A Message ..........................................................40 
6.8 STEP 8 Sending a Message .............................................................43 
6.9 STEP 9 Further Actions .................................................................... 45 
6.9.1 Strategies for Receiving a CAN Message......................................... 45 
6.9.1.1 Hardware Filter (HW Filter) ...............................................................45 
6.9.1.2 ApplCanMsgReceived....................................................................... 46 
6.9.1.3 Ranges.............................................................................................. 46 
6.9.1.4 Search Algorithm............................................................................... 46 
6.9.1.5 Precopy .............................................................................................46 
6.9.1.6 Indication Flag / Indication Function.................................................. 47 
6.9.2 Strategies for Sending a CAN Message ........................................... 48 
6.9.2.1 Update RAM buffer ........................................................................... 48 
6.9.2.2 CanTransmit...................................................................................... 49 
6.9.2.3 The Queue ........................................................................................49 
6.9.2.4 Pretransmit Function .........................................................................49 
6.9.2.5 Confirmation Function and Confirmation Flag................................... 49 
7 Further Information .........................................................................................51 
7.1 An Exercise For Practice................................................................... 51 
7.2 The Solution To The Exercise........................................................... 54 
7.2.1 After the first reception and transmission of a new value:................. 54 
7.2.2 After the reception of the same value as before: .............................. 54 
7.2.3 The solution, step by step .................................................................54 
8 Index .................................................................................................................56

[… 50 further page(s) not extracted …]
