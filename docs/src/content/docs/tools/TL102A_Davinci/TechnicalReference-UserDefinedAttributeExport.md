---
title: "DaVinci Configuration Support — TechnicalReference UserDefinedAttributeExport"
description: "Converted Technical Reference (vendor) from TechnicalReference_UserDefinedAttributeExport.pdf (PDF, 92 KB)."
---

:::note
Converted from `TL102A_Davinci/tools/Developer/Docs/TechnicalReference_UserDefinedAttributeExport.pdf` (Technical Reference (vendor); original PDF, about 92 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL102A_Davinci](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
User-defined attribute XML-export 
Technical Reference 
 
 
 
 
Version 1.3 
 
 
 
 
 
 
Authors: Michael Hoffmann, Andreas Claus 
Version: 1.3 
Status: released (in preparation/completed/inspected/released)

--- Page 2 ---
User-defined attribute XML-export Technical Reference  
 2012, Vector Informatik GmbH Version: 1.3 
  
History 
 
Author Date Version  Remarks 
Hn 2007-02-02 1.0 Document released 
Cs 2007-11-28 1.1 New document template; minor corrections 
Hn 2008-02-08 1.2 Document updated 
Cs 2012-04-11 1.3 DCF workspaces added; minor corrections 
 
Contents  
1 Overview ......................................... ................................................... ....................... 3
1.1 Terms and Acronyms ............................. ................................................... .. 3
2 User-defined attributes in DaVinci ............... ................................................... ........ 4
2.1 Creating user-defined attribute definition ..... ............................................... 4
2.2 User-defined attribute usage ................... ................................................... . 5
2.3 Creating the XML-export ........................ ................................................... .. 6
3 Design object reference .......................... ................................................... .............. 7
4 Attribute definition resolution .................. ................................................... ............ 8
4.1 Reference of global attribute definition values ............................................. 8
4.2 Reference of local attribute value ............. ...................................................  9
5 DCF Workspaces ................................... ................................................... .............. 10 
5.1 Global attribute definition file ............... ................................................... ... 10 
5.2 Loading attribute definitions .................. ................................................... . 10 
6 Contact .......................................... ................................................... ....................... 11

--- Page 3 ---
User-defined attribute XML-export Technical Reference  
 2012, Vector Informatik GmbH Version: 1.3 
  
1  Overview 
With the DaVinci Developer 2.1 and later user-defin ed attribute definitions can be 
exported. This document describes the usage of the exported XML file format. 
1.1 Terms and Acronyms 
Term Definition 
DaVinci DEV DaVinci Developer 
AR AUTOSAR – Automotive Open System Architecture 
GUI Graphical user interface 
DCF DaVinci configuration file workspace

--- Page 4 ---
User-defined attribute XML-export Technical Reference  
 2012, Vector Informatik GmbH Version: 1.3 
  
2 User-defined attributes in DaVinci 
DaVinci DEV are allows the definition of user-defined attributes for certain design elements 
visible within the GUI. 
The set of design elements which are providing the definition of user-defined attributes 
depends on the tool version. 
2.1 Creating user-defined attribute definition 
To create a user-defined attribute definition open the workspace global attribute definition 
table available on the main menu ‘View /barb2right Attribute Definition…’. 
Each user-defined attribute is related to a DaVinci  object type and must have a name 
which is unique in the scope of the attribute definition table. 
The definition of minimum, maximum, and default val ue depends on the selected value 
type 
 
Figure 1: Definition of user-defined attribute

--- Page 5 ---
User-defined attribute XML-export Technical Reference  
 2012, Vector Informatik GmbH Version: 1.3 
  
2.2 User-defined attribute usage 
Attribute definitions can be used at certain design  objects of the workspace. For each 
attribute which is defined within the global attrib ute table and associated with the object 
type of the design object, a local value definition can be specified.  
These values are specific for each design object an d are available in the properties dialog 
of the design object. 
A design object can only use those user-defined att ributes which are defined within the 
global attribute definition table. 
 
Figure 2: Definition of a local value of a user-defined attribute

--- Page 6 ---
User-defined attribute XML-export Technical Reference  
 2012, Vector Informatik GmbH Version: 1.3 
  
2.3 Creating the XML-export 
The export of user-defined attributes is always rel ated to a preceded export of design 
elements. The export can be used with all supported AR versions. 
To create the XML export, select the appropriate de sign element within DaVinci DEV and 
choose the ‘XML Export…’ command from the context menu. 
The export dialog provides an option ‘Export user-d efined attributes’. If this option is 
selected an additional XML output file will be crea ted. The name of the XML file is 
automatically created by using the name of the AR-X ML output file plus the extension 
‘_gen_attr’ (e.g. ‘System_gen_attr.xml’). 
 
 
Figure 3: User-defined attribute export option for XML-exports

[… 5 further page(s) not extracted …]
