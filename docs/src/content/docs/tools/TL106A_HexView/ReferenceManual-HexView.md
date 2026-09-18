---
title: "Hex File Viewer Tooling — ReferenceManual HexView"
description: "Converted Portable Document (vendor or generated report) from ReferenceManual_HexView.pdf (PDF, 2373 KB)."
---

:::note
Converted from `TL106A_HexView/tools/ReferenceManual_HexView.pdf` (Portable Document (vendor or generated report); original PDF, about 2373 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL106A_HexView](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Reference Manual HexView 
2014, Vector Informatik GmbH Version: 1.08.06 
based on template version 5.1.0 
1 / 111 
 
 
 
 
 
 
 
 
 
 
 
HexView 
Reference Manual 
 
 
Version 1.08.06 
 
 
 
 
 
 
 
 
 
 
Authors Armin Happel 
Status Released

--- Page 2 ---
Reference Manual HexView 
2014, Vector Informatik GmbH Version: 1.08.06 
based on template version 5.1.0 
2 / 111 
Document Information 
History 
Author Date Version Remarks 
Vishp 2006-02-21 1.0 > Creation 
Vishp 2006-07-14 1.1 > Description of new features for V1.2.0 
> Main features are: 
> Support for Ford-VBF and Ford-IHex in 
dialogs 
> Compare-Feature 
> Auto-detect file format on file open/save 
Vishp 2006-09-27 1.2 > Description of new features for V1.3.0 
> Merge and compare uses now the auto-
filetype detection 
> Merge operation available from 
commandline 
> Address calculation from banked to linear 
addresses from commandline 
> Checksum calculation feature from 
commandline places results into file or data. 
Vishp 2006-12-07 1.3 > Description of new features for V1.4.0 
> Commandline: Checksum operates on 
selected section. Multiple checksum areas 
can be specified from the commandline. 
> Postbuild operation added 
> Fixing Ford IHex configuration problem for 
flashindicator and File-Browse in the dialog 
> Option /CR (cut-section) added to the 
commandline 
> Delete and  Cut&paste with internal 
clipboard added. 
> Description of the commandline processing 
order added to the document 
> Program returns a value depending on the 
status of operation 
> New option combination /XG with /MPFH to 
re-position existing NOAM to adjusted 
NOAR-fields 
> Goto start of a block (double-click to block 
descriptor)  
> Find ASCII string in data was added 
Vishp 2007-07-09 1.31 > Description of new features for V1.4.6 
> Support part number in GM-files (option /pn)

--- Page 3 ---
Reference Manual HexView 
2014, Vector Informatik GmbH Version: 1.08.06 
based on template version 5.1.0 
3 / 111 
from the commandline and reading the file 
Vishp 2007-09-19 1.4 > Description of new features for V1.5 
> Start CANflash from within Hexview 
> Create partial datafiles for Fiat-export 
> Support VBF V2.4 for Ford 
> Support Align Erase (/AE) 
> Use ranges instead of start and end address 
> Creation of a validation structure 
> New About-dialog with personalized license 
info 
Vishp 2008-01-31 1.5 > Fixing wrong description of checksum 
calculation for method 8 (see Table 3-3, 
index 8) 
Vishp 2009-05-19 1.6 > Description of new features for V1.6 
> Fixing problem when HEX-file contain 
addresses until 0xFFFF.FFFF 
> Extend expdatproc interface to allow 
insertion of data processing results into 
HEX-file 
> Now browse for data processing parameter 
file 
> Intel-HEX record length now adjustable 
> This document can now be opened from 
Help menu 
> Allow to select multiple post build files 
> Generate structured hex file from Eeprom 
data set 
> C-array generation supports structured list, 
Ansi-C and memmap. 
Vishp 2009-11-27 1.06.01 > Fixing problems with path names using a 
colon, e.g. “D:” 
> Minor corrections in the documentation 
(CRC calculation algorithms) 
Vishp 2010-10-11 1.06.04 > AccessParameter for Fiat export now 
editable. 
> Export binary blocks from commandline 
interface 
Vishp 2011-12-05 1.07.00 > Fixing Windows7 problems in dialogs. 
> Faster HEX read operation 
> Support dsPIC copy and ghost byte 
clearance 
> Export splitted binary data files per segment 
> Add checksum to last data bytes (@end)

--- Page 4 ---
Reference Manual HexView 
2014, Vector Informatik GmbH Version: 1.08.06 
based on template version 5.1.0 
4 / 111 
> Further support for compress+sign  
> Padding for data encryption 
> Scanning memory for EepM data (for 
development) 
> S5 records are now tolerated. 
> Swapping words or longwords 
Vishp 2012-09-15 1.08.00 > Solving further Win7 problems in dialogs. 
> Adding SHA256 in checksum and data 
processing DLL 
> Record type specifier in the commandline for 
Intel-HEX and Motorola S-Records. 
> Add import and Export for HEX ASCII data 
through commandline 
> Generate signature header for GM 
> Support for VBF V2.5 (Volvo) 
Vishp 2014-03-11 1.08.04 > Correcting padding mode for AES 
> Add support for IV-Vector w/ AES-CBC 
> Support for VBF V3.0 (Ford) 
> Improvements for the GM-header signature 
generation for cyber security. 
> Corrections on address range definition for 
data processing. 
> Ford-VBF allows now to omit the erase 
table. Editable now in the GUI. 
> Call to CANflash removed. 
> Description for validation structure 
generation added. 
> Support multiple part numbers for VBF 
> Merging files over commandline supports 
now wildcards. 
> Order of identifiers for VBF corrected. 
> Expdatproc V1.08.04 added 
> RSA encprytion/decryption byte order 
corrected. 
> Padding mode for AES corrected 
> IV can be specified explicitly for AES 
CBC in the parameter 
Vishp 2014-04-07 1.08.05 > Commandline option to export MIME coded 
files 
Vishp 2014-05-19 1.08.06 > Export/Import of GAC binary files

--- Page 5 ---
Reference Manual HexView 
2014, Vector Informatik GmbH Version: 1.08.06 
based on template version 5.1.0 
5 / 111 
Reference Documents 
No. Title 
[1] Fiat-Specification 07284-01, dated 2003-05-15 
[2] Ford/Volvo: Versatile Binary Format V2.2-V3.0 
[3] Ford: Module programming and Design specification, V2003.0 
[4] GM: GMW3110, V1.5, chapter 11 
 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 6 ---
Reference Manual HexView 
2014, Vector Informatik GmbH Version: 1.08.06 
based on template version 5.1.0 
6 / 111 
Contents 
1 Introduction ................................ ................................ ................................ .................. 12 
1.1 Important notes ................................ ................................ ................................ ...... 12 
1.2 Terminology ................................ ................................ ................................ ............ 13 
2 User Interface ................................ ................................ ................................ ............... 14 
2.1 With a Double Click to the Main Menu ................................ ................................ .... 15 
2.1.1 Edit a HEX data line ................................ ................................ ...................... 15 
2.1.2 Change the base address of a data block, erase it or jump directly to the 
beginning of the block data................................ ................................ ............ 15 
2.2 Menu ................................ ................................ ................................ ...................... 16 
2.2.1 Menu: “File” ................................ ................................ ................................ ... 16 
2.2.1.1 New ................................ ................................ ................................ ........ 16 
2.2.1.2 Open ................................ ................................ ................................ ...... 16 
2.2.1.2.1 Auto-file format analysing process ................................ ................... 16 
2.2.1.3 Merge ................................ ................................ ................................ ..... 17 
2.2.1.4 Compare ................................ ................................ ................................  18 
2.2.1.5 Save ................................ ................................ ................................ ....... 19 
2.2.1.6 Save as ................................ ................................ ................................ .. 19 
2.2.1.7 Log Commands ................................ ................................ ...................... 19 
2.2.1.8 Import ................................ ................................ ................................ ..... 19 
2.2.1.8.1 Import Intel-Hex/Motorola S-Record ................................ ................ 20 
2.2.1.8.2 Read 16-Bit Intel Hex................................ ................................ ....... 20 
2.2.1.8.3 Import binary data ................................ ................................ ............ 20 
2.2.1.8.4 Import HEX ASCII ................................ ................................ ............ 20 
2.2.1.8.5 Import GM data................................ ................................ ................ 20 
2.2.1.8.6 Import Fiat data ................................ ................................ ............... 20 
2.2.1.8.7 Import Ford IHex data ................................ ..................

[… 105 further page(s) not extracted …]
