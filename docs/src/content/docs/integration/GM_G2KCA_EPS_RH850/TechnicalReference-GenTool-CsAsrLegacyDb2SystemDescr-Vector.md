---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — TechnicalReference GenTool CsAsrLegacyDb2SystemDescr Vector"
description: "Converted Technical Reference (vendor) from TechnicalReference_GenTool_CsAsrLegacyDb2SystemDescr_Vector.pdf (PDF, 716 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/TechnicalReferences/TechnicalReference_GenTool_CsAsrLegacyDb2SystemDescr_Vector.pdf` (Technical Reference (vendor); original PDF, about 716 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Vector Legacy Converter 
Technical Reference 
 
Technical Documentation 
Version 1.4.2 
 
 
 
 
 
 
 
 
 
 
 
Authors Thorsten Fröhlinghaus 
Status Released

--- Page 2 ---
Technical Reference Vector Legacy Converter 
2014, Vector Informatik GmbH Version: 1.4.2 
based on template version 4.11.1 
2 / 26 
Document Information 
History 
Author Date Version Remarks 
Thorsten Fröhlinghaus 2011-04-07 1.0 Created 
Thorsten Fröhlinghaus 2011-04-07 1.0 Released 
Thorsten Fröhlinghaus 2011-12-20 1.1 Legacy Converter V1.3.0 
Thorsten Fröhlinghaus 2012-01-20 1.1 Released 
Thorsten Fröhlinghaus 2012-03-22 1.2 Released 
Thorsten Fröhlinghaus 2012-11-21 1.3 Released 
Thorsten Fröhlinghaus 2014-04-01 1.4.1 Released 
Thorsten Fröhlinghaus 2014-07-28 1.4.2 Released 
Reference Documents 
No. Source Title Version 
[1]  Autosar Specification of the System Template, R3.1 Rev 4 V3.2.0 
[2]  Autosar Specification of the System Template, R3.2 Rev 1 V3.4.0 
[3]  Autosar System Template, R4.0 Rev 3 V4.2.0 
 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference Vector Legacy Converter 
2014, Vector Informatik GmbH Version: 1.4.2 
based on template version 4.11.1 
3 / 26 
Contents 
1 Introduction................................ ................................ ................................ ................... 5 
2 Functional Description ................................ ................................ ................................ . 6 
2.1 DBC Transformation ................................ ................................ .......................... 8 
2.2 LDF Transformation ................................ ................................ ......................... 12 
2.3 Fibex Transformation ................................ ................................ ....................... 15 
2.4 Extension File ................................ ................................ ................................ .. 21 
3 Glossary and Abbreviations ................................ ................................ ...................... 25 
3.1 Glossary ................................ ................................ ................................ .......... 25 
3.2 Abbreviations ................................ ................................ ................................ ... 25 
4 Contact ................................ ................................ ................................ ........................ 26

--- Page 4 ---
Technical Reference Vector Legacy Converter 
2014, Vector Informatik GmbH Version: 1.4.2 
based on template version 4.11.1 
4 / 26 
Tables 
Table 2-1  Vector Legacy Converter help text. ................................ ............................. 6 
Table 2-2  Transformation of CAN network objects. ................................ ..................... 9 
Table 2-3  Transformation of user-defined attributes. ................................ ................. 11 
Table 2-4  Transformation of LIN network objects. ................................ ..................... 14 
Table 2-5  Transformation of Fibex 2.0.1 elements. ................................ ................... 18 
Table 2-6  Transformation of Fibex 3.0.0/3.1.0 elements. ................................ .......... 20 
Table 2-7  Vector System Description Extension file elements................................. .. 24

--- Page 5 ---
Technical Reference Vector Legacy Converter 
2014, Vector Informatik GmbH Version: 1.4.2 
based on template version 4.11.1 
5 / 26 
1 Introduction 
The Vector Legacy Converter (VLC) supports the migration of legacy embedded software 
to the AUTOSAR software architecture. The VLC is a console application which transforms 
one or more DBC -, LDF - and Fibex files into an AUTOSAR System Description and  its 
ECU Extracts. The VLC is typically called by the DaVinci Project Assistant (DPA), but it can 
also be used as a stand -alone tool. The resulting ECU Extracts will serve as input for the 
Initial EcuC Generator.

--- Page 6 ---
Technical Reference Vector Legacy Converter 
2014, Vector Informatik GmbH Version: 1.4.2 
based on template version 4.11.1 
6 / 26 
2 Functional Description 
The VLC analyses legacy communication databases, and it maps their communication ele-
ments to AUTOSAR System Description elements. There are no standards or established 
rules which define such a mapping between legacy communication databases and System 
Descriptions. For this reason, the VLC defines its own AUTOSAR mapping rules which aim 
at preserving the semantics of the original communication databases.  These generic rules 
may be supplemented with OEM-specific rules. 
The AUTOSAR System Description allows various modeling variants w.r.t. to, e.g., naming 
conventions and package structures. The VLC  imposes fixed modeling rules which define 
a common namespace  for DBC -, LDF - and Fibex transf ormations. The VLC modeling 
rules are not coordinated  with the AUTOSAR transformation s of other tools  from other 
vendors. T he transformation results of the VLC and ot her tools may appear rather 
different. 
The VLC supports no user interaction, and thus the transformation between legacy formats 
and AUTOSAR System Description s is always the same. However, the VLC still identifies 
the manufacturer of a communication database, and it applies  OEM-specific rules. These 
OEM-specific rules must be implemented in advance. 
The calling conventions and options of the VLC are specified with the following help text: 
 
Usage: LegacyDb2SystemDescrConverter [options] <file|dir> [<file|dir> ...] 
[extfile] 
 
Create an AUTOSAR System Description out of one or more DBC, LDF or Fibex 
communication databases. 
 
Options: 
  -h, --help                 Show this help 
  -a, --adoptname            Adopt DBC filename as cluster name 
  -e, --extract              Create ECU extracts 
  -r, --release <31|32|40>   AUTOSAR release 
  -o, --output <file|dir>    Output file or directory 
   
Parameters: 
  <file|dir>                 Input file (*.dbc, *.ldf, *.xml) or directory 
  extfile                    Extension file (*.vsde) 
 
              Table 2-1  Vector Legacy Converter help text. 
The options may also be specified in a file called LegacyDb2SystemDescrConverter.config 
which resides in the same directory as the exe file LegacyDb 2SystemDescrConverter.exe. 
In this way, options can be defined which are  processed, e.g., when calling the VLC from 
the DPA. 
With the option ‘-r’ or ‘--release’ the AUTOSAR schema version can be selected. Currently, 
AUTOSAR 3.1.4, AUTOSAR 3.2.1 and AUTOSAR 4.0.3  are supported.  The VLC imple-
ments those schema versions which are required by the Vector tool chain, especially by 
the Initial EcuC Generator. The VLC does not aim at supporting arbitrary AUTOSAR sche -
ma versions.

[… 20 further page(s) not extracted …]
