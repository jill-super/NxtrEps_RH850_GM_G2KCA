---
title: "Fault Injection — DF001A FltInj DDReport"
description: "Converted Design Document / Report from DF001A_FltInj_DDReport.txt (TXT, 11 KB)."
---

:::note
Converted from `DF001A_FltInj_Design/Reports/DF001A_FltInj_DDReport.txt` (Design Document / Report; original TXT, about 11 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to DF001A_FltInj_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of DF001A_FltInj_DataDict
14-Jun-2016 06:43:45
Tool Release:  2.41.0



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
FltInj_logl                 	    Inj_logl       Unknown Keyword used.Only Nexteer approved Keywords should be used.
UpdUsrPrm                   	Found in model but not in data dictionary.
(variables: 4, errors: 2)

-----------------------
Client:	<TriggerName>
-------------------------
(variables: 2, errors: 0)

----------------------------
INPUT SIGNALS:	<Identity>
----------------------------
FltInjUsrPrm_ArgIn          	Found in model but not in data dictionary.
SigPah_ArgIn1               	Found in model but not in data dictionary.
SigPah_ArgIn2               	Found in model but not in data dictionary.
SigPah_ArgIn3               	Found in model but not in data dictionary.
SigPah_ArgIn4               	Found in model but not in data dictionary.
(variables: 1, errors: 5)

-----------------------------
OUTPUT SIGNALS:	<Identity>
-----------------------------
SigPah_ArgOut1              	Found in model but not in data dictionary.
SigPah_ArgOut4              	Found in model but not in data dictionary.
SigPah_ArgOut2              	Found in model but not in data dictionary.
SigPah_ArgOut3              	Found in model but not in data dictionary.
(variables: 0, errors: 4)

---------------------------------------
INTER-RUNNABLE VARIABLES:	<Identity>
---------------------------------------
FltInjPahGain               	Name does not match required pattern.
FltInjPahOffs               	Name does not match required pattern.
(variables: 2, errors: 2)

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
FltInjFltEna                	Name does not match required pattern.
FltInjRefTmr                	Name does not match required pattern.
FltInjUsrPrm                	Name does not match required pattern.
(variables: 3, errors: 3)

--------------------------------------------------------------------------------------------
CONSTANTS:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
FLTINJ_ASSI_ASSICMDBAS           	Name does not match required pattern as it is a special case.
FLTINJ_CURRMEASCORRLN_CURRMEASIDPTSIG	Name does not match required pattern as it is a special case.
FLTINJ_CURRMEAS_MOTCURRCORRDA    	Name does not match required pattern as it is a special case.
FLTINJ_CURRMEAS_MOTCURRCORRDD    	Name does not match required pattern as it is a special case.
FLTINJ_CURRMEAS_TESTOK           	Name does not match required pattern as it is a special case.
FLTINJ_DAMPG_DAMPGCMDBAS         	Name does not match required pattern as it is a special case.
FLTINJ_DIAGCMGR_DIAGCSTSIVTR1INACTV	Name does not match required pattern as it is a special case.
FLTINJ_DIAGCMGR_DIAGCSTSIVTR2INACTV	Name does not match required pattern as it is a special case.
FLTINJ_EOTDAMPGFWL_EOTDAMPGCMD   	Name does not match required pattern as it is a special case.
FLTINJ_HWAG0MEAS_HWAG0           	Name does not match required pattern as it is a special case.
FLTINJ_HWAG0MEAS_TESTOK          	Name does not match required pattern as it is a special case.
FLTINJ_HWAGCORRLN_HWAGIDPTSIG    	Name does not match required pattern as it is a special case.
FLTINJ_HWAGSYSARBN_HWAG          	Name does not match required pattern as it is a special case.
FLTINJ_HWAGSYSARBN_SERLCOMHWAG   	Name does not match required pattern as it is a special case.
FLTINJ_HWTQ0MEAS_HWTQ0           	Name does not match required pattern as it is a special case.
FLTINJ_HWTQ0MEAS_TESTOK0         	Name does not match required pattern as it is a special case.
FLTINJ_HWTQ2MEAS_HWTQ2           	Name does not match required pattern as it is a special case.
FLTINJ_HWTQCORRLN_HWTQIDPTSIG    	Name does not match required pattern as it is a special case.
FLTINJ_HYSCMP_HYSCMPCMD          	Name does not match required pattern as it is a special case.
FLTINJ_INERTIACMPTQ_ASSIHIFRQCMD 	Name does not match required pattern as it is a special case.
FLTINJ_INERTIACMPVEL_INERTIACMPCMD	Name does not match required pattern as it is a special case.
FLTINJ_LIMRCDNG_EOTGAIN          	Name does not match required pattern as it is a special case.
FLTINJ_LIMRCDNG_EOTLIM           	Name does not match required pattern as it is a special case.
FLTINJ_LIMRCDNG_SYSMOTTQCMDSCA   	Name does not match required pattern as it is a special case.
FLTINJ_MOTAG0MEAS_MOTCTRLMOTAG0MECL	Name does not match required pattern as it is a special case.
FLTINJ_MOTAG0MEAS_TESTOK         	Name does not match required pattern as it is a special case.
FLTINJ_MOTAG2MEAS_MOTAG2MECL     	Name does not match required pattern as it is a special case.
FLTINJ_MOTAGCORRLN_MOTAGIDPTSIG  	Name does not match required pattern as it is a special case.
FLTINJ_MOTTQEOLSCAG_MOTTQCMDMRFSCAD	Name does not match required pattern as it is a special case.
FLTINJ_RTN_RTNCMD                	Name does not match required pattern as it is a special case.
FLTINJ_STABYCMP_ASSICMD          	Name does not match required pattern as it is a special case.
FLTINJ_SYSFRICLRNG_SYSFRICOFFS   	Name does not match required pattern as it is a special case.
FLTINJ_TQOSCN_PREFINALCMD        	Name does not match required pattern as it is a special case.
FLTINJ_VEHSIGCDNG_SERLCOMVEHLATA 	Name does not match required pattern as it is a special case.
FLTINJ_VEHSIGCDNG_SERLCOMVEHLGTA 	Name does not match required pattern as it is a special case.
FLTINJ_VEHSIGCDNG_SERLCOMVEHSPD  	Name does not match required pattern as it is a special case.
FLTINJ_VEHSIGCDNG_SERLCOMVEHSPDVLD	Name does not match required pattern as it is a special case.
FLTINJ_VEHSIGCDNG_SERLCOMVEHYAWRATE	Name does not match required pattern as it is a special case.
FLTINJ_VEHSIGCDNG_VEHLATA        	Name does not match required pattern as it is a special case.
FLTINJ_VEHSIGCDNG_VEHLGTA        	Name does not match required pattern as it is a special case.
FLTINJ_VEHSIGCDNG_VEHSPD         	Name does not match required pattern as it is a special case.
FLTINJ_VEHSIGCDNG_VEHYAWRATE     	Name does not match required pattern as it is a special case.
STD_ON                           	Name does not match required pattern.
FLTINJ_ASSI_ASSICMDBAS      	Found in data dictionary but not in model.
FLTINJ_CURRMEAS_MOTCURRCORRDA	Found in data dictionary but not in model.
FLTINJ_CURRMEAS_MOTCURRCORRDD	Found in data dictionary but not in model.
FLTINJ_CURRMEAS_TESTOK      	Found in data dictionary but not in model

[… truncated after 8000 characters …]
```
