---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — TechnicalReference Database Attributes GM"
description: "Converted Technical Reference (vendor) from TechnicalReference_Database_Attributes_GM.pdf (PDF, 122 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/TechnicalReference_Database_Attributes_GM.pdf` (Technical Reference (vendor); original PDF, about 122 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Database Attributes 
Technical Reference 
 
GMLAN 3.1 
Version 2.02.01 
 
 
 
 
 
 
 
 
 
 
Authors Frank Triem 
Versions: 2.02.01 
Status: Released

--- Page 2 ---
Technical Reference Database Attributes   
2013, Vector Informatik GmbH Version: 2.02.01 
Based on template version 2.8 
2 / 21 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Frank Triem 2007-06-06 1.0 Creation of document based on “Database 
Attributes GMLAN V3.0”. 
Frank Triem 2007-06-25 1.1 Database Attribute 
GenMsgMandatoryToSupervise corrected 
Frank Triem 2008-01-23 2.0 Update for configuration tool GENy 
Frank Triem 2008-02-06 2.1 Database attributes added 
- Baudrate 
- SamplePointMin 
- SamplePointMax 
- SyncJumpWidthMin 
- SyncJumpWidthMax 
Frank Triem 2012-10-23 2.2 Database Attribute NodeSuprvStabilityTime 
added in chapter 3.2 
Frank Triem 2013-01-28 2.02.01 ESCAN00064577: Update GMLAN version 
from GMLAN 3.0 to GMLAN 3.1 
Table 1-1  History of the Document 
 
 
 
 
 
 
 
 
 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference Database Attributes   
2013, Vector Informatik GmbH Version: 2.02.01 
Based on template version 2.8 
3 / 21 
Contents 
1 Document Information .................................................................................................  2 
1.1 History ............................................................................................................... 2 
2 Introduction................................................................................................................... 5 
3 Attribute Definitions for GMLAN V3.0 Databases ....................................................... 6 
3.1 Network Attributes .............................................................................................. 6 
3.1.1 Network Attributes for Node Communication Active Message ............ 7 
3.1.2 Network Attributes for Virtual Networks .............................................. 7 
3.1.3 Network Attributes for Bit Timing Register setup .................................  8 
3.2 Node Attributes .................................................................................................. 8 
3.3 Message Attributes ............................................................................................ 9 
3.3.1 Attribute Definitions for Diagnostics .................................................. 10 
3.4 Signal Attributes ............................................................................................... 11 
3.4.1 VN-Assignment of Signals................................................................ 11 
3.4.2 Signal Transmit Model Attributes ...................................................... 11 
3.4.3 Signal Supervision Attributes ............................................................ 12 
3.4.4 Signal Attributes ............................................................................... 13 
4 Attribute Settings in Terms of GM Concepts ............................................................ 14 
4.1 Signal Transmit Model ..................................................................................... 14 
4.1.1 Message Attributes .......................................................................... 14 
4.1.2 Signal Attributes ............................................................................... 15 
4.2 Signal Supervision ........................................................................................... 16 
4.2.1 Signal Attributes ............................................................................... 16 
5 Database Attributes for CANoe Models .................................................................... 17 
6 Database Attributes not evaluated by GENy ............................................................. 18 
6.1 Signal Transmit Model Attributes ...................................................................... 19 
6.1.1 Node Mapped Rx-Signal Default Value Attributes ............................ 20 
7 Contact ........................................................................................................................ 21

--- Page 4 ---
Technical Reference Database Attributes   
2013, Vector Informatik GmbH Version: 2.02.01 
Based on template version 2.8 
4 / 21 
Tables 
Table  1-1  History of the Document ............................................................................. 2 
Table  3-1  Network Attributes ...................................................................................... 7 
Table  3-2  Network Attributes for Node Communication Active Message ..................... 7 
Table  3-3  Network Attributes for Virtual Networks ....................................................... 7 
Table  3-4  Network Attributes for Bit Timing Register setup ......................................... 8 
Table  3-6  Node Attributes ........................................................................................... 8 
Table  3-7  Message Attributes ..................................................................................... 9 
Table  3-8  Attribute Definitions for Diagnostics .......................................................... 10 
Table  3-9  VN-Assignment of Signals ........................................................................ 11 
Table  3-10  Signal Supervision Attributes .................................................................... 12 
Table  3-11  Signal Attributes ........................................................................................  13 
Table  4-1  Message Attributes of Transmit Model ...................................................... 14 
Table  4-2  Signal Attributes of Transmit Model ........................................................... 15 
Table  4-3  Signal Attributes for Supervision ...............................................................  16 
Table  4-4  Signal Attributes for Failsoft Mechanism ................................................... 16 
Table  5-1  Database Attributes for CANoe Models ..................................................... 17 
Table  6-1  Network attributes not evaluated by GENy ............................................... 19 
Table  6-2  Signal Transmit Model attributes not evaluated by GENy ......................... 19 
Table  6-3  Rx-Signal Default attributes not evaluated by GENy .................................  20

--- Page 5 ---
Technical Reference Database Attributes   
2013, Vector Informatik GmbH Version: 2.02.01 
Based on template version 2.8 
5 / 21 
2 Introduction 
This document describes the database attributes that are used by the configuration and 
generation tool GENy for the configuration of the GMLAN Handler. In chapter 3 all possible 
attributes are listed along with a description of how the attributes should be set for use with 
GMLAN. 
A list of database base attributes that can be found in the GM databases, which are not 
used by GENy, can be found in chapter 6 . Please note that this is not a complete list of all 
available database attributes. 
 
 
  
 
Caution 
This document is valid for GMLAN 3.1 and Nm_Gmlan_Gm version 4.02.00 and higher.

--- Page 6 ---
Technical Reference Database Attributes   
2013, Vector Informatik GmbH Version: 2.02.01 
Based on template version 2.8 
6 / 21 
3 Attribute Definitions for GMLAN 3.1 Databases 
3.1 Network Attributes 
On the network level the following attributes are evaluated by GENy: 
Name Type Description 
Manufacturer String This is a fixed value and must be set to “GM” 
Default: “GM” 
NmType String Must be set to “GMLAN” to define the GMLAN 
network management. 
Default: 
“GMLAN” 
NmBaseAddress Hexadecimal Defines the base address for the VNMF. This 
value is usually set to 0x620 to declare a range of 
0x620-0x63F in the CAN-identifier range for the 
VNMF. 
NmMessageCount Integer This attribute defines the maximum number of 
nodes on the network. This attribute is used in 
combination with NmBaseAddress and spans a 
range of CAN-identifier within the 11-bit range for 
the VNMF. The value must be given as 2N (e.g. 
16 or 32). 
NetworkType String Defines the type of the CAN-network. The 
following Network Types are known: 
Possible values:  
“Powertrain”, “Bodybus”, “Infotainment” 
GENy uses this attribute in order to configure the 
baud rate. 
VersionNumber BCD-coded 
Integer 
This attribute can be used for versioning 
purposes. The value shall be a BCD-coded 
format. Thus, the number 100 is treated as 
Version 1.00, or the value 245 is handled as 
V2.45. This attribute definition is stored in ROM in 
two 8-bit constant values that can be accessed 
globa

[… 15 further page(s) not extracted …]
