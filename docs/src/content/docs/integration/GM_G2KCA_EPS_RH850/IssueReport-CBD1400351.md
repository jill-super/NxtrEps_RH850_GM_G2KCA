---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — IssueReport CBD1400351"
description: "Converted Portable Document (vendor or generated report) from IssueReport_CBD1400351.pdf (PDF, 399 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/DeliveryInformation/IssueReport_CBD1400351.pdf` (Portable Document (vendor or generated report); original PDF, about 399 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Issue Report
1
License Number Customer
CBD1400351 Nexteer Automotive Corporation
Package: GM Global A / FR - ECU Product "Steering 
Systems"
Micro: R7F701311
Compiler: GHS 2013.5.5
Maintenance Expiry Date
2015-09-01
SIP Delivery Date SIP Version
2015-10-23 13.00.00
SLP Delivery Number
GM Global A / FR D03
Report Creation Date
2015-10-23
Contact
In case of questions or the need for an update of the basic software delivery, please contact 
Ralf.Fritz@vector.com or your Vector contact person.
Table of Contents
1. Introduction
1.1 Resolving Issues
1.2 Issue Classification
2. New Issues
2.1 Runtime Issues without Workaround: 5
2.2 Runtime Issues with Workaround: 11
2.3 Apparent Issues: 51
2.4 Compiler Warnings: 9
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
• Compiler Warnings: As a service we report the known compiler warnings. The occurrence of 
a compiler warning may depend on the used configuration and compiler settings.
• Apparent Issues: Apparent issues are detected immediately when using the basic software. 
If an issue does not show up while working with the basic software the ECU project is not 
affected by the issue. Apparent issues may or may not have workarounds.
The chapter 'New Issues for Information' lists issues that are not relevant for the use case that 
has been documented in the questionnaire provided to Vector. The issues may, however, be 
relevant for other use cases. Additionally, issues that have been accepted or are tolerated by the 
OEM (as defined in the questionnaire) are reported here.

--- Page 3 ---
Issue Report
3
2. New Issues

--- Page 4 ---
Issue Report
4
2.1 Runtime Issues without Workaround
The lists contain issues that have been detected since the last report and which could not be 
excluded based on the use-cases defined in the questionnaire (see chapter ‘New Issues for 
Information’).

--- Page 5 ---
Issue Report
5
ESCAN00076676 'initializing' : truncation from 'SomeBigDataType' to 
'SomeSmallerDataType'
Component@Subcomponent: CommonAsr_ComStackLib@GenTool_GeneratorMsr
First affected version: 4.00.00
Fixed in versions: 4.00.01
 
Problem Description:
What happens (symptoms):
-------------------------------------------------------------------
a compiler warning like the following occurs:
warning C4305: 'initializing' : truncation from 'SomeBigDataType' to 'SomeSmallerDataType'
when you are using the code
Nevertheless, the consequence for the ECU is unpredictable.
When does this happen:
-------------------------------------------------------------------
The warning is issued by the compiler during compilation of the code in case the configuration is 
as described below. 
In which configuration does this happen:
-------------------------------------------------------------------
Any configuration using generated index based data types which are NOT changeable at postbuild 
time.
AND 
the code has been generated by Com or IpduM or PduR or LdCom or BswM.
 
Resolution Description:
Workaround:
-------------------------------------------------------------------
Il_AsrComCfg5: Configure ComMinimizeNumericalDataTypes to NONE.
Il_AsrIpduMCfg5: Configure IpduMMinimizeNumericalDataTypes to NONE.
Gw_AsrPduRCfg5: Configure PduRMinimizeNumericalDataTypes to NONE.
Il_AsrLdCom: No workaround available.
SysService_Asr4BswMCfg5: No workaround available.
Tp_Asr4TpLin: Not affected.
If_Asr4IfLin: Not affected.
If_AsrIfCan: Not affected.
SysService_Asr4EcuM: Not affected.
Ccl_Asr4ComMCfg5: Not affected.
Cdd_AsrCddCfg5: Not affected
Cdd_AsrCddCfg5: Not affected
EcuC_AsrEcuC: Not affected
Resolution:
-------------------------------------------------------------------
The described issue is corrected by modification of all affected work-products.

--- Page 6 ---
Issue Report
6
ESCAN00079240 Undefined ECU behavior due to invalid index access 
in 0:* and 1:* Relations
Component@Subcomponent: CommonAsr_ComStackLib@GenTool_GeneratorMsr
First affected version: 4.00.00
Fixed in versions: 5.00.01
 
Problem Description:

[… 84 further page(s) not extracted …]
