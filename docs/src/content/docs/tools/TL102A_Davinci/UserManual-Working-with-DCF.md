---
title: "DaVinci Configuration Support — UserManual Working with DCF"
description: "Converted User Manual / User Guide from UserManual_Working_with_DCF.pdf (PDF, 499 KB)."
---

:::note
Converted from `TL102A_Davinci/tools/Developer/Docs/UserManual_Working_with_DCF.pdf` (User Manual / User Guide; original PDF, about 499 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL102A_Davinci](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Working with DCF 
User Manual 
 
 
 
 
Version 1.6 
 
 
 
 
 
 
Authors: Matthias Wernicke, Andreas Claus, Stefanie Kruse  
Version: 1.6 
Status: released (in preparation/completed/inspected/released)

--- Page 2 ---
User Manual Working with DCF  
 2012, Vector Informatik GmbH Version: 1.6 
  
1 History 
Author Date Version Remarks 
Wk 2008-02-07  0.1  Initial version 
Wk 2008-02-08  0.2 Additional remark in ch. 5.1 
Wk 2008-03-27  1.1 
Ch. 6.2 “Handling of read-only objects” added. 
Ch. 5.1 “Creating a new DCF” updated. Ch. 7 
“Limitations” added. Released. 
Cs 2008-04-17  1.2 
Ch. 4 “Relative path handling” added 
Ch. 7 “Limitations” updated 
Ske 2009-02-08  1.3 Ch.7 “DCFUtility” added. “Limitations” removed. 
Wk 2011-01-10  1.4 Harmonized with UserManual_DataImport.pdf  
Wk 2011-08-12  1.5 Ch. 6.2 updated. Screenshots updated. 
Wk 2012-06-15  1.6 Obsolete terms and limitations removed.

--- Page 3 ---
User Manual Working with DCF  
 2012, Vector Informatik GmbH Version: 1.6 
  
Contents  
1 History .............................................................................................. ......................... 2 
2 About this Document .................................................................................. ............. 5 
2.1  Abbreviations and Items used in this Document ......................................... 5 
3 Introduction ...................................... ................................................... ..................... 6 
3.1  What is a DaVinci Developer Workspace? .................................................. 6 
3.2  What is a DaVinci Configuration File? ......................................................... 6 
4 DCF storage format ................................................................................... ............... 7 
5 Working with DCF ..................................................................................... .............. 11  
5.1  Creating a new DCF ................................................................................. 11  
5.2  Opening an existing DCF .......................................................................... 12  
5.3  Exporting a DCF ...................................................................................... . 13  
5.4  Importing a DCF ...................................................................................... . 14  
5.5  Converting a DEV into a DCF (or vice versa) ............................................ 14  
6 Using DCF as interface to a CM system ................................................................  15  
6.1  General concept ...................................................................................... . 15  
6.2  Handling of read-only objects ................................................................... 16  
7 Working with DaVinci Configuration File Utility ................................................... 18  
7.1 Installation ......................................................................................... ....... 18  
7.1.1  Setup program ........................................................................................ .. 18  
7.1.2  Licensing ............................................................................................ ...... 18  
7.2  Starting DaVinci Configuration File Utility .................................................. 18  
7.3  Open DCF workspace .............................................................................. 20  
7.4  DCF workspace ........................................................................................  21  
7.4.1  Content of a DCF workspace .................................................................... 21

--- Page 4 ---
User Manual Working with DCF  
 2012, Vector Informatik GmbH Version: 1.6 
  
7.4.2  Missing files ........................................................................................ ...... 22  
7.5  DCB files of a DCF workspace ................................................................. 23  
7.5.1  Content of DCB files .................................................................................  23  
7.5.2  Corrupt DCB files .................................................................................... .. 23  
7.6  Compare AUTOSAR files of DCF workspaces .......................................... 25  
7.7  Command line usage of comparison ......................................................... 26  
8 Tips and Tricks ...................................................................................... ................. 27  
8.1  When to use DEV or DCF? ....................................................................... 27  
8.2  Working with temporary DEV .................................................................... 27  
9 Contact .............................................................................................. ...................... 28  
 
Illustrations 
Figure 4-1: Granularity of the design objects in a DCF ........................................................... 8 
Figure 4-2: Folder structure of a DCFP ............................................................... ................... 8 
Figure 4-3: Example DCF .............................................................................. ...................... 10  
Figure 6-1: Using DCF with a CM system ............................................................... ............. 16

--- Page 5 ---
User Manual Working with DCF  
 2012, Vector Informatik GmbH Version: 1.6 
  
2 About this Document 
Besides the traditional DaVinci Developer Workspace  (DEV), DaVinci Developer supports 
an alternative storage format for the design data: the DaVinci Configuration File (DCF). 
This document describes when to use DCFs and how to work with DCFs. 
2.1 Abbreviations and Items used in this Document 
DEV DaVinci Developer Workspace 
DCF DaVinci Configuration File 
DCFP DaVinci Configuration File Package 
DCFE DaVinci Configuration File Element 
CM Configuration Management

--- Page 6 ---
User Manual Working with DCF  
 2012, Vector Informatik GmbH Version: 1.6 
  
3 Introduction 
Design data created with DaVinci Devloper need to b e persistently stored. You may 
choose among the following storage formats: 
 
/square6 DaVinci Developer Workspace (DEV) 
/square6 DaVinci Configuration File (DCF) 
Both formats have their specific advantages. Depend ing on your use cases you should 
decide which format is appropriate for you. 
3.1 What is a DaVinci Developer Workspace? 
The DaVinci Developer Workspace is the native XML b ased storage format of DaVinci 
Developer. This storage format is optimized to achi eve a fast loading and saving time of 
the design data. 
The detailed storage format is proprietary and migh t be changed by Vector without notice 
in future DaVinci versions. Of course, loading of o ld workspaces is always possible with a 
newer DaVinci version. 
3.2 What is a DaVinci Configuration File? 
The DaVinci Configuration File is an alternative st orage format of DaVinci Developer. This 
format is appropriate for cooperative working with DaVinci Developer and any external CM 
system with a file-based interface. You may use DaV inci Developer as authoring tool for 
the design data, and you may use the CM system to m anage the design data in a 
repository. This gives you the maximum degree of fr eedom to use the CM system’s 
features like versioning, branching or merging file s. To ensure long term readability of old 
design data in the CM system, the DCF concept avoids proprietary formats where possible 
and uses standardized AUTOSAR XML formats instead.

[… 22 further page(s) not extracted …]
