---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — IssueReport CBD1400346"
description: "Converted Portable Document (vendor or generated report) from IssueReport_CBD1400346.pdf (PDF, 278 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/IssueReport_CBD1400346.pdf` (Portable Document (vendor or generated report); original PDF, about 278 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Issue Report
1
License Number Customer
CBD1400346 Nexteer Automotive Corporation
Package: GMLAN 3.1 - CANbedded License for GM; 
MultiChannel
Micro: R7F701311
Compiler: GHS 2015.1.7
Maintenance Expiry Date
2014-08-01
SIP Delivery Date SIP Version
2016-04-29 01.01.35
SLP Delivery Number
GMLAN 3.1 D01
Report Creation Date
2016-05-06
Contact
In case of questions or the need for an update of the basic software delivery, please contact 
GMSupport@us.vector.com or your Vector contact person.
Table of Contents
1. Introduction
1.1 Resolving Issues
1.2 Issue Classification
2. New Issues
2.1 Runtime Issues without Workaround: 0
2.2 Runtime Issues with Workaround: 6
2.3 Apparent Issues: 8
2.4 Not Released Functionality: 0
2.5 Compiler Warnings: 24
3. New Issues for Information: 0
4. Report Legend
5. Quality Management Contact

--- Page 2 ---
Issue Report
2
1. Introduction
1.1 Resolving Issues
Reported issues are not necessarily fixed automatically by the next update delivery. If some of the 
reported issues shall be fixed, please contact Vector to establish an agreement about issues that 
shall be fixed in upcoming deliveries. Please note that Vector may fix additional issues without 
explicit request.
1.2 Issue Classification
This Issue Report provides issues that have been detected since the last report. The issues have 
been classified to facilitate the assessment of their impact:
The chapter 'New Issues' lists issues that have been detected since the last report and which could 
not be excluded based on the use-case defined in the questionnaire. The issues are classified as 
follows:
• Runtime Issues without Workaround: Runtime issues without a workaround require an 
update of the basic software delivery in case the issue affects the ECU overall functionality. 
The effect of an issue to the ECU functionality has to be analyzed by the customer as the basic 
software usage and its configuration is not known by Vector. The risk of change has also to be 
taken into account.
• Runtime Issues with Workaround: It is not recommended to update a delivery due to a 
runtime issue with a documented workaround. The effect of an issue to the ECU functionality 
has to be analyzed by the customer as the basic software usage and its configuration is not 
known by Vector. The risk of change has also to be taken into account.
• Apparent Issues: Apparent issues are detected immediately when using the basic software. 
If an issue does not show up while working with the basic software the ECU project is not 
affected by the issue. Apparent issues may or may not have workarounds.
• Not Released Functionality: Not released functionalities are modules and features that have 
not yet passed a complete development cycle (they are e.g. not or only partly tested). For 
serial production projects the integrator has to ensure that all BETA features are disabled as 
indicated. If a ESCAN affects a complete BSW module, the module must not be used for serial 
production.
• Compiler Warnings: As a service we report the known compiler warnings. The occurrence of 
a compiler warning may depend on the used configuration and compiler settings.
The chapter 'New Issues for Information' lists issues that are not relevant for the use case that 
has been documented in the questionnaire provided to Vector. The issues may, however, be 
relevant for other use cases. Additionally, issues that have been accepted or are tolerated by the 
OEM (as defined in the questionnaire) are reported here.

