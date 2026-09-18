---
title: "Motor Velocity — SF040A MotVel DDReport"
description: "Converted Design Document / Report from SF040A_MotVel_DDReport.txt (TXT, 3 KB)."
---

:::note
Converted from `SF040A_MotVel_Design/Reports/SF040A_MotVel_DDReport.txt` (Design Document / Report; original TXT, about 3 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF040A_MotVel_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of SF040A_MotVel_DataDict
19-Sep-2016 16:06:41
Tool Release:  2.46.0



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
(variables: 3, errors: 0)

--------------------------------------
SrvRunnable:	<TriggerName>
--------------------------------------
(variables: 0, errors: 0)

-----------------------
Client:	<TriggerName>
-------------------------
(variables: 0, errors: 0)

----------------------------
INPUT SIGNALS:	<Identity>
----------------------------
MotCtrlMotAgBuf_SigIn       	Found in model but not in data dictionary.
MotCtrlMotAgTiBuf_SigIn     	Found in model but not in data dictionary.
(variables: 5, errors: 2)

-----------------------------
OUTPUT SIGNALS:	<Identity>
-----------------------------
MotVelCrf                   	Name does not match required pattern.
MotVelMrf                   	Name does not match required pattern.
MotCtrlMotAgBuf_SigOut      	Found in model but not in data dictionary.
MotCtrlMotAgTiBuf_SigOut    	Found in model but not in data dictionary.
(variables: 6, errors: 4)

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
(variables: 0, errors: 0)

------------------------------------------
DISPLAY VARIABLES:	d<ShoName><Identity>
------------------------------------------
(variables: 3, errors: 0)

-----------------------------------------------
PER-INSTANCE MEMORY:	<Identity>
-----------------------------------------------
MotVelIninCntr              	Name does not match required pattern.
(variables: 5, errors: 1)

--------------------------------------------------------------------------------------------
CONSTANTS:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
(variables: 13, errors: 0)

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
37 variables,  7 issues to fix.


End of Report

```
