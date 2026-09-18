---
title: "Microcontroller Diagnostic — ES002A McuDiagc DDReport"
description: "Converted Design Document / Report from ES002A_McuDiagc_DDReport.txt (TXT, 3 KB)."
---

:::note
Converted from `ES002A_McuDiagc_Design/Reports/ES002A_McuDiagc_DDReport.txt` (Design Document / Report; original TXT, about 3 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES002A_McuDiagc_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of ES002A_McuDiagc_DataDict
04-Oct-2016 09:50:17
Tool Release:  2.43.0



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
(variables: 1, errors: 0)

----------------------------
INPUT SIGNALS:	<Identity>
----------------------------
FastLoopCntr                	Cannot match name to list of known Nexteer signals.
MotCtrlLoopCntr2MilliSec    	Cannot match name to list of known Nexteer signals.
SlowLoopCntr                	Cannot match name to list of known Nexteer signals.
(variables: 3, errors: 3)

-----------------------------
OUTPUT SIGNALS:	<Identity>
-----------------------------
LoopCntr2MilliSec           	Cannot match name to list of known Nexteer signals.
MotCtrlFastLoopCntr         	Cannot match name to list of known Nexteer signals.
MotCtrlSlowLoopCntr         	Cannot match name to list of known Nexteer signals.
(variables: 3, errors: 3)

---------------------------------------
INTER-RUNNABLE VARIABLES:	<Identity>
---------------------------------------
(variables: 0, errors: 0)

------------------------------------
CALIBRATIONS:	<ShoName><Identity>
------------------------------------
(variables: 3, errors: 0)

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
(variables: 3, errors: 0)

-----------------------------------------------
PER-INSTANCE MEMORY:	<Identity>
-----------------------------------------------
(variables: 4, errors: 0)

--------------------------------------------------------------------------------------------
CONSTANTS:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
(variables: 5, errors: 0)

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
McuDiagcFlt                 	Name does not match required pattern.
(variables: 1, errors: 1)

------
OTHER:
------
Unit Delay:                 	'Unit Delay Block'	'StateMustResolveToSignalObject' property must be enabled.
Unit Delay1:                	'Unit Delay Block'	'StateMustResolveToSignalObject' property must be enabled.
(variables: 0, errors: 2)
 
************************
Grand Totals:
27 variables,  9 issues to fix.


End of Report

```
