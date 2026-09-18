---
title: "Renesas Microcontroller Abstraction Support — Releasenotes P1x FULL R403 Ver4.00.04"
description: "Converted Release Notes from Releasenotes_P1x_FULL_R403_Ver4.00.04.pdf (PDF, 601 KB)."
---

:::note
Converted from `RenesasMcalSuprt/doc/4.00.04/Releasenotes_P1x_FULL_R403_Ver4.00.04.pdf` (Release Notes; original PDF, about 601 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to RenesasMcalSuprt](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Renesas Electronics  Release Date: 08/06/2015 
 
Page 1 of 42 
Release Notes for RENESAS RH850/P1x: 
RENESAS_SW-AUTOSAR-P1x: MCAL Ver4.00.04 
QM Beta Quality 
1.1 Purpose: 
To deliver AUTOSAR R4.0.3 MCAL software for P1x V4.00.04 release using the following inputs. 
 
    Device Manual:          r01uh0436ej0070_rh850p1x.pdf 
 
    Device File:          DF-RH850P1M-EE_V100.zip 
 
    Operating Precautions:  R01TU0069ED0200_RH850.pdf 
                          
    Flash Libraries:       RENESAS_FCL_RH850_T01E_V2.00.exe 
                       RENESAS_FDL_RH850_T01E_V2.00.exe 
 
    Modules supported:     ADC, CAN, DIO, FLS, FLSTST, FR, GPT, ICU, MCU, PORT, PWM,     
                             RAMTST, SPI, WDG.

--- Page 2 ---
Renesas Electronics  Release Date: 08/06/2015 
 
Page 2 of 42 
1.2 Package information 
Product  RH850/P1x 
Variant P1M 
Product Release Version Ver4.00.04 
AUTOSAR Specification Version 4.0.3 
Device tested on P1M - R7F701310  
Devices supported R7F701304  
R7F701305 
R7F701310 
R7F701311 
R7F701312  
R7F701313  
R7F701314  
R7F701315  
R7F701318 
R7F701319  
R7F701320  
R7F701321  
R7F701322  
R7F701323  
Release Date 08-June-2015

--- Page 3 ---
Renesas Electronics  Release Date: 08/06/2015 
 
Page 3 of 42 
1.3 Tools  
1.3.1 GHS 
Tool Version Options 
GreenHills 
Multi IDE – 
compiler 
Green Hills Multi 
V6.1.4 Compiler 
Version 2013.5.5 
+ 
Patches : 
P2, P9, P12, P13, 
P14 
-Ospace -g -cpu=rh850g3k -gsize  
-prepare_dispose -sda=all -passsource  
-Wundef -no_callt -reserve_r2  
--short_enum -fsoft --prototype_errors  
--diag_error 193 -dual_debug -large_sda  
--no_commons -shorten_loads  
-shorten_moves -Wshadow -nofloatio  
-ignore_callt_state_in_interrupts -delete  
-inline_prologue 
1.3.2 Configuration code generator 
Tool Version Options 
ECU Spectrum 4.0.14 - 
1.3.3 Additional software 
Tool Version Options 
NA - -

--- Page 4 ---
Renesas Electronics  Release Date: 08/06/2015 
 
Page 4 of 42 
1.4 Generic Information 
1.4.1 Release Target 
Processor P1M - R7F701310 
Module Generic 
Date 08-June-2015 
1.4.2 Release Items 
Filename Version Change Description 
P1x_translation.h  1.0.6 File updated for FLS and CAN macros. 
ComStack_Types.h  1.0.1 No change 
Std_Types.h  1.0.1 No change 
rh850_Types.h 1.0.4 No change 
Platform_Types.h  1.0.1 No change 
Compiler.h 1.0.3 No change 
Compiler_Cfg.h  1.0.5 No change 
MemMap.h  1.0.6 No change 
NvM_Types.h  1.0.1 No change 
Os.h  1.0.1 No change 
Os.c  1.0.2 No change 
GettingStarted_MCAL_Drivers_X1x.
pdf 
1.0.5 No change 
AUTOSAR_Modules_Overview.pdf 1.0.7 No change 
1.4.3 Known Issues 
ID Description 
1. Please refer KnownIssues_P1x_R403_2015_CW23.pdf

--- Page 5 ---
Renesas Electronics  Release Date: 08/06/2015 
 
Page 5 of 42 
 
1.5 Module Index 
 
ADC 
 
CAN 
 
DIO 
 
FLS 
 
FLSTST 
 
FR 
 
GPT 
 
ICU 
 
MCU 
 
PORT 
 
PWM 
 
RAMTST 
 
SPI 
 
WDG

--- Page 6 ---
Renesas Electronics  Release Date: 08/06/2015 
 
Page 6 of 42 
2 ADC 
2.1 Target Info 
Processor P1M - R7F701310 
Module ADC 
Date 08-June-2015 
2.2 Release Items 
Filename Version Change Description 
P1x- Parameter Definition files 
R403_ADC_P1M_04_05_12_13_20
_21.arxml 
1.0.5 As part of Px4 V4.00.04 Release, following changes 
are made                                           
1. As per mantis #24237, Parameter                
AdcUseHwContiScanMode is added in AdcGroup container.                                      
2. As per mantis #27411, PDF name is modified.     
3. Copyright information is updated.               
R403_ADC_P1M_10_11_14_15_18
_19_22_23.arxml 
1.0.6 As part of Px4 V4.00.04 Release, following changes 
are made                                           
1. As per mantis #24237, Parameter              
AdcUseHwContiScanMode is added in AdcGroup container.                                      
2. As per mantis #27411, PDF name is modified.     
3. Copyright information is updated.             
BSWMDT 
R403_ADC_P1x_BSWMDT.arxml 1.0.4 As part of P1x V4.00.04 Release, following changes are made:                                          
1. Software version is updated.           
2. As per mantis #26305, critical section name  
'RAMDA TA_PROTECTION' is changed to            
'ADC_RAMDA TA_PROTECTION'.                       
3. Copyright information is updated.               
Source Code 
Adc.c 1.7.7 As part of P1x V4.00.04 Release, following changes are made: 
1. NULL check is added for 'PtrToSamplePtr' in 
Adc_GetStreamLastPointer() API. 
2. As per mantis #26305, critical section name 
'RAMDA TA_PROTECTION' is changed to 
'ADC_RAMDA TA_PROTECTION'. 
3. MISRA violation is updated. 
Adc_Irq.c 1.3.4 No change

[… 36 further page(s) not extracted …]
