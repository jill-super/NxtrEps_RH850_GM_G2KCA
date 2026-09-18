---
title: "Runtime Environment — TechnicalReference Rte"
description: "Converted Technical Reference (vendor) from TechnicalReference_Rte.pdf (PDF, 2223 KB)."
---

:::note
Converted from `Rte/doc/TechnicalReference_Rte.pdf` (Technical Reference (vendor); original PDF, about 2223 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Rte](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR RTE 
Technical Reference 
 
  
Version 4.8.0 
 
 
 
 
 
 
 
 
 
 
Authors Bernd Sigle, Martin Schlodder, Sascha Sommer, 
Stephanie Schaaf, Katharina Benkert, Cornelius Reuss 
Status Released

--- Page 2 ---
Technical Reference MICROSAR RTE    
2015, Vector Informatik GmbH Version: 4.8.0 
based on template version 3.5 
2 / 139 
Document Information 
History 
Author Date Version Remarks 
Bernd Sigle 2005-11-14 2.0.0 Document completely reworked and adapted to 
AUTOSAR RTE  
Bernd Sigle 2006-04-20 2.0.1 API description for Rte_IRead / Rte_IWrite added, 
description of used OS/COM services added 
Bernd Sigle 2006-07-11 2.0.2 API description for Rte_Receive / Rte_Send added; 
Adaptation to RTE SWS 1.0.0 Final 
Martin Schlodder 2006-11-02 2.0.3 Separation of RTE and target package 
Martin Schlodder 2006-11-15 2.0.4 Client/Server communication 
Martin Schlodder 2006-12-21 2.0.5 Serialized client/server communication 
Martin Schlodder 2007-01-17 2.0.6 Array data types 
Martin Schlodder 2007-02-14 2.0.7 Added exclusive areas, removed description of 
TargetPackages 
Bernd Sigle 2007-02-19 2.0.8 Added transmission acknowledgement  handling and 
minor rework of the document  
Bernd Sigle 2007-04-25 2.0.9 Added Rte_IStatus 
Martin Schlodder 2007-04-27 2.0.10 Added IRV and Const/Enum 
Martin Schlodder 
Bernd Sigle 
2007-05-01 2.1.0 Completed documentation for Version 2.2 
Bernd Sigle 2007-07-27 2.1.1 Added Rte_InitMemory, Rte_IWriteRef Runnable. 
Added description of runnable activation offset und 
updated picture of MICROSAR architecture.  
Martin Schlodder 2007-08-03 2.1.2 Added description of template update. 
Martin Schlodder 
Bernd Sigle 
2007-11-16 2.1.3 Added warning regarding IWrite / IrvIWrite.           
Added API descriptions of VFB trace hooks. 
Updated data type info for nested types. 
Martin Schlodder 
Bernd Sigle 
2008-02-06 2.1.4 Updated descriptions on template merging and task 
mapping.                                                                
Added description of Rte_Pim, Rte_CData, 
Rte_Calprm and Rte_Result.                                
Added support of string data type.                      
Updated command line argument description.     
Added NvRAM mapping description.                    
Added chapter about compiler abstraction and 
memory mapping. 
Hannes Futter 2008-03-11 2.1.5 Additional command line switches to support direct 
generation on xml and dcf files. 
Bernd Sigle 2008-03-26 2.2.0 Updated description of NV Memory Mapping and 
Chapter about limitations added.                       
Chapter about compiler and memory abstraction 
updated.                                                              
Support for AUTOSAR Release 3.0 added.

--- Page 3 ---
Technical Reference MICROSAR RTE    
2015, Vector Informatik GmbH Version: 4.8.0 
based on template version 3.5 
3 / 139 
Bernd Sigle 2008-04-16 2.3.0 Added description about A2L file generation and 
updated command line options and example calls to 
cover also the AUTOSAR XML input files. 
Bernd Sigle 2008-07-16 2.4.0 Removed limitations for multiple instantiation and 
compatibility mode support. 
Bernd Sigle 2008-08-13 2.5.0 Added description of indirect APIs Rte_Port, Rte_Ports 
and Rte_NPorts. Added description of platform 
dependent resource calculation. 
Bernd Sigle 2008-10-23 2.6.0 Added description of memory protection support. 
Bernd Sigle 2009-01-23 2.7.0 Added description of mode management APIs 
Rte_Mode and Rte_Switch and updated description of 
Rte_Feedback.                                                      
Added description of Rte_Invalidate and 
Rte_IInvalidate and added new Com APIs.           
Added additional runnable trigger events and removed 
section for runnables without trigger, which is no 
longer supported.                                             
Deviation for [rte_sws_2648] added.                                
Usage of new document template 
Bernd Sigle 2009-03-26 2.8.0 Removed limitations for unconnected ports and for 
data type generation. 
Sascha Sommer 
Bernd Sigle 
2009-08-11 2.9.0 Added description about usage of basic / extended 
task 
Added description of command line parameter -v 
Sascha Sommer 
Bernd Sigle  
2009-10-22 2.10.0 Added a warning for VFB trace hooks that prevent 
macro optimizations 
Explained that the Activation task attribute has to be 
set for basic tasks 
Init-Runnables no longer need to have a special suffix 
Explained the new periodic trigger implementation 
dialog. 
Server runnables with CanBeInvokedConcurrently set 
to false do not need to be mapped to tasks when the 
calling clients cannot interrupt each other 
Resource Usage is now listed in a HTML report 
Updated version of referenced documents and of 
supported AUTOSAR release. 
Updated examples with new workspace file extension. 
Added new defines for memory mapping. 
Bernd Sigle 2010-04-09 2.11.0 Added description of user header file Rte_UserTypes.h 
Updated component history and interface functions to 
the OS. Added pictures of Rte Interfaces and Rte 
Include Structure. Updated picture of MICROSAR 
architecture. Rework of chapter structure. 
Bernd Sigle 2010-05-25 2.11.1 Added description of RTE optimization mode

--- Page 4 ---
Technical Reference MICROSAR RTE    
2015, Vector Informatik GmbH Version: 4.8.0 
based on template version 3.5 
4 / 139 
Bernd Sigle 
Sascha Sommer 
2010-05-26 2.12.0 Added new measurement chapter, added description 
of COM Rx Filter, macros for access of invalid value, 
initial value, lower and upper limit, added support of   
minimum start interval and second array passing 
variant. Support of AUTOSAR Release 3.1 (RTE SWS 
2.2.0) 
Bernd Sigle 
 
2010-07-22 2.13.0 Added online calibration support. Removed limitation 
of missing transmission error detection 
Bernd Sigle 
 
2010-09-28 2.13.1 Added more detailed description of extended record 
data type compatibility rule 
Bernd Sigle 
 
2010-11-23 2.14.0 Removed obsolete command line parameters –bo, –bc 
and –bn. 
Stephanie Schaaf        
Bernd Sigle 
Sascha Sommer  
2011-07-25 2.15.0 Added general support of AUTOSAR Release 3.2.1 
(RTE SWS 2.4.0).  
Added support of never received status. 
Added support of S/R update handling. 
Mentioned that –g c and –g i ignore service 
components when –m specifies an ECU project. 
Explained RTE usage with Non-Trusted BSW     
Added hint for FUNC_P2CONST() problems 
Explained measurement of COM signals 
Stephanie Schaaf  
Bernd Sigle 
Sascha Sommer 
2012-01-25 2.16.0 Enhanced command line interface (support for several 
generation modes in one command line call, optional 
command line parameter –m) 
Split of RTE into OS Application specific files 
Byte arrays no longer need to be mapped to signals 
groups 
Allow configuration of Schedule() calls in non-
preemptive tasks 
Bernd Sigle 2012-05-18 2.17.0 Corrected description how the Rte_IsUpdated API can 
be enabled 
Bernd Sigle 2012-09-18 2.18.0 Added general support of AUTOSAR Release 3.2.2 
(RTE SWS 2.5.0). 
Added support of non-queued N:1 S/R communication    
Bernd Sigle 2012-08-28 3.90.0 AUTOSAR 4.0.3 support, DaVinci Configurator 5 
support  
Bernd Sigle 2012-12-11 4.0.0 Updated API descriptions concerning 
RTE_E_UNCONNECTED  return code 
Added description of Rte_UserTypes.h file which is 
now also generated with the template mechanism 
Stephanie Schaaf 2013-03-26 4.1.0 Added support of Rte_MemSeg.a2l file 
Added description of –o sub option for A2L file path 
Bernd Sigle 2013-06-14 4.1.1 Added Multi-Core support (S/R communication) 
Added support of Inter-Runnable Variables with 
composite data types

--- Page 5 ---
Technical Reference MICROSAR RTE    
2015, Vector Informatik GmbH Version: 4.8.0 
based on template version 3.5 
5 / 139 
Katharina Benkert 
Stephanie Schaaf 
Sascha Sommer 
Bernd Sigle 
2013-10-30 4.2.0 Added support for arrays of dynamic data length 
(Rte_Send/Rte_Receive) 
Added support for parallel generation for multiple 
component types 
Multicore support 
Added support for SchM Contract Phase Generation 
Added support for Nv Block SWCs 
Katharina Benkert 
Sascha Sommer 
Stephanie Schaaf 
2014-02-06 4.3.0 Added support of VFB Trace Client Prefixes 
Optimized Multicore support without IOCs 
Memory Protection support for Multicore systems 
Inter-ECU sender/receiver communication, queued 
sender/receiver communication and mapped 
client/server calls are no longer limited to the BSW 
partition 
Added support of Development Error Reporting 
Added support of registering XCP Events in the XCP 
module configuration 
Stephanie Schaaf 
Bernd Sigle 
2014-06-17 4.4.0 Support for unconnected client ports for synchronous 
C/S communication 
Inter-Ecu C/S communication using SOME/IP 
Transformer 
Support for PR-Ports 
S/R Serialization using SOME/IP Transformer and E2E 
Transformer 
Support LdCom 
Bernd Sigle 2014-08-13 4.4.1 Described decimal coding of the version defines and 
the return code of SchM_GetVersionInfo 
Added chapter 

[… 133 further page(s) not extracted …]
