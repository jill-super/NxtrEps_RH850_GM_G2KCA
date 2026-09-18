---
title: "Polarity Configuration — ES102A PolarityCfg DDReport"
description: "Converted Design Document / Report from ES102A_PolarityCfg_DDReport.txt (TXT, 3 KB)."
---

:::note
Converted from `ES102A_PolarityCfg_Design/Reports/ES102A_PolarityCfg_DDReport.txt` (Design Document / Report; original TXT, about 3 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES102A_PolarityCfg_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of ES102A_PolarityCfg_DataDict
29-Apr-2016 13:35:42
Tool Release:  2.38.0



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
PolarityCfgRead             	.SrvRunnnable:	Name should not contain FDDs <ShoName>
PolarityCfgWr               	.SrvRunnnable:	Name should not contain FDDs <ShoName>
(variables: 2, errors: 2)

-----------------------
Client:	<TriggerName>
-------------------------
PolarityCfgSaved_SetRamBlockStatus	.Client:	Name should not contain FDDs <ShoName>
(variables: 1, errors: 1)

----------------------------
INPUT SIGNALS:	<Identity>
----------------------------
(variables: 0, errors: 0)

-----------------------------
OUTPUT SIGNALS:	<Identity>
-----------------------------
(variables: 26, errors: 0)

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
PolarityCfgSaved            	Name does not match required pattern.
(variables: 1, errors: 1)

------------------------------------------
DISPLAY VARIABLES:	d<ShoName><Identity>
------------------------------------------
(variables: 0, errors: 0)

-----------------------------------------------
PER-INSTANCE MEMORY:	<Identity>
-----------------------------------------------
(variables: 0, errors: 0)

--------------------------------------------------------------------------------------------
CONSTANTS:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
(variables: 0, errors: 0)

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
32 variables,  4 issues to fix.


End of Report

```
