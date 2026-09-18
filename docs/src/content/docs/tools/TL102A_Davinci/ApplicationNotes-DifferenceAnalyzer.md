---
title: "DaVinci Configuration Support — ApplicationNotes DifferenceAnalyzer"
description: "Converted Portable Document (vendor or generated report) from ApplicationNotes_DifferenceAnalyzer.pdf (PDF, 370 KB)."
---

:::note
Converted from `TL102A_Davinci/tools/Developer/Docs/ApplicationNotes_DifferenceAnalyzer.pdf` (Portable Document (vendor or generated report); original PDF, about 370 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL102A_Davinci](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
DaVinci Difference Analyzer 
Application Note 
 
 
 
 
Version 1.7 
 
 
 
 
 
 
Authors: Stefanie Kruse, Matthias Wernicke, Andreas 
Claus, Daniel Fürderer 
Version: 1.7 
Status: released

--- Page 2 ---
DaVinci Difference Analyzer Application Note  
 2015, Vector Informatik GmbH Version: 1.7 
  
History 
 
Author Date Version  Remarks 
Ske 2009-05-20 1.0 Initial version 
Ske 2009-06-10 1.1 Description of starting DaVinci Difference Analyzer enhanced 
Wk 2009-07-29 1.2 Document restructured and completed 
Cs 2011-06-28 1.3 Description of filter options added 
Dfr 2012-01-24 1.4 Updated figures and added description of view options (3.6), 
Parent Path (3.7) and DPA compare (3.8) 
Cs 2012-05-02 1.5 Additional Copyrights added 
Dfr 2014-01-28 1.6 Added description of ‘Filter equal elements’ option (3.5.2 and 4) 
Cs 2015-05-28 1.7 Usage of Saxon-PE distributable package

--- Page 3 ---
DaVinci Difference Analyzer Application Note  
 2015, Vector Informatik GmbH Version: 1.7 
  
Contents  
1 Overview ............................................................................................. ...................... 5 
2 Installation ......................................................................................... ....................... 6 
2.1  Setup program ........................................................................................ .... 6 
2.2  Licensing ............................................................................................ ........ 6 
3 Using DaVinci Difference Viewer ...................................................................... ....... 7 
3.1  Starting the difference analysis ................................................................... 7  
3.2  Display of the differences ...........................................................................  8 
3.3  Saving the result of a difference analysis .................................................... 9 
3.4  Opening the result file of a difference analysis ............................................ 9 
3.5  Filter Options ....................................................................................... ....... 9 
3.5.1  Element Identification ...............................................................................  10  
3.5.2  Filter equal elements ................................................................................  11  
3.5.3  Element Filter ....................................................................................... .... 11  
3.5.4  Loading/Storing Options ........................................................................... 11  
3.6  View Options ......................................................................................... ... 11  
3.7  Parent path changes ................................................................................ 12  
3.8  Comparing DPA Projects .......................................................................... 12  
3.8.1  Starting the difference analysis ................................................................. 12  
3.8.2  Result Overview ...................................................................................... . 12  
4 Command line usage ................................................................................... .......... 14  
5 Result file .......................................................................................... ...................... 15  
6 Additional Copyrights ................................................................................ ............ 17  
6.1  Saxon-HE ............................................................................................. .... 17  
6.1.1  IKVM Runtime ......................................................................................... . 17

--- Page 4 ---
DaVinci Difference Analyzer Application Note  
 2015, Vector Informatik GmbH Version: 1.7 
  
7 Contact .............................................................................................. ...................... 18

--- Page 5 ---
DaVinci Difference Analyzer Application Note  
 2015, Vector Informatik GmbH Version: 1.7 
  
1  Overview 
This document explains the usage of the command lin e tool “DaVinci Difference Analyzer” 
Version 2.7 and tells how to interpret the result.  
 
DaVinci Difference Analyzer compares two ARXML file s and puts the result into a result 
file. Additionally you can compare two DaVinci Proj ect Assistant projects by their DPA 
files. For further information on DPA compare see chapter 3.8.

--- Page 6 ---
DaVinci Difference Analyzer Application Note  
 2015, Vector Informatik GmbH Version: 1.7 
  
2 Installation 
2.1 Setup program 
The DaVinci Difference Analyzer can be installed by  starting the setup program 
DaVinciDiff.msi. This setup is part of a DaVinci to ol setup and is installed during the tool 
installation procedure. 
The DaVinci Difference Analyzer is installed into one of the following folders: 
n  English Windows: C:\Program Files\Common Files\Vector 
n  German Windows: C:\Programme\Gemeinsame Dateien\Vector 
The following executables are installed in the sub-folder “DiffAnalyzer”: 
n  DVDiffSys.exe: Command line program for comparing AUTOSAR XML files 
(System Description files, Software Component Description files or ECU 
Configuration Description files) 
n  DVDiffView.exe: Program for displaying the differences between two AUTOSAR 
XML files 
2.2 Licensing 
In order to run DaVinci Difference Analyzer a license of at least one of the following tools is 
required on the PC: 
n  DaVinci Configurator Pro 
n  DaVinci Developer

[… 12 further page(s) not extracted …]
