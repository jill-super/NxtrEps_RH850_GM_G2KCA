---
title: "Renesas Microcontroller Abstraction Support — GettingStarted MCAL Drivers X1x"
description: "Converted Portable Document (vendor or generated report) from GettingStarted_MCAL_Drivers_X1x.pdf (PDF, 1511 KB)."
---

:::note
Converted from `RenesasMcalSuprt/doc/4.00.04/GettingStarted_MCAL_Drivers_X1x.pdf` (Portable Document (vendor or generated report); original PDF, about 1511 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to RenesasMcalSuprt](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Getting Started Document for 
X1x MCAL Driver 
 
 
 
 
Version 1.0.5
User’s 
Manual 
 
 
 
Target Device: 
RH850/X1x 
 
 
 
 
 
 
 
 
All information contained in these materials, including products and product specifications, 
represents information on the product at the time of publication and is subject to change by 
Renesas Electronics Corp. without notice. Please review the latest information published by 
Renesas Electronics Corp. through various means, including the Renesas Electronics Corp. 
website (http://www.renesas.com). 
 
 
 
 
 
 
www.renesas.com Rev.0.01 Aug 2014

--- Page 2 ---
2

--- Page 3 ---
3 
Notice 
1. All information included in this document is current as of the date this document is issued. Such information, however, is 
subject to change without any prior notice. Before purchasing or using any Renesas Electronics products listed herein, please 
confirm the latest product information with a Renesas Electronics sales office. Also, please pay regular and careful attention to 
additional and different information to be disclosed by Renesas Electronics such as that disclosed through our website. 
2. Renesas Electronics does not assume any liability for infringement of patents, copyrights, or other intellectual property rights 
of third parties by or arising from the use of Renesas Electronics products or technical information described in this document. 
No license, express, implied or otherwise, is granted hereby under any patents, copyrights or other intellectual property rights 
of Renesas Electronics or others. 
3. You should not alter, modify, copy, or otherwise misappropriate any Renesas Electronics product, whether in whole or in part. 
4. Descriptions of circuits, software and other related information in this document are provided only to illustrate the operation of 
semiconductor products and application examples.  You are fully responsible for the incorporation of these circuits, software, 
and information in the design of your equipment.  Renesas Electronics assumes no responsibility for any losses incurred by 
you or third parties arising from the use of these circuits, software, or information. 
5. When exporting the products or technology described in this document, you should comply with the applicable export control 
laws and regulations and follow the procedures required by such laws and regulations.  You should not use Renesas 
Electronics products or the technology described in this document for any purpose relating to military applications or use by 
the military, including but not limited to the development of weapons of mass destruction.  Renesas Electronics products and 
technology may not be used for or incorporated into any products or systems whose manufacture, use, or sale is prohibited 
under any applicable domestic or foreign laws or regulations. 
6. Renesas Electronics has used reasonable care in preparing the information included in this document, but Renesas Electronics 
does not warrant that such information is error free.  Renesas Electronics assumes no liability whatsoever for any damages 
incurred by you resulting from errors in or omissions from the information included herein. 
7. Renesas Electronics products are classified according to the following three quality grades:  "Standard", "High Quality", and 
"Specific".  The recommended applications for each Renesas Electronics product depends on the product's quality grade, as 
indicated below.  You must check the quality grade of each Renesas Electronics product before using it in a particular 
application.  You may not use any Renesas Electronics product for any application categorized as "Specific" without the prior 
written consent of Renesas Electronics.  Further, you may not use any Renesas Electronics product for any application for 
which it is not intended without the prior written consent of Renesas Electronics.  Renesas Electronics shall not be in any way 
liable for any damages or losses incurred by you or third parties arising from the use of any Renesas Electronics product for an 
application categorized as "Specific" or for which the product is not intended where you have failed to obtain the prior written 
consent of Renesas Electronics.  The quality grade of each Renesas Electronics product is "Standard" unless otherwise 
expressly specified in a Renesas Electronics data sheets or data books, etc. 
"Standard": Computers; office equipment; communications equipment; test and measurement equipment; audio and visual 
equipment; home electronic appliances; machine tools; personal electronic equipment; and industri

--- Page 4 ---
4

--- Page 5 ---
5 
Abbreviations and Acronyms 
 
 
 
Abbreviation / Acronym Description 
ARXML/arxml AUTOSAR xml 
AUTOSAR Automotive Open System Architecture 
BSWMDT Basic Software Module Description Template 
<MSN> Module Short Name 
ECU Electronic Control Unit 
GUI Graphical User Interface 
MB Mega Bytes 
MHz Mega Hertz 
RAM Random Access Memory 
xml/XML eXtensible Markup Language 
<MICRO_VARIANT> F1x, R1x, P1x, E1x etc. 
<MICRO_SUB_VARIANT> F1L, R1L, P1L, E1L, E1MS etc. 
AUTOSAR_VERSION 3.2.2 or 4.0.3 
DEVICE_NAME Example :701205EAFP 
 
 
 
Definitions 
 
 
 
Terminology Description 
.xml XML File. 
.one Project Settings file. 
.arxml AUTOSAR XML File. 
.trxml Translation XML File. 
ECU Configuration 
Parameter Definition File 
The ECU Configuration Parameter Definition is of type XML, which contains the 
definition for AUTOSAR software components i.e. definitions for Modules, 
Containers and Parameters. The format of the XML File will be compliant with 
AUTOSAR ECU specification standards. 
ECU Configuration 
Description File 
The ECU Configuration Description file in XML format, which contains the 
configured values for Parameters, Containers and Modules. ECU Configuration 
Description XML File format will be compliant with the AUTOSAR ECU 
specification standards. 
BSWMDT File The BSWMDT File in XML format, which is the template for the Basic Software 
Module Description. BSWMDT File format will be compliant with the AUTOSAR 
BSWMDT specification standards. 
Translation XML File Translation XML File is in XML format which contains translation and device 
specific header file path. 
Configuration XML File Configuration XML File is in XML format which contains command line options 
and options for input/output file path.

--- Page 6 ---
6

[… 60 further page(s) not extracted …]