--- Page 3 ---
Issue Report
3
2. New Issues
2.1 Runtime Issues without Workaround
The lists contain issues that have been detected since the last report and which could not be 
excluded based on the use-cases defined in the questionnaire (see chapter ‘New Issues for 
Information’).
2.2 Runtime Issues with Workaround
It is not recommended to update a delivery due to a runtime issue with a documented 
workaround. The effect of an issue to the ECU functionality has to be analyzed by the customer as 
the basic software usage and its configuration is not known by Vector. Thereby the risk of change 
has also to be taken into account. 
Index
ESCAN00027894 Memory is overwritten when initializing the CANBedded Stack
Nm_Gmlan_Gm@Implementation
ESCAN00045854 An incorrect timeout is issued for Flow Control and Consecutive Frame timing 
supervision.
Tp_Iso15765@GenTool_Geny
ESCAN00068912 Positive response to service $A5 03 not suppressed
Diag_CanDesc__coreBase@Implementation
ESCAN00073999 Signal handler names have wrong names after deletion of some signals of a 
DID
Diag_CanDesc__coreBase@GenTool_Geny_CANdesc
ESCAN00078197 Missing first response for service 0xA9 0x81 request
Diag_CanDesc__coreBase@Implementation
ESCAN00081145 Validity Bits for Oem GM (Consistency Checks)
GenTool_GenyObjectHierarchyCan@GenTool_Geny

--- Page 4 ---
Issue Report
4
ESCAN00027894 Memory is overwritten when initializing the 
CANBedded Stack
Component@Subcomponent: Nm_Gmlan_Gm@Implementation
First affected version: 3.30.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
Memory is overwritten when initializing the CANBedded Stack.
When does this happen:
-------------------------------------------------------------------
The issue occurs always and immediately if CclInitPowerOn or IlInitPowerOn is called with the 
configuration mentioned below.
In which configuration does this happen:
-------------------------------------------------------------------
Any configuration, where the number of Nm Channels differs from the number of Can Channels.
Hint: The generated define in kCanNumberOfChannels in can_cfg.h differs from 
kNmNumberOfChannels generated to nm_cfg.h
 
Resolution Description:
Workaround:
-------------------------------------------------------------------
Do not call IlInitPowerOn in the application. Instead, call IlInit for each channel which uses the 
Interaction Layer.
Note for GM ECUs: If the Interaction Layer is not used on the first channel in GENy (channel index 
0), the application must additionally call CanInitPowerOn before IlInit.
Example:
The ECU has three CAN channels, where the Interaction Layer is only used on the first two.
IlInit(0); /* Initialize the IL on CAN channel 0 */
IlInit(1); /* Initialize the IL on CAN channel 1 */
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

--- Page 5 ---
Issue Report
5
ESCAN00045854 An incorrect timeout is issued for Flow Control and 
Consecutive Frame timing supervision.
Component@Subcomponent: Tp_Iso15765@GenTool_Geny
First affected version: 2.00.00
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
An incorrect timeout is issued for Flow Control (TX) and Consecutive Frame (RX) timing 
supervision in case of large timeouts.
When does this happen:
-------------------------------------------------------------------
During runtime at transmission and/or reception of multi frames.
In which configuration does this happen:
-------------------------------------------------------------------
This can only appear if channel specific timing is activated (#if defined 
TP_CHANNEL_SPECIFIC_TIMING)
AND 
the configured timeout values are greater than 255 "ticks".
Please note that the number of "ticks" is calculated by dividing the configured timeout value by 
the configured periodic cycle time of the TP.
 
Resolution Description:
Workaround:
-------------------------------------------------------------------
Use smaller timeouts or increase the call-cycle of the TP task functions.
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

--- Page 6 ---
Issue Report
6
ESCAN00068912 Positive response to service $A5 03 not suppressed
Component@Subcomponent: Diag_CanDesc__coreBase@Implementation
First affected version: 6.12.01
Fixed in versions:
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
The positive response to service $A5 03 is not suppressed. 
AND possibly
The following compiler warning occurs:
 static void DescOemEnableProgrammingMode(DescMsgContext *pMsgContext)
 ^
"desc.c", Warning[Pe177]: 
 function "DescOemEnableProgrammingMode" was declared but never referenced
When does this happen:
-------------------------------------------------------------------
At runtime/compile time.
In which configuration does this happen:
-------------------------------------------------------------------
Configurations created in an older delivery affected by ESCAN00061312:
"Not possible to support negative responses while suppressing positive response for service $A5 
03"
AND
The 'Reload all description files' button on the 'Diag_CanDesc_Kwp' pa

[… 41 further page(s) not extracted …]
