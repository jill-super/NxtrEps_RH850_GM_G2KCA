---
title: "Inertia Compensation by Velocity — SF014A InertiaCmpVel DDReport"
description: "Converted Design Document / Report from SF014A_InertiaCmpVel_DDReport.txt (TXT, 3 KB)."
---

:::note
Converted from `SF014A_InertiaCmpVel_Design/Reports/SF014A_InertiaCmpVel_DDReport.txt` (Design Document / Report; original TXT, about 3 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF014A_InertiaCmpVel_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of SF014A_InertiaCmpVel_DataDict
19-Sep-2016 14:05:20
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
InertiaCmpVelCmdDi          	Name does not match required pattern.
(variables: 8, errors: 1)

-----------------------------
OUTPUT SIGNALS:	<Identity>
-----------------------------
InertiaCmpVelCmd            	Name does not match required pattern.
(variables: 1, errors: 1)

---------------------------------------
INTER-RUNNABLE VARIABLES:	<Identity>
---------------------------------------
(variables: 0, errors: 0)

------------------------------------
CALIBRATIONS:	<ShoName><Identity>
------------------------------------
(variables: 24, errors: 0)

----------------------------------------------
IMPORTED CALIBRATIONS:	<ShoName><Identity>
---------------------------------------------
(variables: 3, errors: 0)

-------------------------------------------
NON-VOLATILE MEMORY:	<Identity>
-------------------------------------------
(variables: 0, errors: 0)

------------------------------------------
DISPLAY VARIABLES:	d<ShoName><Identity>
------------------------------------------
(variables: 11, errors: 0)

-----------------------------------------------
PER-INSTANCE MEMORY:	<Identity>
-----------------------------------------------
(variables: 9, errors: 0)

--------------------------------------------------------------------------------------------
CONSTANTS:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
FLTINJ_INERTIACMPVEL_INERTIACMPCMD	Name does not match required pattern as it is a special case.
(variables: 9, errors: 1)

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
69 variables,  3 issues to fix.


End of Report

```
