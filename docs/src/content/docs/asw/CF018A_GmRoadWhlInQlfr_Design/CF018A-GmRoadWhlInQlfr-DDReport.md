---
title: "General Motors Road Wheel Input Qualifier — CF018A GmRoadWhlInQlfr DDReport"
description: "Converted Design Document / Report from CF018A_GmRoadWhlInQlfr_DDReport.txt (TXT, 3 KB)."
---

:::note
Converted from `CF018A_GmRoadWhlInQlfr_Design/Reports/CF018A_GmRoadWhlInQlfr_DDReport.txt` (Design Document / Report; original TXT, about 3 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CF018A_GmRoadWhlInQlfr_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of CF018A_GmRoadWhlInQlfr_DataDict
23-Mar-2016 15:55:22
Tool Release:  2.30.0



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
(variables: 2, errors: 0)

--------------------------------------
SrvRunnable:	<TriggerName>
--------------------------------------
(variables: 0, errors: 0)

-----------------------
Client:	<TriggerName>
-------------------------
(variables: 3, errors: 0)

----------------------------
INPUT SIGNALS:	<Identity>
----------------------------
WhlPlsPerRev                	.DocUnits:	Not on approved list.
WhlRotlStsTiStampResl       	.DocUnits:	Not on approved list.
(variables: 8, errors: 2)

-----------------------------
OUTPUT SIGNALS:	<Identity>
-----------------------------
(variables: 3, errors: 0)

---------------------------------------
INTER-RUNNABLE VARIABLES:	<Identity>
---------------------------------------
(variables: 0, errors: 0)

------------------------------------
CALIBRATIONS:	<ShoName><Identity>
------------------------------------
(variables: 2, errors: 0)

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
(variables: 8, errors: 0)

-----------------------------------------------
PER-INSTANCE MEMORY:	<Identity>
-----------------------------------------------
PrevRawLeWhlFrq             	.EngMax:    	Value is unusually high.
PrevRawRiWhlFrq             	.EngMax:    	Value is unusually high.
(variables: 12, errors: 2)

--------------------------------------------------------------------------------------------
CONSTANTS:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
(variables: 12, errors: 0)

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
NTCNR_0X0E3         	Found in model but not in data dictionary.
(variables: 1, errors: 1)

------
OTHER:
------
(variables: 0, errors: 0)
 
************************
Grand Totals:
52 variables,  5 issues to fix.


End of Report

```
