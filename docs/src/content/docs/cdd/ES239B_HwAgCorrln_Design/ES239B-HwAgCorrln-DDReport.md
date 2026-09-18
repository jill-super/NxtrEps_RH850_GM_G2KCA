---
title: "Handwheel Angle Correlation — ES239B HwAgCorrln DDReport"
description: "Converted Design Document / Report from ES239B_HwAgCorrln_DDReport.txt (TXT, 3 KB)."
---

:::note
Converted from `ES239B_HwAgCorrln_Design/Reports/ES239B_HwAgCorrln_DDReport.txt` (Design Document / Report; original TXT, about 3 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES239B_HwAgCorrln_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of ES239B_HwAgCorrln_DataDict
25-Aug-2016 17:09:58
Tool Release:  2.45.0



--------------------------------
DATA CLASS VIOLATION CHECKS
--------------------------------
(errors: 0)

---------------------------------------------------------------
FDD DEFINITION VARIABLE:	<Type><Number><Variant>  e.g. SF099A
--------------------------------------------------------------
(variable: 1, errors: 0)

----------------------------
DATA DICTIONARY FILENAME:
----------------------------
(errors:  0)

------------------------------------------------------------
RUNNABLE:	<ShoName>Per<Number>  or  <ShoName>Init<Number>
------------------------------------------------------------
(variables: 1, errors: 0)

--------------------------------------
SrvRunnable:	<TriggerName>
--------------------------------------
(variables: 0, errors: 0)

-----------------------
Client:	<TriggerName>
-------------------------
(variables: 1, errors: 0)

----------------------------
INPUT SIGNALS:	<Identity>
----------------------------
HwAgA                       	Cannot match name to list of known Nexteer signals.
HwAgAQlfr                   	Cannot match name to list of known Nexteer signals.
HwAgARollgCntr              	Cannot match name to list of known Nexteer signals.
(variables: 3, errors: 3)

-----------------------------
OUTPUT SIGNALS:	<Identity>
-----------------------------
HwAgCorrlnSt                	Name does not match required pattern.
(variables: 2, errors: 1)

---------------------------------------
INTER-RUNNABLE VARIABLES:	<Identity>
---------------------------------------
(variables: 0, errors: 0)

------------------------------------
CALIBRATIONS:	<ShoName><Identity>
------------------------------------
(variables: 0, errors: 0)

----------------------------------------------
IMPORTED CALIBRATIONS:	<ShoName><Identity>
---------------------------------------------
(variables: 0, errors: 0)

-------------------------------------------
NON-VOLATILE MEMORY:	<Identity>
-------------------------------------------
(variables: 0, errors: 0)

------------------------------------------
DISPLAY VARIABLES:	d<ShoName><Identity>
------------------------------------------
(variables: 1, errors: 0)

-----------------------------------------------
PER-INSTANCE MEMORY:	<Identity>
-----------------------------------------------
(variables: 2, errors: 0)

--------------------------------------------------------------------------------------------
CONSTANTS:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
FLTINJ_HWAGCORRLN_HWAGIDPTSIG    	Name does not match required pattern as it is a special case.
(variables: 2, errors: 1)

-------------------------
CSArguments:	<IDENTITY>
---------------------------
(variables: 0, errors: 0)

--------------------------------------------------------------------------------------------
CONFIGPARAM:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
(variables: 0, errors: 0)

----------------------------
NTC SIGNALS:	<Identity>
----------------------------
(variables: 0, errors: 0)

------
OTHER:
------
(variables: 0, errors: 0)
 
************************
Grand Totals:
13 variables,  5 issues to fix.


End of Report

```
