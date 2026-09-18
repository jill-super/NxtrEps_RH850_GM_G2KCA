---
title: "DaVinci Configuration Support — UserManual DataImport"
description: "Converted User Manual / User Guide from UserManual_DataImport.pdf (PDF, 118 KB)."
---

:::note
Converted from `TL102A_Davinci/tools/Developer/Docs/UserManual_DataImport.pdf` (User Manual / User Guide; original PDF, about 118 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL102A_Davinci](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Data Import 
User Manual 
 
 
 
 
Version 2.0 
 
 
 
 
 
 
Authors: Matthias Wernicke 
Version: 2.0 
Status: released (in preparation/completed/inspected/released)

--- Page 2 ---
User Manual Data Import  
2011, Vector Informatik GmbH Version: 2.0 
  
1 History 
Author Date Version Remarks 
Wk 2009-08-27  1.0  Initial version 
Wk 2011-01-07  2.0 
Document scope extended: description of 
general import mechanisms, description of 
special import functions completed 
 
Contents  
1 History....................................................................................................................... 2 
2  About this Document ............................................................................................... 3 
3 Use Cases ................................................................................................................. 4 
4  Approach .................................................................................................................. 6 
4.1  Definition of import mode via difference analysis ........................................ 7 
4.2  Interactive definition of import mode ........................................................... 8 
4.3  Preset of import mode (automatic merge)................................................... 8 
4.3.1  Preparation of workspace........................................................................... 8 
4.3.2  Automatic pre-setting of import mode for new imported objects.................. 9 
4.3.3  Resulting behavior of DaVinci Developer.................................................... 9 
5 Special Import Functions......................................................................................... 9 
5.1 Overwrite Import Mode Preset.................................................................. 10  
5.2  Update Diagnostic Configuration .............................................................. 11  
6 Contact.................................................................................................................... 12

--- Page 3 ---
User Manual Data Import  
2011, Vector Informatik GmbH Version: 2.0 
  
2 About this Document 
This document describes the specific features of DaVinci Developer for importing data 
according to the AUTOSAR SWC Template. It is applicable for the import of AUTOSAR 
XML files or DCF files (DaVinci Configuration File).   
For details about the import function for the ECU Configuration Template, please see 
TechnicalReference_EcuConfigurationFiles.pdf. 
Abbreviations and Items used in this Document: 
SWC Software Component 
PIM Per-Instance Memory

--- Page 4 ---
User Manual Data Import  
2011, Vector Informatik GmbH Version: 2.0 
  
3 Use Cases 
The specific import/update features of DaVinci Developer are relevant for scenarios, where 
several involved persons (e.g. the OEM and the TIER1) both contribute SWC design 
artifacts to the overall project. 
 
Figure 1 shows an example, where the TIER1 needs to integrate a SWC of the OEM 
 
/square6 OEM defines an atomic component type with some port prototypes (A). OEM exports 
the component type and passes it to the TIER1 
/square6 TIER1 imports the component type, and integrates it as component prototype into a 
composition type, which already has some other component prototypes and port 
prototypes (red color in B). 
/square6 OEM changes the atomic component type, e.g. by adding some port prototypes and 
removing others (C). OEM exports the component type and passes it to the TIER1 
/square6 TIER1 imports the component type, and expects that the changes of the OEM are 
incorporated (D)

--- Page 5 ---
User Manual Data Import  
2011, Vector Informatik GmbH Version: 2.0 
  
SWC2 
Composition1 
SWC1 
SWC2 
SWC2 
Composition1 
SWC1 
SWC2 
OEM Workspace TIER1 Workspace 
A B
C D  
Figure 1: Import/Update Example 1 
 
 
 
 
Figure 2 shows an example, where the TIER1 needs to extend a composition of the OEM 
 
/square6 OEM defines a composition type with some port prototypes and component 
prototypes (A). OEM exports the composition type and passes it to the TIER1 
/square6 TIER1 imports the composition type, and makes changes like adding further port 
prototypes, component prototypes and connector prototypes (red color in B). TIER1 
considers these changes as “private” and does not return these changes to the OEM. 
/square6 OEM changes the composition, e.g. by adding some port prototypes and removing 
others (C). OEM exports the composition type and passes it to the TIER1 
/square6 TIER1 imports the composition type, and expects that the changes of the OEM are

--- Page 6 ---
User Manual Data Import  
2011, Vector Informatik GmbH Version: 2.0 
  
incorporated as well as the changes done by the TIER1 (D) 
 
Composition1 
SWC2 
Composition1 
SWC1 
SWC2 
Composition1 
SWC2 
Composition1 
SWC1 
SWC2 
OEM Workspace TIER1 Workspace 
A B
C D  
Figure 2: Import/Update Example 2 
 
4 Approach 
The import process in DaVinci Developer considers individual objects within the import 
context (set of AUTOSAR XML files or DCF files) and the workspace, see Figure 3. The 
objects are identified by the combination of object type and object short name. Based on 
this identification, the set of objects may be completely disjunctive, or (partially) overlap.

[… 6 further page(s) not extracted …]
