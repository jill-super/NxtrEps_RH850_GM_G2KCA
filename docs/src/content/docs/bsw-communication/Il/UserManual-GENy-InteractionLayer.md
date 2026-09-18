---
title: "Interaction Layer (Signal Communication) — UserManual GENy InteractionLayer"
description: "Converted User Manual / User Guide from UserManual_GENy_InteractionLayer.pdf (PDF, 340 KB)."
---

:::note
Converted from `Il/doc/UserManual_GENy_InteractionLayer.pdf` (User Manual / User Guide; original PDF, about 340 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Il](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Vector Informatik GmbH, Ingerheimer Str. 24, 70499 Stuttgart 
Tel. 0711/80670-0, Fax 0711/80670-399, Email can@vector-informatik.de 
Internet http:\\www.vector-informatik.de  
 
 
 
 
 
 
 
 
 
 
 
Interaction Layer 
with GENy 
User Manual 
(Your First Steps) 
 
 
Version 1.03.01

--- Page 2 ---
User Manual  Interaction Layer  
 2007, Vector Informatik GmbH  Version: 1.03.01 
 based on template version 1.8 
1 / 35  
 
 
 
 
 
 
 
Authors: Klaus Emmert 
Version: 1.03.01 
Status: released (in preparation/completed/inspected/released)

--- Page 3 ---
User Manual  Interaction Layer  
 2007, Vector Informatik GmbH  Version: 1.03.01 
 based on template version 1.8 
2 / 35  
History 
Author Date Version Remarks 
Klaus Emmert 2004-04-29 1.00 Converted from Version 0.8 to 
new User Manual Layout.  
Klaus Emmert 2004-05-17 1.1 Usage of vstdlib added (started with 
IL version 1.83)  
Klaus Emmert 2005-06-24 1.02 GENy added as new 
Configuration Tool. 
Gunnar Meiss 2007-05-16 1.03 ESCAN00020395 
Gunnar Meiss 2007-07-12 1.03.01 ESCAN00021408 Update 
Contents

--- Page 4 ---
User Manual  Interaction Layer  
 2007, Vector Informatik GmbH  Version: 1.03.01 
 based on template version 1.8 
3 / 35  
Motivation For This Work 
What is a signal?  
A Signal is an abstract container for information. It can hold physical values, states 
or commandos. Signals can concern the complete vehi cle or only some control 
units.  
Using the Interaction Layer you do not have to take  care about the transmission or 
reception of signal or the data consistency. If you  need the content of a signal, just 
read it, if a value changed, just write it. All the rest is done by the Interaction Layer. 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
WARNING 
All application code in any of the Vector User Manu als is for training 
purposes only. They are slightly tested and designed to understand the basic 
idea of using a certain component or a set of components.

--- Page 5 ---
User Manual  Interaction Layer  
 2007, Vector Informatik GmbH  Version: 1.03.01 
 based on template version 1.8 
4 / 35  
Contents  
1 Welcome to the Interaction Layer User Manual............................................. 7 
1.1  Beginners with the Interaction Layer start here?................................ 7 
1.2  For Advanced Users................................. ......................................... 7 
1.3  Special topics .................................................................................... 7 
1.4  Additional Documents dealing with the Interaction Layer ................... 7 
2 About This Document ................................................................................... .. 8 
2.1  How This Documentation Is Set-Up ................................................... 8 
2.2  Legend and Explanation of Symbols.................................................. 9 
3 Interaction Layer – An Overall View ............................................................. 10  
3.1  Transmission problems.............................. ...................................... 10  
3.1.1  What is left to do for transmission................ .................................... 10  
3.2  Reception problems................................. ........................................ 11  
3.2.1  What is left to do for Reception................... ..................................... 11  
3.3  Tools And Files.................................... ............................................ 11  
3.3.1  The data base file (DBC file)...................... ...................................... 11  
3.3.2  Configuration Tool ........................................................................... 12  
3.3.3  Generation Process with CANbedded Software Component ........... 12  
3.4  What Is the Vector Interaction Layer................................................ 14  
3.5  What The Interaction Layer Does .................................................... 14  
4 This Component – A More Detailed View..................................................... 15  
4.1  Files to form the Interaction Layer.................................................... 15  
4.1.1  Fix files that form the Interaction Layer ............................................ 15  
4.1.2  Generated files that must not be changed, too................................. 15  
4.1.2.1  Configuration Tool GENy............................ ..................................... 15  
4.1.3  Configurable files................................. ............................................ 15  
4.1.4  il.c............................................... ................................................... .. 15  
4.1.5  il_def. h.......................................... .................................................. 15  
4.1.6  Il_par.c........................................... .................................................. 15  
4.1.7  il_par.h........................................... .................................................. 15  
4.1.8  il_cfg.h........................................... .................................................. 16  
4.1.9  il_inc.h ............................................................................................. 16  
4.1.9.1  Vstdlib.c / vstdlib.h.............................. ............................................. 16  
4.1.10  Includes when using GENy........................... ................................... 16  
4.2  Handling of the Interaction Layer ..................................................... 16  
5 A Basically Running Interaction Layer In 7 Steps....................................... 18

--- Page 6 ---
User Manual  Interaction Layer  
 2007, Vector Informatik GmbH  Version: 1.03.01 
 based on template version 1.8 
5 / 35  
5.1  STEP 1  Unpack the delivery ........................................................... 19  
5.2  STEP 2  Configuration Tool and DBC File ....................................... 20  
5.2.1  Working with the Configuration Tool GENy...................................... 21  
5.2.1.1  Project Setup in GENy.............................. ....................................... 21  
5.2.1.2  Interaction Layer Settings in GENy................. ................................. 21  
5.3  STEP 3  Generate Files............................. ...................................... 23  
5.4  STEP 4  Add Files to Your Application............................................. 24  
5.4.1  Using GENy......................................... ............................................ 24  
5.5  STEP 5 Adaptations For Your Application ....................................... 25  
5.6  STEP 6 Compile And Link ............................................................... 28  
5.7  STEP 7 Test the Software Component ............................................ 28  
5.7.1  Built-up of the test environment ....................................................... 28  
5.7.2  Test of Interaction Layer .................................................................. 29  
6 Further Information ................................................................................... .... 31  
6.1  States of the Interaction Layer ......................................................... 31  
6.2  Debugging of Interaction Layer..................... ................................... 31  
6.3  Where to get the generated names for the macros and 
functions.......................................... ................................................ 32  
6.4  Usage of flags and functions............................................................ 32  
6.5  Data Consistency ............................................................................ 33  
7 Index.............................................. ................................................... ................ 1

[… 29 further page(s) not extracted …]
