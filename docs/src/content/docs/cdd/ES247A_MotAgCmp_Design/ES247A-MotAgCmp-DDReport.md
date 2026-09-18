---
title: "Motor Angle Comparison — ES247A MotAgCmp DDReport"
description: "Converted Design Document / Report from ES247A_MotAgCmp_DDReport.txt (TXT, 3 KB)."
---

:::note
Converted from `ES247A_MotAgCmp_Design/Reports/ES247A_MotAgCmp_DDReport.txt` (Design Document / Report; original TXT, about 3 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES247A_MotAgCmp_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of ES247A_MotAgCmp_DataDict
06-Nov-2015 10:20:17
Tool Release:  2.22.0



--------------------------------
DATA CLASS VIOLATION CHECKS
--------------------------------
(errors: 0)

---------------------------------------------------------------
FDD DEFINITION VARIABLE:	<Type><Number><Variant>  e.g. SF99A
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
SrvRunnable:	<ShoName><TriggerName>
--------------------------------------
(variables: 2, errors: 0)

------------
Client:	
------------
(variables: 1, errors: 0)

----------------------------
INPUT SIGNALS:	<Identity>
----------------------------
MotAgCumvAlgndMrfRev        	Cannot match name to list of known Nexteer signals.
(variables: 3, errors: 1)

-----------------------------
OUTPUT SIGNALS:	<Identity>
-----------------------------
(variables: 4, errors: 0)

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
(variables: 1, errors: 0)

-------------------------------------------
NON-VOLATILE MEMORY:	<Identity>
-------------------------------------------
MotAgCmpMotAgBackEmf        	Name does not match required pattern.
(variables: 1, errors: 1)

------------------------------------------
DISPLAY VARIABLES:	d<ShoName><Identity>
------------------------------------------
(variables: 0, errors: 0)

-----------------------------------------------
PER-INSTANCE MEMORY:	<Identity>
-----------------------------------------------
MotAgCmpFirstRunCmpl        	Name does not match required pattern.
MotAgCmpMotCtrlMotAgCumvAlgndMrfRevPrev	Name does not match required pattern.
MotAgCmpMotCtrlMotAgMeclPrev	Name does not match required pattern.
(variables: 3, errors: 3)

--------------------------------------------------------------------------------------------
CONSTANTS:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
(variables: 4, errors: 0)

----------------
CSArguments:	
----------------
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
22 variables,  5 issues to fix.


End of Report

```
