---
title: "Renesas Microcontroller Abstraction Support — KnownIssues P1x R403 2015 CW23"
description: "Converted Portable Document (vendor or generated report) from KnownIssues_P1x_R403_2015_CW23.pdf (PDF, 107 KB)."
---

:::note
Converted from `RenesasMcalSuprt/doc/4.00.04/KnownIssues_P1x_R403_2015_CW23.pdf` (Portable Document (vendor or generated report); original PDF, about 107 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to RenesasMcalSuprt](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
ID Category Summary Description ASR_TicketType Status
22712 General Usage of value INF not according ASR 
requirements
Problem description: 
According AUTOSAR_TPS_ECUConfiguration the value 'inf' derived from standard module definition STMD must be used as follows: 
• [ecuc_sws_6045] If the min value equals -inf or the max value equals inf in 
the StMD the min/max values in the VSMD shall be replaced with the actually 
supported min/max values for this implementation. 
 
Expected behavior: 
INF shall not be used, but instead the actual MIN/MAX values shall be available in PDFs 
 
Current behavior: 
See problem description field.
BUG OPEN 
ISSUE
26927 General [Port] 
AUTOSAR_PORT_Component_UserManual.
pdf is lacking information about Exclusives 
areas for CRITICAL SECTION PROTECTION
Problem description: 
Lack of information about Exclusives areas in AUTOSAR_PORT_Component_UserManual.pdf. As a result user is facing difficulty during integration. 
Source Package: AUTOSAR_RH850_P1x_MCAL_E4.03 
 
Expected Behavior: 
The user manual should contain information about INIT_CONFIG_PROTECTION, REFRESH_PORT_INTERNAL_PROTECTION and SET_TO_DIO_ALT_PROTECTION. 
 
Actual behaviour: 
UM only describes SET_PIN_MODE_PROTECTION in chapter 4.4, but SET_PIN_DIR_PROTECTION, INIT_CONFIG_PROTECTION, REFRESH_PORT_INTERNAL_PROTECTION and 
SET_TO_DIO_ALT_PROTECTION, SET_PIN_DEFAULT_MODE_PROTECTION, SET_PIN_DEFAULT_DIR_PROTECTION are not mentioned.
BUG OPEN 
ISSUE
26988 General CAN and LIN modules not following 
Autosar requirement BSW00347
Problem description: 
As per AUTOSAR requirement BSW00347, the driver modules shall be named as per <MSN>_<VendorId>_<VendorSpecificName>_<ServiceName>. 
For Example : 'Can_Init()' will become 'Can_59_Renesas_Init()'.  
It shall be followed for File Names, Public APIs, Published Parameters, Memory allocation Keywords and Public data types. But this is not followed in CAN and LIN modules which support 
multiple instance as per autosar base definition file. 
 
Expected behaviour: 
The driver modules shall be named as per <MSN>_<VendorId>_<VendorSpecificName>_<ServiceName>. 
 
Actual behaviour:  
The driver modules(CAN and LIN) are not named as per <MSN>_<VendorId>_<VendorSpecificName>_<ServiceName>. 
 
The following MCAL modules have the tag 'UPPER-MULTIPLICITY-INFINITE' is set to 'true' in Autosar Base Definition file AUTOSAR_MOD_ECUConfigurationParameters.arxml and hence 
support multiple instance. 
1. CAN 
2. Ethernet 
3. FLS 
4. Flexray 
5. ICU 
6. LIN 
7. PWM 
8. WDG 
But for Ethernet, FLS, ICU, and PWM modules, the requirement BSW00347 is moved to NA requirements in the Traceability section.  
BUG OPEN 
ISSUE

--- Page 2 ---
27639 General PRAGMA define inconsistent to device 
header file package
<u>Problem Description:</u> 
PRAGMA define differs between io_macros_v2.h from device header file packages and compiler.h in MCAL package. 
 
In Compiler.h: 
#define PRAGMA(x) _Pragma(x) 
 
In io_macros_v2.h: 
#define PRAGMA(x) _Pragma(#x) 
 
<u>Current Behaviour:</u> 
In customer application this might cause a compilation warning due to a macro redefinition if both header files are used. 
 
<u>Expected Behaviour:</u> 
Consistent define used in both header files. 
BUG OPEN 
ISSUE
27721 General Command line option -F not working Problem description: 
The -F/FILEVERSION option of generation tool is not working. Instead of listing the version of tool code files, the tool is throwing error 'ERR000011:ECU Configuration Description File is 
not provided as input to the Generation Tool'. 
 
Expected behavior: 
On the usage of -F/FILEVERSION option, generation tool must list the version of tool code files. 
 
Actual behaviour: 
See Problem description. 
BUG OPEN 
ISSUE
27747 General Makefiles use invalid include paths for GHS 
builder
Problem Description: 
The GHS makefiles for sample applications use invalid include paths parameters. 
This behaviour has currently no effect to GHS builder but this might change. 
It lengthens the command lines without any use. 
 
Actual behaviour: 
GHS builder is called with invalid options like 
-I\4.0.3 
-I\common 
 
Expected behaviour: 
Only valid include path parameters shall be used.
BUG OPEN 
ISSUE
27766 General Functional codes are executing Even after 
DEM is reported.
Problem Description: 
 
Even after DEM error is reported, functional codes are getting executed, which may result in unexpected behavior of driver.  
 
Similar issue is found in SPI while doing functional testing for E1x V4.00.04 release, And an issue is reported in mantis # bug:26731. 
 
Decided to create new ticket to start  investigation for similar issues in all other module (see note:181849). 
 
 
 
Expected behavior:  
Functional codes shall not execute after reporting DEM Error. 
 
 
Actual behavior:  
Functional codes are executed even after reporting DEM Error. 
BUG OPEN 
ISSUE

--- Page 3 ---
27974 General Makefiles specify irrelevant folders for 
header search
Problem description: 
The -I parameter is used to specify folders where the GHS builder shall search for header files. But also source folders are given. 
 
Actual behaviour: 
Many irrelevant folders are given as parameter to GHS builder. When project becomes large the maximum command line length (8k) is exceeded. 
 
Expected behaviour: 
Only relevant folders shall be given with -I parameter.
BUG OPEN 
ISSUE
28478 General CAN-ENTER-EXCLUSIVE-AREA-REF tag is 
missing in the BSWMDT
canEnterExclusiveArea is required inside the entity in BSWMDT, if the referenced exclusive area is used in the entity's code.  
The entity can be BswCalledEntity, BswSchedulableEntity or BswInterruptEntity. 
 
 
Actual behaviour: 
 
<BSW-INTERNAL-BEHAVIOR UUID="ECUS:951843a9-6848-4a8d-869a-7b29a87158fa"> 
  <SHORT-NAME>BswInternalBehavior_0</SHORT-NAME> 
    <EXCLUSIVE-AREA UUID="ECUS:1b965de4-5e4a-49d8-a4cb-e7782386f347"> 
      <SHORT-NAME>VARIABLE_PROTECTION</SHORT-NAME> 
    </EXCLUSIVE-AREA> 
  </EXCLUSIVE-AREAS> 
  <ENTITYS> 
    <BSW-INTERRUPT-ENTITY UUID="ECUS:8d9d01cd-59a4-4f9d-a0c5-a46966e1b2ad"> 
      <SHORT-NAME>BswInterruptEntity_1</SHORT-NAME> 
      <IMPLEMENTED-ENTRY-REF DEST="BSW-MODULE-ENTRY">/ArPackage_0/MCU_FEINT_ISR</IMPLEMENTED-ENTRY-REF> 
      <INTERRUPT-CATEGORY>CAT-1</INTERRUPT-CATEGORY> 
      <INTERRUPT-SOURCE>INTLVI</INTERRUPT-SOURCE> 
    </BSW-INTERRUPT-ENTITY> 
 
Expected behaviour: 
 
<BSW-INTERNAL-BEHAVIOR UUID="ECUS:951843a9-6848-4a8d-869a-7b29a87158fa"> 
  <SHORT-NAME>BswInternalBehavior_0</SHORT-NAME> 
    <EXCLUSIVE-AREA UUID="ECUS:1b965de4-5e4a-49d8-a4cb-e7782386f347"> 
      <SHORT-NAME>VARIABLE_PROTECTION</SHORT-NAME> 
    </EXCLUSIVE-AREA> 
  </EXCLUSIVE-AREAS> 
BUG OPEN 
ISSUE
28534 General Wrong upper multiplicity definition for 
Configuration container.
Problem description: 
In PDF of some MCAL modules the upper multiplicity is defined as 
<UPPER-MULTIPLICITY-INFINITE>XX</UPPER-MULTIPLICITY-INFINITE> 
 
The above definitions are not correct according to ASR ecuc_sws_2011. 
 
 
Actual behavior: 
Multiple configuration is not possible due to the above problem. 
 
Expected behavior: 
The correct definitions must be as follows: 
<UPPER-MULTIPLICITY>XX</UPPER-MULTIPLICITY>
BUG OPEN 
ISSUE

--- Page 4 ---
26812 ADC Unexpected DET ADC_E_IDLE is been raised 
from Adc_DisableHardware Trigger
Problem Description: 
Unexpected DET ADC_E_IDLE is being raised when Adc_DisableHardwareTrigger is invoked for an already enabled group (using the api Adc_EnableHardwareTrigger)whose status is 
ADC_STREAM_COMPLETED. 
 
Expected Behaviour : 
As  per requirement ADC304, the DET ADC_E_IDLE should not be reported when Adc_DisableHardwareTrigger is called for a group that has already been enabled using 
Adc_EnableHardwareTrigger. 
 
Actual Behaviour : 
The DET ADC_E_IDLE is reported when Adc_DisableHardwareTrigger is called for a group that has already been enabled using Adc_EnableHardwareTrigger. 
BUG OPEN 
ISSUE
27492 ADC HW triggered One-shot conversion in 
Circular Streaming is not working as 
expected
Problem Description: 
As per AUTOSAR specification, one HW trigger should trigger only one ADC channel group conversion stream. The conversion must finish once it receives the HW trigger that is equal to 
number of streams configured for the group.  
 
But in the current design single trigger executes the whole stream of conversions. 
 
Expected Behavior:  
Only one ADC channel Group conversion stream should happen per H/W trigger. 
 
Actual Behavior: 
Streaming conversion is getting completed with single H/W trigger
BUG OPEN 
ISSUE
27505 ADC 'ucGroupSettings' element of 
Adc_GstGroupConfig[] is not generated 
properly
Problem Description: 
LSB of 'ucGroupSettings' element decides whether a group is one-shot or continuous.  
'0' means continuous group and  
'1' means one-shot group. 
But code generator is not generating this properly. 
For one-shot mode and circular streaming group it generates '1' and 
for continuous mode and linear streaming group 

[… 36 further page(s) not extracted …]
