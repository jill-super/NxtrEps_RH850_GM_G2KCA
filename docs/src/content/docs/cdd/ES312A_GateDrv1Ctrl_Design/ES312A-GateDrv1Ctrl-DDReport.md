---
title: "Gate Driver 1 Control — ES312A GateDrv1Ctrl DDReport"
description: "Converted Design Document / Report from ES312A_GateDrv1Ctrl_DDReport.txt (TXT, 11 KB)."
---

:::note
Converted from `ES312A_GateDrv1Ctrl_Design/Reports/ES312A_GateDrv1Ctrl_DDReport.txt` (Design Document / Report; original TXT, about 11 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES312A_GateDrv1Ctrl_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of ES312A_GateDrv1Ctrl_DataDict
22-Sep-2016 11:29:16
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
IoHwAb_GetGpioMotDrvr1Diag  	    Ab_            Unknown Keyword used.Only Nexteer approved Keywords should be used.
IoHwAb_SetGpioGateDrv1Rst   	    Ab_            Unknown Keyword used.Only Nexteer approved Keywords should be used.
IoHwAb_SetGpioSysFlt2B      	    Ab_            Unknown Keyword used.Only Nexteer approved Keywords should be used.
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
GateDrv1RstPhy              	Cannot match name to list of known Nexteer signals.
MotDrvr1IninTestCmpl        	Cannot match name to list of known Nexteer signals.
PhaDFb                      	Cannot match name to list of known Nexteer signals.
PhaDLowrGatePhy             	Cannot match name to list of known Nexteer signals.
PhaDUpprGatePhy             	Cannot match name to list of known Nexteer signals.
PhaEFb                      	Cannot match name to list of known Nexteer signals.
PhaELowrGatePhy             	Cannot match name to list of known Nexteer signals.
PhaEUpprGatePhy             	Cannot match name to list of known Nexteer signals.
PhaFFb                      	Cannot match name to list of known Nexteer signals.
PhaFLowrGatePhy             	Cannot match name to list of known Nexteer signals.
PhaFUpprGatePhy             	Cannot match name to list of known Nexteer signals.
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
SpiConf_SpiChannel_GateDrv1Cfg0Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Cfg0Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Cfg1Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Cfg1Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Cfg2Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Cfg2Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Cfg3Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Cfg3Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Cfg4Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Cfg4Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Cfg5Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Cfg5Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Cfg6Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Cfg6Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Cfg7Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Cfg7Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1CtrlCh	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1CtrlCh	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Diag0Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Diag0Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Diag1Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Diag1Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Diag2Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Diag2Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Mask0Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Mask0Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Mask1Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Mask1Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1Mask2Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1Mask2Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1VrfyCmd0Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1VrfyCmd0Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1VrfyCmd1Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1VrfyCmd1Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1VrfyRes0Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_SpiChannel_GateDrv1VrfyRes0Ch	Name does not match required pattern.
SpiConf_SpiChannel_GateDrv1VrfyRes1Ch	AUTOSAR requires that constants be ALL CAPS.
SpiConf_Spi

[… truncated after 8000 characters …]
```
