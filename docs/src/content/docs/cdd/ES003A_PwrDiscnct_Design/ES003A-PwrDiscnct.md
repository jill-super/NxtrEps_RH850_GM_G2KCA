---
title: "Power Disconnect — ES003A PwrDiscnct"
description: "Converted Portable Document (vendor or generated report) from ES003A_PwrDiscnct.pdf (PDF, 37 KB)."
---

:::note
Converted from `ES003A_PwrDiscnct_Design/Doc/ES003A_PwrDiscnct.pdf` (Portable Document (vendor or generated report); original PDF, about 37 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES003A_PwrDiscnct_Design](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
/ESG Group/FDD Module Requirements/EA4 Specific 
ES003A_PwrDiscnct 
ES003A_PowerDisconnect 
Version: 0.0 
Printed by: Rakesh Prabhakara 
Printed on: Thursday, March 26, 2015 
Generated from DOORS 9.5.1.2

--- Page 2 ---
Contents 
1 1Purpose 
2 2Interface Requirements 
2.1 2Definitions 
2.1.1 2Inputs 
2.1.2 2Outputs 
2.1.3 2Internally Defined Terms 
3 4Requirements 
3.1 4Primary Functional Requirements 
3.2 4Hardware Requirements 
3.3 4Software Requirements 
3.3.1 4Special Execution Requirements 
3.3.2 4Functional Requirements 
3.3.2.1 4Sub-Function: Calculate Delta Voltage 
3.3.2.2 4Sub-Function: Power Disconnect Sequence A Control 
3.3.2.3 5Sub-Function: Power Disconnect Sequence B Control 
3.4 5Diagnostic Requirements 
3.4.1 5Power Disconnect Fault for Inverter1 at Init (NTC 0x042) 
3.4.1.1 5Required Debounce Strategy 
3.4.1.2 5Requirements to Perform Diagnostic Test Conditions 
3.4.1.3 5Test Condition Negative Requirements 
3.4.1.4 5Test Condition Positive Requirements 
3.4.2 5Power Disconnect Fault for Inverter2 at Init (NTC 0x4A) 
3.4.2.1 5Required Debounce Strategy 
3.4.2.2 5Requirements to Perform Diagnostic Test Conditions 
3.4.2.3 6Test Condition Negative Requirements 
3.4.2.4 6Test Condition Positive Requirements 
Contents ii

--- Page 3 ---
Page 1 of 6 Printed Thursday, March 26, 2015 
ID 
ES003A 
_1 
ES003A_PowerDisconnect 
1 Purpose

--- Page 4 ---
Page 2 of 6 Printed Thursday, March 26, 2015 
ID 
ES003A 
_2 
ES003A 
_5 
ES003A 
_6 
ES003A 
_9 
ES003A 
_10 
ES003A 
_11 
ES003A 
_12 
ES003A 
_13 
ES003A 
_106 
ES003A 
_7 
ES003A 
_20 
ES003A 
_15 
ES003A 
_14 
ES003A 
_8 
ES003A 
_17 
ES003A_PowerDisconnect 
2 Interface Requirements 
2.1 Definitions 
2.1.1 Inputs 
For the purposes of this document, the input signals are referred to as stated in the following (note each 
input is identified in a separate object for linking purposes to the design): 
Defined terms used in the document shall be in bold text .
BattVltg: ADC Converted representation of Battery Voltage (Upstream of Power Disconnect) 
BattVltgSwd1: ADC Converted representation of Switch Voltage from Inverter 1 (Downstream of 
Power Disconnect) 
BattVltgSwd2: ADC Converted representation of Switch Voltage from Inverter 2(Downstream of 
Power Disconnect) 
ELECGLBPRM_IVTRCNT_CNT_U08: Number of Inverters 
StrtUpSt: Comprehensive collection of start-up bits indicating Power Up Sequence Type 
2.1.2 Outputs 
For the purposes of this document, the input signals are referred to as stated in the following (note each 
input is identified in a separate object for linking purposes to the design): 
Defined terms used in the document shall be in bold text .
PwrDiscnctATestCmpl : Flag Indicating that the sequence A is complete 
PwrDiscnctBTestCmpl: Flag Indicating that the sequence B is complete 
2.1.3 Internally Defined Terms 
For the purposes of this document, the internally defined variables are referred to as stated in the 
following (note each input is identified in a separate object for linking purposes to the design): 
Defined terms used in the document shall be in underlined text .

--- Page 5 ---
Page 3 of 6 Printed Thursday, March 26, 2015 
ID 
ES003A 
_21 
ES003A 
_23 
ES003A 
_18 
ES003A 
_22 
ES003A 
_74 
ES003A 
_75 
ES003A_PowerDisconnect 
DeltaVltg1 : This indiactes the difference between BattVltg and BattVltgSwd1. 
DeltaVltg2 : This indiactes the difference between BattVltg and BattVltgSwd2 
PwrDisncntMaxSwdVltg : Field configurable variable that indicates largest voltage at which 
BattVltgSwd1 and BattVltgSwd2 saturate (nominally 16V) 
PwrDiscnctOpenThd : Voltage threshold for determining BattVltgSwd1 and BattVltgSwd2 is open 
PwrDiscnctSequenceA : PwrDiscnctSequenceA are the necessary steps performed by this function 
before the power disconnect is allowed to be closed. 
PwrDiscnctSequenceB : PwrDiscnctSequenceB are the necessary steps performed by this function after 
the power disconnect has been closed.

--- Page 6 ---
Page 4 of 6 Printed Thursday, March 26, 2015 
ID 
ES003A 
_3 
ES003A 
_25 
ES003A 
_26 
ES003A 
_27 
ES003A 
_48 
ES003A 
_28 
ES003A 
_97 
ES003A 
_98 
ES003A 
_99 
ES003A 
_53 
ES003A 
_56 
ES003A 
_50 
ES003A 
_76 
ES003A 
_46 
ES003A 
_47 
ES003A_PowerDisconnect 
3 Requirements 
3.1 Primary Functional Requirements 
The "Power Disconnect" Function shall verify that the PowerDisconnect is not stuck closed at 
initialization once per Ignition Cycle. 
3.2 Hardware Requirements 
NONE 
3.3 Software Requirements 
3.3.1 Special Execution Requirements 
The "Power Disconnect" function shall provide mechanism to split its startup procedure into pre-close 
(PwrDiscnctSequenceA ) and post-close (PwrDiscnctSequenceB ). This is necessary because a separate 
function is actually responsible for closing the power disconnect. 
The "Power Disconnect" Function shall provide mechanism for its startup sequences to wait for 
StrtUpSt  to performs its actions. 
3.3.2 Functional Requirements 
3.3.2.1 Sub-Function: Calculate Delta Voltage 
The "Power Disconnect" Function shall  calculate DeltaVltg1 for BattVltgSwd1 as below: 
DeltaVltg1 = Abs(Min(PwrDiscnctMaxSwdVltg , BattVltg ) - BattVltgSwd1) ;
The "Power Disconnect" Function shall calculate DeltaVltg2 for BattVltgSwd2  as below: 
DeltaVltg2 = Abs(Min(PwrDiscnctMaxSwdVltg , BattVltg ) - BattVltgSwd2) ; (Only when  IvtrCnt = 
2) 
3.3.2.2 Sub-Function: Power Disconnect Sequence A Control 
The "Power Disconnect" Function shall verify if the EPS Primary Disconnect is not stuck closed in 
PwrDiscnctSequenceA.

[… 2 further page(s) not extracted …]
