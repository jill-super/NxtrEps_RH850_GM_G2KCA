---
title: "Non-Volatile M — ES006A NvM DDReport"
description: "Converted Design Document / Report from ES006A_NvM_DDReport.txt (TXT, 13 KB)."
---

:::note
Converted from `ES006A_NvM_Design/Reports/ES006A_NvM_DDReport.txt` (Design Document / Report; original TXT, about 13 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to ES006A_NvM_Design](./)

*Conversion method: ver batim transcription.*

```text
Verification of ES006A_NvM_DataDict
07-Oct-2016 09:55:24
Tool Release:  2.48.0



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
Missing Model 	Unable to find model for comparison to data dictionary.
(errors:  1)

------------------------------------------------------------
RUNNABLE:	<ShoName>Per<Number>  or  <ShoName>Init<Number>
------------------------------------------------------------
NvM_Init                    	.Runnnable:	Name must end with 'Init' or 'Per1', 'Per2', etc.
NvM_Init                    	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_MainFunction            	.Runnnable:	Name must end with 'Init' or 'Per1', 'Per2', etc.
NvM_MainFunction            	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_MainFunction            	    Main           Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_MainFunction            	    Function       Unknown Keyword used.Only Nexteer approved Keywords should be used.
(variables: 4, errors: 6)

--------------------------------------
SrvRunnable:	<TriggerName>
--------------------------------------
NvMPIM_EraseBlock           	.SrvRunnnable:	Name should not contain FDDs <ShoName>
NvMPIM_EraseBlock           	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_EraseBlock           	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_EraseBlock           	    Block          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_GetDataIndex         	.SrvRunnnable:	Name should not contain FDDs <ShoName>
NvMPIM_GetDataIndex         	.TestTolerance 	Value is at default value of 999.
NvMPIM_GetDataIndex         	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_GetDataIndex         	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_GetDataIndex         	    Index          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_GetErrorStatus       	.SrvRunnnable:	Name should not contain FDDs <ShoName>
NvMPIM_GetErrorStatus       	.TestTolerance 	Value is at default value of 999.
NvMPIM_GetErrorStatus       	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_GetErrorStatus       	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_GetErrorStatus       	    Error          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_GetErrorStatus       	    Status         Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_InvalidateBlock      	.SrvRunnnable:	Name should not contain FDDs <ShoName>
NvMPIM_InvalidateBlock      	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_InvalidateBlock      	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_InvalidateBlock      	    Invalidate     Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_InvalidateBlock      	    Block          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_ReadBlock            	.SrvRunnnable:	Name should not contain FDDs <ShoName>
NvMPIM_ReadBlock            	.TestTolerance 	Value is at default value of 999.
NvMPIM_ReadBlock            	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_ReadBlock            	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_ReadBlock            	    Block          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_RestoreBlockDefaults 	.SrvRunnnable:	Name should not contain FDDs <ShoName>
NvMPIM_RestoreBlockDefaults 	.TestTolerance 	Value is at default value of 999.
NvMPIM_RestoreBlockDefaults 	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_RestoreBlockDefaults 	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_RestoreBlockDefaults 	    Block          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_RestoreBlockDefaults 	    Defaults       Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetBlockProtection   	.SrvRunnnable:	Name should not contain FDDs <ShoName>
NvMPIM_SetBlockProtection   	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetBlockProtection   	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetBlockProtection   	    Block          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetBlockProtection   	    Protection     Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetDataIndex         	.SrvRunnnable:	Name should not contain FDDs <ShoName>
NvMPIM_SetDataIndex         	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetDataIndex         	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetDataIndex         	    Index          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetRamBlockStatus    	.SrvRunnnable:	Name should not contain FDDs <ShoName>
NvMPIM_SetRamBlockStatus    	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetRamBlockStatus    	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetRamBlockStatus    	    Block          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_SetRamBlockStatus    	    Status         Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_WriteBlock           	.SrvRunnnable:	Name should not contain FDDs <ShoName>
NvMPIM_WriteBlock           	    I              Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_WriteBlock           	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_WriteBlock           	    Write          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvMPIM_WriteBlock           	    Block          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_CancelJobs              	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_CancelJobs              	    Cancel         Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_CancelJobs              	    Jobs           Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_CancelWriteAll          	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_CancelWriteAll          	    Cancel         Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_CancelWriteAll          	    Write          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_EraseBlock              	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_EraseBlock              	    Block          Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_GetDataIndex            	.TestTolerance 	Value is at default value of 999.
NvM_GetDataIndex            	    M_             Unknown Keyword used.Only Nexteer approved Keywords should be used.
NvM_GetDataIndex        

[… truncated after 8000 characters …]
```
