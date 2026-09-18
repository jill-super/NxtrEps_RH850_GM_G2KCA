---
title: "Temperature Monitoring — ES005 TmplMonr Requirements"
description: "Converted Requirements Export from ES005 TmplMonr Requirements.pdf (PDF, 37 KB)."
---

:::note
Converted from `ES005A_TmplMonr_Design/Doc/ES005 TmplMonr Requirements.pdf` (Requirements Export; original PDF, about 37 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES005A_TmplMonr_Design](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
/ESG Group/FDD Module Requirements/EA4 Specific 
ES005A_TmplMonr 
Besilened v2.0 and Released 
Version: 2.0 
Printed by: Nayeem Mahmud 
Printed on: Friday, July 31, 2015 
Generated from DOORS 9.3.0.7

--- Page 2 ---
Contents 
1 1Interface Requirements 
1.1 1Definitions 
1.1.1 1Inputs 
1.1.2 1Outputs 
1.1.3 1Internally Defined Terms 
2 2Requirements 
2.1 2Primary Functional Requirements 
2.2 2Hardware Requirements 
2.3 2Software Requirements 
2.3.1 2Functional Requirements 
2.3.1.1 2Sub Function: Temporal Monitor Signal Generation 
2.3.1.2 2Sub Function: Temporal Monitor Initialization 
2.3.1.3 3Sub Function: Temporal Monitor Run 
2.4 3Diagnostic Requirements 
2.4.1 3Temporal Monitor Init Test Fault (NTC0x040) 
2.4.1.1 3Required Debounce Strategy 
2.4.1.2 3Requirements to Perform Diagnostic Test Conditions 
2.4.1.3 3Test Condition Negative Requirements 
2.4.1.4 4Test Condition Positive Requirements 
2.4.2 4Temporal Monitor Run Fault (NTC0x041) 
2.4.2.1 4Required Debounce Strategy 
2.4.2.2 4Requirements to Perform Diagnostic Test Conditions 
2.4.2.3 4Test Condition Negative Requirements 
2.4.2.4 5Test Condition Positive Requirements 
2.5 5Manufacturing Requirements 
Contents ii

--- Page 3 ---
Page 1 of 5 Printed Friday, July 31, 2015 
ID 
ES005A 
_7 
ES005A 
_8 
ES005A 
_9 
ES005A 
_92 
ES005A 
_93 
ES005A 
_106 
ES005A 
_13 
ES005A 
_96 
ES005A 
_97 
ES005A 
_100 
ES005A 
_101 
ES005A 
_102 
ES005A 
_103 
Besilened v2.0 and Released 
1 Interface Requirements 
1.1 Definitions 
1.1.1 Inputs 
PwrOutpEnaFb  : A physical feedback input signal to verify that temporal monitor function is properly 
working. 
NErr: An input signal used to decide PwrOutpEna hi or low state. 
StrtUpSt : Startup State enumeration input is used to decide when Temporal Monitor function should 
start. 
1.1.2 Outputs 
PwrOutpEna :  This physical output when driven high will enable power to the Gate Drive(s). 
TmplMonrIninTestCmpl : An output flag to notify Temporal Monitor Initializaion test completed or 
not-completed .
1.1.3 Internally Defined Terms 
TmplMonrWdg :  Physical square wave output used for Temporal Monitor verification. 
SysFlt2A :  An output signal generated to control the power pass of Gate Drive A. 
SysFlt2B :  An output signal generated to control the power pass of Gate Drive B.

--- Page 4 ---
Page 2 of 5 Printed Friday, July 31, 2015 
ID 
ES005A 
_20 
ES005A 
_21 
ES005A 
_144 
ES005A 
_169 
ES005A 
_22 
ES005A 
_126 
ES005A 
_23 
ES005A 
_24 
ES005A 
_25 
ES005A 
_29 
ES005A 
_104 
ES005A 
_31 
ES005A 
_32 
ES005A 
_108 
ES005A 
_107 
Besilened v2.0 and Released 
2 Requirements 
2.1 Primary Functional Requirements 
The Temporal Monitor function shall detect an error of ±11% in the Primary Processor clock within 
200ms. 
The Temporal Monitor function shall provide a mechanism to store its sequence number 
(TmplMonrIninCntr) into the per-instance menory. 
2.2 Hardware Requirements 
None 
2.3 Software Requirements 
2.3.1 Functional Requirements 
2.3.1.1 Sub Function: Temporal Monitor Signal Generation 
The Temporal Monitor function shall generate TmplMonrWdg  square wave signal with the following 
characteristics. 
Period = 2ms ± 0.12ms 
Duty Cycle =  50 ± 30% 
2V < Vmax  < 5 V 
-0.1 V > Vmin <  0.5 V 
The Temporal Monitor function shall generate TmplMonrWdg signal by toggling a GPIO pin from 
Temporal Monitor Software Function. 
2.3.1.2 Sub Function: Temporal Monitor Initialization 
The Temporal Monitor function shall perform initialization test at Warm Init state once per ignition 
cycle. 
The Temporal Monitor function shall start Temporal Monitor Initialization when StrtUpSt  = 
ELECGLBPRM_STRTUPSTTMPLMONININTESTSTRT_CNT_U08 & Tm plMonrIninTestCmplFlg 
= 1. 
The Temporal Monitor Function shall generate TmplMonrWdg  for 8 periodic execution followed by a 
constant LOW value signal for 8 periodic execution as part of Temporal Monitor Initialization.

--- Page 5 ---
Page 3 of 5 Printed Friday, July 31, 2015 
ID 
ES005A 
_167 
ES005A 
_110 
ES005A 
_111 
ES005A 
_122 
ES005A 
_168 
ES005A 
_125 
ES005A 
_124 
ES005A 
_145 
ES005A 
_146 
ES005A 
_147 
ES005A 
_157 
ES005A 
_149 
ES005A 
_158 
ES005A 
_170 
ES005A 
_150 
ES005A 
_163 
Besilened v2.0 and Released 
The Temporal Monitor Function shall verify that it has control over PwrOutpEna  signal by forcing a 
fault and monitoring the feedback signal. 
The Temporal Monitor function shall issue a FLASH_MODE command through SPI if re-flash is 
requested. 
The Temporal Monitor function shall issue a WD_RESTART command through SPI to get out of flash 
mode once re-programming is done. 
2.3.1.3 Sub Function: Temporal Monitor Run 
The Temporal Monitor function shall increment the internal valid counter value by 1 if 10 subsequent 
rising edges of 2 ms ± 0.12 ms square wave pulses are present over a 20 ms moving window after the 
Temporal Monitor Initialization.. 
The Temporal Monitor function shall qualify TmplMonrWdg signal when the internal valid counter 
value reaches to a predefined SPI configured value.
The Temporal Monitor function shall continue monitoring and qualifying the TmplMonrWdg signal 
during the rest of the ignition cycle. 
2.4 Diagnostic Requirements 
2.4.1 Temporal Monitor Init Test Fault (NTC0x040) 
2.4.1.1 Required Debounce Strategy 
The Temporal Monitor function use the  Immediate fault strategy for NTC0x040. 
2.4.1.2 Requirements to Perform Diagnostic Test Conditions 
The Temporal Monitor function shall perform the test condition for NTC0x040 during the Temporal 
Monitor Initialization and only once per ignition cycle. 
The Temporal Monitor function shall perform the test condition for NTC0x040 during the sequence 
number ( TmplMonrIninCntr) 8 to 50. 
2.4.1.3 Test Condition Negative Requirements 
The Temporal Monitor function shall provide a negative result for NTC0x040, when the  sequence 
number is 8-10 and PwrOutpEna  is not High.

--- Page 6 ---
Page 4 of 5 Printed Friday, July 31, 2015 
ID 
ES005A 
_171 
ES005A 
_172 
ES005A 
_173 
ES005A 
_177 
ES005A 
_176 
ES005A 
_175 
ES005A 
_178 
ES005A 
_151 
ES005A 
_164 
ES005A 
_152 
ES005A 
_153 
ES005A 
_159 
ES005A 
_154 
ES005A 
_160 
ES005A 
_174 
ES005A 
_155 
Besilened v2.0 and Released 
The Temporal Monitor function shall provide a negative result for NTC0x040, when the  sequence 
number is 12 and PwrOutpEna  is not Low. 
The Temporal Monitor function shall provide a negative result for NTC0x040, when the  sequence 
number is 13-15 and PwrOutpEna  is not High. 
The Temporal Monitor function shall provide a negative result for NTC0x040, when the  sequence 
number is 16 and PwrOutpEna  is not Low. 
The Temporal Monitor function shall provide a negative result for NTC0x040, when the  sequence 
number is 17 and Watchdog State = Idle or Flash or Test Hunt or Watchdog. 
The Temporal Monitor function shall provide a negative result for NTC0x040, when the  sequence 
number is 19 and Edge and Valid Counter value is not written properly. 
The Temporal Monitor function shall provide a negative result for NTC0x040, when the  sequence 
number is 50 and PwrOutpEna  is LOW and Watchdog State = Watchdog. 
The Temporal Monitor function shall provide a negative result for NTC0x040, when the  sequence 
number is 50 and PwrOutpEna  is LOW and Watchdog State is not Watchdog. 
2.4.1.4 Test Condition Positive Requirements 
The Temporal Monitor function shall provide a positive result to the test condition for NTC 0x040 
when none of the negative result requirements are satisfied. 
2.4.2 Temporal Monitor Run Fault (NTC0x041) 
2.4.2.1 Required Debounce Strategy 
The Temporal Monitor function use the  Immediate fault strategy for NTC0x041. 
2.4.2.2 Requirements to Perform Diagnostic Test Conditions 
The Temporal Monitor function shall perform the test condition for NTC0x041 in ENABLE.. 
The Temporal Monitor function shall perform the test condition for NTC0x041 when the sequesnce 
number is greater than 50. 
2.4.2.3 Test Condition Negative Requirements

[… 1 further page(s) not extracted …]
