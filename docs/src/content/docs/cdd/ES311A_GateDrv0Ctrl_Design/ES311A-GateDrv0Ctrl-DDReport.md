---
title: "Gate Driver 0 Control — ES311A GateDrv0Ctrl DDReport"
description: "Converted Design Document / Report from ES311A_GateDrv0Ctrl_DDReport.txt (TXT, 11 KB)."
---

:::note
Converted from `ES311A_GateDrv0Ctrl_Design/Reports/ES311A_GateDrv0Ctrl_DDReport.txt` (Design Document / Report; original TXT, about 11 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES311A_GateDrv0Ctrl_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of ES311A_GateDrv0Ctrl_DataDict
22-Sep-2016 10:46:46
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
Call_Spi_AsyncTransmit      	Name does not match required pattern.
Call_Spi_AsyncTransmit      	    Call_          Unknown Keyword used.Only Nexteer approved Keywords should be used.
Call_Spi_AsyncTransmit      	    Spi_           Unknown Keyword used.Only Nexteer approved Keywords should be used.
Call_Spi_AsyncTransmit      	    Transmit       Unknown Keyword used.Only Nexteer approved Keywords should be used.
IoHwAb_GetGpioMotDrvr0Diag  	    Ab_            Unknown Keyword used.Only Nexteer approved Keywords should be used.
IoHwAb_SetGpioGateDrv0Rst   	    Ab_            Unknown Keyword used.Only Nexteer approved Keywords should be used.
IoHwAb_SetGpioSysFlt2A      	    Ab_            Unknown Keyword used.Only Nexteer approved Keywords should be used.
Spi_ReadIB                  	    Spi_           Unknown Keyword used.Only Nexteer approved Keywords should be used.
Spi_ReadIB                  	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
Spi_WriteIB                 	    Spi_           Unknown Keyword used.Only Nexteer approved Keywords should be used.
Spi_WriteIB                 	    Write          Unknown Keyword used.Only Nexteer approved Keywords should be used.
Spi_WriteIB                 	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
(variables: 7, errors: 12)

----------------------------
INPUT SIGNALS:	<Identity>
----------------------------
PhaALowrCmd                 	Cannot match name to list of known Nexteer signals.
PhaAUpprCmd                 	Cannot match name to list of known Nexteer signals.
PhaBLowrCmd                 	Cannot match name to list of known Nexteer signals.
PhaBUpprCmd                 	Cannot match name to list of known Nexteer signals.
PhaCLowrCmd                 	Cannot match name to list of known Nexteer signals.
PhaCUpprCmd                 	Cannot match name to list of known Nexteer signals.
(variables: 9, errors: 6)

-----------------------------
OUTPUT SIGNALS:	<Identity>
-----------------------------
GateDrv0RstPhy              	Cannot match name to list of known Nexteer signals.
MotDrvr0IninTestCmpl        	Cannot match name to list of known Nexteer signals.
PhaAFb                      	Cannot match name to list of known Nexteer signals.
PhaALowrGatePhy             	Cannot match name to list of known Nexteer signals.
PhaAUpprGatePhy             	Cannot match name to list of known Nexteer signals.
PhaBFb                      	Cannot match name to list of known Nexteer signals.
PhaBLowrGatePhy             	Cannot match name to list of known Nexteer signals.
PhaBUpprGatePhy             	Cannot match name to list of known Nexteer signals.
PhaCFb                      	Cannot match name to list of known Nexteer signals.
PhaCLowrGatePhy             	Cannot match name to list of known Nexteer signals.
PhaCUpprGatePhy             	Cannot match name to list of known Nexteer signals.
(variables: 11, errors: 11)

---------------------------------------
INTER-RUNNABLE VARIABLES:	<Identity>
---------------------------------------
(variables: 2, errors: 0)

------------------------------------
CALIBRATIONS:	<ShoName><Identity>
------------------------------------
(variables: 10, errors: 0)

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
(variables: 7, errors: 0)

-----------------------------------------------
PER-INSTANCE MEMORY:	<Identity>
-----------------------------------------------
(variables: 15, errors: 0)

--------------------------------------------------------------------------------------------
CONSTANTS:	(ALL CAPS) required: 
						 For "Global" CONSTANTS --- <SHONAME>_<IDENTITY>_<UNITS>_<DATATYPE>
						 For "Local" CONSTANTS  --- <IDENTITY>_<UNITS>_<DATATYPE>
-------------------------------------------------------------------------------------------
SpiConf_SpiChannel_GateDrv0Cfg0Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Cfg0Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Cfg1Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Cfg1Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Cfg2Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Cfg2Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Cfg3Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Cfg3Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Cfg4Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Cfg4Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Cfg5Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Cfg5Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Cfg6Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Cfg6Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Cfg7Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Cfg7Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0CtrlCh	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0CtrlCh	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Diag0Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Diag0Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Diag1Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Diag1Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Diag2Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Diag2Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Mask0Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Mask0Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Mask1Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Mask1Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0Mask2Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0Mask2Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0VrfyCmd0Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0VrfyCmd0Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0VrfyCmd1Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0VrfyCmd1Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0VrfyRes0Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv0VrfyRes0Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv0VrfyRes1Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_Spi

[… truncated after 8000 characters …]
```
