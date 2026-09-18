---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — ProductInformation 2 MICROSAR SoftwarePackagesAndMaintenance"
description: "Converted Portable Document (vendor or generated report) from ProductInformation_2_MICROSAR_SoftwarePackagesAndMaintenance.pdf (PDF, 196 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/DeliveryInformation/ProductInformation_2_MICROSAR_SoftwarePackagesAndMaintenance.pdf` (Portable Document (vendor or generated report); original PDF, about 196 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Product Information MICROSAR Software Packages and Maintenance 
2015, Vector Informatik GmbH Version: 1.12.0 
based on template version 5.2.0 
1 / 6 
1 Vector Embedded Software 
Definition SLP/HLP/SIP, Maintenance and Release Types 
1.1 Software License Package (SLP) 
The SLP includes the license and usage rights (see quotation) for a hardware-independent 
module (e.g. a COM layer) based on a defined specification. 
Depending on the type of module, the software will be based on the following technical 
specifications: 
> AUTOSAR, ASAM, OSEK/VDX, ISO, HIS, etc. 
> OEM requirements (for OEM-specific deliveries) 
> Customer-specific requirements (optional) 
The following work products are licensed by purchase of an SLP: 
> The module as source code 
> Detailed technical documentation 
> Generator plug-in to generate ANSI C code 
> Configuration files for convenient configuration with Vector configuration tools 
The module will be tested using a component test suite on a standard hardware platform 
(CANoe Emulation). Integration testing on the specific µController and delivery will be 
performed when a SIP is purchased (see section 1.3). 
1.2 Hardware License Package (HLP) 
The HLP includes the license and usage rights (see quotation) for a hardware -dependent 
module (e.g. CAN Driver) and is valid for a combination of compiler (version independent), 
microcontroller family and relevant hardware (e.g. CAN cell). 
Depending on the type of module, the software will be based on the following technical 
specifications: 
> AUTOSAR, ASAM, OSEK, ISO, HIS, etc. 
> OEM requirements (for OEM-specific deliveries) 
> Customer-specific requirements (optional) 
> Specification of microcontroller and compiler 
The following work products are licensed by purchase of an HLP:  
> The module as source code 
> Detailed technical documentation 
> Generator plug-in to generate ANSI C code 
> Configuration files for convenient configuration with Vector configuration tools.

--- Page 2 ---
Product Information MICROSAR Software Packages and Maintenance 
2015, Vector Informatik GmbH Version: 1.12.0 
based on template version 5.2.0 
2 / 6 
The module will be tested using a component test suite on a derivative of the 
microcontroller family which is defined by Vector. Integration testing on the specific 
µController and delivery will be performed when a SIP is purchased (see section 1.3). 
 
1.3 Software Integration Package (SIP) 
The SIP includes integration, test, release and delivery of the modules that are licensed by 
an SLP and/or an HLP.  
To perform integration and closely test the customer's use case, the following must be 
defined in accordance with the customer: 
> Microcontroller derivative 
> Compiler, compiler version, and compiler options 
> Use case (e.g. number of CAN channels) 
> Car manufacturer (regarding communication description, pre-configuration…) 
For each SIP , all delivered work products will be added to a configuratio n management 
system, thus allowing redeliveries for a minimum of 10 years (excluding the Beta SIP). 
1.4 Mini SIP 
The Mini SIP includes the delivery of individual modules. The software is tested on module 
level. The delivery is not tested on the target hardware and compiler. But Vector provides 
remedy of defects if they are based on defined processor and compiler mentioned in the 
quote. 
1.5 SIP Types 
1.5.1 Beta SIP 
A Beta SIP can only be ordered in combination with a Production SIP.  Depending on the 
agreement with the cus tomer, the software may include the complete or reduced 
functionality. The software is only  preliminary integrated and tested. The usage of a Beta 
SIP for serial production is prohibited. The Beta SIP software may only be used for test 
purposes. Vector gra nts no warranty and/or liability to the extent permitted by law or 
statute. 
1.5.2 Production SIP 
A Production SIP is a package which includes the release for serial production. 
1.5.3 Update SIP  
An Update SIP is a package which replaces a previous Production SIP. An U pdate SIP is 
necessary if an additional delivery is needed because of modified requirements (compiler 
version, options, functionality, etc.). The delivery will be performed according to the 
existing contractual agreement and must be scheduled with Vector. 
1.5.4 Prototype SIP 
A Prototype SIP is a special package which may only be purchased by a Tier 1. The use is 
limited to a defined application area, e.g. prototyping. The software is only  preliminary

