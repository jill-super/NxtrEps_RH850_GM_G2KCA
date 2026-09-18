---
title: "Watchdog Driver — AUTOSAR WDG Component UserManual"
description: "Converted User Manual / User Guide from AUTOSAR_WDG_Component_UserManual.pdf (PDF, 863 KB)."
---

:::note
Converted from `Wdg/doc/AUTOSAR_WDG_Component_UserManual.pdf` (User Manual / User Guide; original PDF, about 863 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Wdg](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
AUTOSAR MCAL R4.0.3 
User‟s Manual 
 
 
 
 
WDG Driver Component Ver.1.0.4 
 
Embedded User‟s Manual 
 
 
 
 
 
Target Device: 
RH850/P1x 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
All information contained in these materials, including products and product specifications, 
represents information on the product at the time of publication and is subject to change by 
Renesas Electronics Corp. without notice. Please review the latest information published by 
Renesas Electronics Corp. through various means, including the Renesas Electronics Corp. 
website (http://www.renesas.com). 
 
 
 
 
www.renesas.com Rev.0.01 Apr 2015

--- Page 2 ---
2

--- Page 3 ---
3 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
Notice 
1. All information included in this document is current as of the date this document is issued. Such information, however, is subject to 
change without any prior notice. Before purchasing or using any Renesas Electronics products listed herein, please confirm the latest 
product information with a Renesas Electronics sales office. Also, please pay regular and careful attention to additional and different 
information to be disclosed by Renesas Electronics such as that disclosed through our website. 
2. Renesas Electronics does not assume any liability for infringement of patents, copyrights, or other intellectual property rights of third 
parties by or arising from the use of Renesas Electronics products or technical information described in this document. No license, 
express, implied or otherwise, is granted hereby under any patents, copyrights or other intellectual property rights of Renesas 
Electronics or others. 
 3. You should not alter, modify, copy, or otherwise misappropriate any Renesas Electronics product, whether in whole or in part. 
4. Descriptions of circuits, software and other related information in this document are provided only to illustrate the operation of 
semiconductor products and application examples.  You are fully responsible for the incorporation of these circuits, software, and 
information in the design of your equipment.  Renesas Electronics assumes no responsibility for any losses incurred by 
you or third parties arising from the use of these circuits, software, or information. 
5. When exporting the products or technology described in this document, you should comply with the applicable export control laws 
and regulations and follow the procedures required by such laws and regulations.  You should not use Renesas Electronics products 
or the technology described in this document for any purpose relating to military applications or use by the military, including but 
not limited to the development of weapons of mass destruction.  Renesas Electronics products and technology may not be used for or 
incorporated into any products or systems whose manufacture, use, or sale is prohibited under any applicable domestic or foreign 
laws or regulations. 
6. Renesas Electronics has used reasonable care in preparing the information included in this document, but Renesas Electronics does 
not warrant that such information is error free.  Renesas Electronics assumes no liability whatsoever for any damages incurred by 
you resulting from errors in or omissions from the information included herein. 
7. Renesas Electronics products are classified according to the following three quality grades:  "Standard", "High Quality", and 
"Specific".  The recommended applications for each Renesas Electronics product depends on the product's quality grade, as indicated 
below.  You must check the quality grade of each Renesas Electronics product before using it in a particular application.  You may 
not use any Renesas Electronics product for any application categorized as "Specific" without the prior written consent of Renesas 
Electronics.  Further, you may not use any Renesas Electronics product for any application for which it is not intended without the 
prior written consent of Renesas Electronics.  Renesas Electronics shall not be in any way liable for any damages or losses incurred by 
you or third parties arising from the use of any Renesas Electronics product for an application categorized as "Specific" or for which 
the product is not intended where you have failed to obtain the prior written consent of Renesas Electronics.  The quality grade of 
each Renesas Electronics product is "Standard" unless otherwise expressly specified in a Renesas Electronics data sheets or data 
books, etc. 
"Standard": Computers; office equipment; communications equipment

--- Page 4 ---
4

--- Page 5 ---
5 
Abbreviations and Acronyms 
 
Abbreviation / Acronym Description 
ADC Analog Digital Converter 
ANSI American National Standards Institute 
API Application Programming Interface 
AUTOSAR Automotive Open System ARchitecture 
CAN Controller Area Network 
DEM Diagnostic Event Manager 
DET/Det Development Error Tracer 
DIO Digital Input And Output 
ECU Electronic Control Unit 
EEPROM Electrical Erasable Programmable Read Only Memory 
ID/Id Identifier 
ISR Interrupt Service Routine 
LIN Local Interconnect Network 
MCAL Microcontroller Abstraction Layer 
MCU MicroController Unit 
PWM Pulse Width Modulation 
RAM Random Access Memory 
ROM Read Only Memory 
SCI Serial Communication Interface 
SPI Serial Peripheral Interface 
WDG/wdg WatchDog 
WDT WatchDog Timer 
WDGIF WatchDog Interface 
CDD Complex Device Driver 
 
 
 
Definitions 
 
Term Represented by 
Sl. No. Serial Number 
WDTAEVAC Watchdog Timer Enable Register for Varying Activation Code 
WDTAMD Watchdog Timer Mode Register 
WDTAWDTE Watchdog Timer Enable Register for Fixed Activation Code

--- Page 6 ---
6

[… 48 further page(s) not extracted …]
