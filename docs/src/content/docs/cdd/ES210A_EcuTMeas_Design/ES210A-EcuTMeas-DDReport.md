---
title: "Electronic Control Unit Temperature Measurement — ES210A EcuTMeas DDReport"
description: "Converted Design Document / Report from ES210A_EcuTMeas_DDReport.txt (TXT, 3 KB)."
---

:::note
Converted from `ES210A_EcuTMeas_Design/Reports/ES210A_EcuTMeas_DDReport.txt` (Design Document / Report; original TXT, about 3 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES210A_EcuTMeas_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of ES210A_EcuTMeas_DataDict
28-Apr-2016 17:28:53
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
(variables: 2, errors: 0)

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
EcuTAdcFaild                	Cannot match name to list of known Nexteer signals.
(variables: 3, errors: 1)

-----------------------------
OUTPUT SIGNALS:	<Identity>
-----------------------------
(variables: 1, errors: 0)

---------------------------------------
INTER-RUNNABLE VARIABLES:	<Identity>
---------------------------------------
(variables: 0, errors: 0)

------------------------------------
CALIBRATIONS:	<ShoName><Identity>
------------------------------------
(variables: 8, errors: 0)

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
(variables: 0, errors: 0)

-----------------------------------------------
PER-INSTANCE MEMORY:	<Identity>
-----------------------------------------------
EcuTMeasFilStVarPrev        	Name does not match required pattern.
EcuTMeasFilStVarPrev        	    Var            Unknown Keyword used.Only Nexteer approved Keywords should be used.
(variables: 1, errors: 2)

--------------------------------------------------------------------------------------------
CONSTANTS:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
(variables: 1, errors: 0)

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
TMeasFlt            	Found in data dictionary but not in model.
(variables: 2, errors: 1)

------
OTHER:
------
(variables: 0, errors: 0)
 
************************
Grand Totals:
20 variables,  4 issues to fix.


End of Report

```