--- Page 3 ---
Product Information MICROSAR Software Packages and Maintenance 
2015, Vector Informatik GmbH Version: 1.12.0 
based on template version 5.2.0 
3 / 6 
integrated and tested. The SIP is only available for platforms which are already supported 
by Vector. License packages (HLP, SLP) are not necessary. An upgrade to a Production 
SIP is only possible if identical technical features are used and the Prototype SIP is not 
older than one year. Vector grants no warranty and/o r liability to the extent permitted by 
law or statute. 
1.5.5 Overview SIP Types 
The following table lists the scope of services, deliverables and release types for each SIP 
Type 
SIP Type /  
Mini SIP  
Beta SIP 
Production 
SIP 
Update SIP 
Prototype 
SIP 
Scope of 
Services Integration and test of selected 
modules     
Delivery      
Remedy of defects     
Deliverables 
Software (Source or object code 
dependent on the contractual 
agreement - NDA) 
    
Documentation 1   1 
Test report  4   
Demo application 2 2,4   
Release 
Types3 Beta Release     
Pre Release     
Final Release     
Serial Production Release     
1 The documentation is not necessarily complete 
2 Depends on the package 
3 Release Types are described in detail on page 5 
4 Not part of the Mini SIP 
Table 1-1  Overview SIP Types 
1.6 Maintenance 
Maintenance of Vector Embedded Software is available for the SLP, HLP and SIP . 
Maintenance generally includes bug-fixing.

--- Page 4 ---
Product Information MICROSAR Software Packages and Maintenance 
2015, Vector Informatik GmbH Version: 1.12.0 
based on template version 5.2.0 
4 / 6 
  
 
Note 
Only the latest delivered version will be maintained. 
  
1.6.1 SLP Maintenance 
The maintenance of the SLP includes the adaptation  of the appropriate working products 
(components, documentation, generators …). The SLP Maintenance includes: 
> Adaptations caused by “minor“ or “patch“-version modifications of the related 
AUTOSAR specification. In case of new functions, the extension of the licensed 
functionality has to be discussed with Vector. 
> Adaptations caused by comparable changes of other specifications based on Vector’s 
assessment. 
> Registered RfCs for the AUTOSAR Specification are included as far as they are 
required by the OEM. 
Deliveries are not included as part of SLP maintenance; they are part of SIP maintenance. 
The SLP maintenance period begins with the first delivery. 
1.6.2 HLP Maintenance 
The maintenance of the HLP includes the adaptation of the appropriate work products 
(components, documentation, generators …). The HLP maintenance includes: 
> Adaptations caused by “minor“ or “patch“-version modifications of the related 
AUTOSAR specification. In case of new functions, the extension of the licensed 
functionality has to be discussed with Vector. 
> Adaptation caused by comparable changes of other specifications based on Vector’s 
assessment. 
> Adaptation caused by minor hardware changes based on Vector’s assessment. 
> The implementation of simple workarounds for hardware issues. 
Deliveries are not included as part of HLP maintenance; they are part of the SIP 
maintenance. 
The HLP maintenance period begins with the first delivery. 
1.6.3 SIP Maintenance 
The SIP Standard Maintenance includes: 
> Reporting about known issues (“Active Issue Reporting“). 
> One delivery per year (Update SIP or update of a Beta SIP)

--- Page 5 ---
Product Information MICROSAR Software Packages and Maintenance 
2015, Vector Informatik GmbH Version: 1.12.0 
based on template version 5.2.0 
5 / 6 
  
 
Note 
This update will be delivered on request ! 
  
> If a bug-fix delivery should be needed on short notice such a delivery would be 
performed without a comprehensive test. In this case the status of the delivery would 
be Beta Release or Pre Release (see Release Types in chapter 1.7). 
A Production Release has to be scheduled with Vector separately. 
The SIP maintenance period starts with the first delivery of the product (Beta SIP or 
Production SIP). 
In addition to the SIP Standard Maintenance, Vector offers SIP Extended Maintenance and 
SIP Production Maintenance. 
SIP Extended Maintenance contains the same features as SIP Standard Maintenance. It 
includes one further delivery per year (Update SIP or Beta SIP). 
SIP Produc tion Maintenance only includes reporting about known issues (“Active Issue 
Reporting“). But Vector provides remedy of def ects in cas
