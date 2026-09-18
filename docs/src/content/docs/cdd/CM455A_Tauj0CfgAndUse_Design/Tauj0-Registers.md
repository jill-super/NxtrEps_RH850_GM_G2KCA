---
title: "Tauj0 Configuration And Use — Tauj0 Registers"
description: "Converted Text Note / Report from Tauj0 Registers.txt (TXT, 75 KB)."
---

:::note
Converted from `CM455A_Tauj0CfgAndUse_Design/Doc/Tauj0 Registers.txt` (Text Note / Report; original TXT, about 75 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM455A_Tauj0CfgAndUse_Design](./)

*Conversion method: ver batim transcription.*

```text
RegOutpTAUJ0CDR0 = DataDict.OpSignal;
RegOutpTAUJ0CDR0.LongName = 'Register TAUJ0CDR0';
RegOutpTAUJ0CDR0.Description = 'Register TAUJ0CDR0';
RegOutpTAUJ0CDR0.DocUnits = 'Cnt';
RegOutpTAUJ0CDR0.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CDR0.EngDT = dt.u32;
RegOutpTAUJ0CDR0.EngInit = 0;
RegOutpTAUJ0CDR0.EngMin = 0;
RegOutpTAUJ0CDR0.EngMax = 4294967295;
RegOutpTAUJ0CDR0.TestTolerance = 0;
RegOutpTAUJ0CDR0.WrittenIn = {};
RegOutpTAUJ0CDR0.WriteType = 'Phy';

RegOutpTAUJ0CDR1 = DataDict.OpSignal;
RegOutpTAUJ0CDR1.LongName = 'Register TAUJ0CDR1';
RegOutpTAUJ0CDR1.Description = 'Register TAUJ0CDR1';
RegOutpTAUJ0CDR1.DocUnits = 'Cnt';
RegOutpTAUJ0CDR1.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CDR1.EngDT = dt.u32;
RegOutpTAUJ0CDR1.EngInit = 0;
RegOutpTAUJ0CDR1.EngMin = 0;
RegOutpTAUJ0CDR1.EngMax = 4294967295;
RegOutpTAUJ0CDR1.TestTolerance = 0;
RegOutpTAUJ0CDR1.WrittenIn = {};
RegOutpTAUJ0CDR1.WriteType = 'Phy';

RegOutpTAUJ0CDR2 = DataDict.OpSignal;
RegOutpTAUJ0CDR2.LongName = 'Register TAUJ0CDR2';
RegOutpTAUJ0CDR2.Description = 'Register TAUJ0CDR2';
RegOutpTAUJ0CDR2.DocUnits = 'Cnt';
RegOutpTAUJ0CDR2.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CDR2.EngDT = dt.u32;
RegOutpTAUJ0CDR2.EngInit = 0;
RegOutpTAUJ0CDR2.EngMin = 0;
RegOutpTAUJ0CDR2.EngMax = 4294967295;
RegOutpTAUJ0CDR2.TestTolerance = 0;
RegOutpTAUJ0CDR2.WrittenIn = {};
RegOutpTAUJ0CDR2.WriteType = 'Phy';

RegOutpTAUJ0CDR3 = DataDict.OpSignal;
RegOutpTAUJ0CDR3.LongName = 'Register TAUJ0CDR3';
RegOutpTAUJ0CDR3.Description = 'Register TAUJ0CDR3';
RegOutpTAUJ0CDR3.DocUnits = 'Cnt';
RegOutpTAUJ0CDR3.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CDR3.EngDT = dt.u32;
RegOutpTAUJ0CDR3.EngInit = 0;
RegOutpTAUJ0CDR3.EngMin = 0;
RegOutpTAUJ0CDR3.EngMax = 4294967295;
RegOutpTAUJ0CDR3.TestTolerance = 0;
RegOutpTAUJ0CDR3.WrittenIn = {};
RegOutpTAUJ0CDR3.WriteType = 'Phy';

RegOutpTAUJ0CNT0 = DataDict.OpSignal;
RegOutpTAUJ0CNT0.LongName = 'Register TAUJ0CNT0';
RegOutpTAUJ0CNT0.Description = 'Register TAUJ0CNT0';
RegOutpTAUJ0CNT0.DocUnits = 'Cnt';
RegOutpTAUJ0CNT0.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CNT0.EngDT = dt.u32;
RegOutpTAUJ0CNT0.EngInit = 0;
RegOutpTAUJ0CNT0.EngMin = 0;
RegOutpTAUJ0CNT0.EngMax = 4294967295;
RegOutpTAUJ0CNT0.TestTolerance = 0;
RegOutpTAUJ0CNT0.WrittenIn = {};
RegOutpTAUJ0CNT0.WriteType = 'Phy';

RegOutpTAUJ0CNT1 = DataDict.OpSignal;
RegOutpTAUJ0CNT1.LongName = 'Register TAUJ0CNT1';
RegOutpTAUJ0CNT1.Description = 'Register TAUJ0CNT1';
RegOutpTAUJ0CNT1.DocUnits = 'Cnt';
RegOutpTAUJ0CNT1.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CNT1.EngDT = dt.u32;
RegOutpTAUJ0CNT1.EngInit = 0;
RegOutpTAUJ0CNT1.EngMin = 0;
RegOutpTAUJ0CNT1.EngMax = 4294967295;
RegOutpTAUJ0CNT1.TestTolerance = 0;
RegOutpTAUJ0CNT1.WrittenIn = {};
RegOutpTAUJ0CNT1.WriteType = 'Phy';

RegOutpTAUJ0CNT2 = DataDict.OpSignal;
RegOutpTAUJ0CNT2.LongName = 'Register TAUJ0CNT2';
RegOutpTAUJ0CNT2.Description = 'Register TAUJ0CNT2';
RegOutpTAUJ0CNT2.DocUnits = 'Cnt';
RegOutpTAUJ0CNT2.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CNT2.EngDT = dt.u32;
RegOutpTAUJ0CNT2.EngInit = 0;
RegOutpTAUJ0CNT2.EngMin = 0;
RegOutpTAUJ0CNT2.EngMax = 4294967295;
RegOutpTAUJ0CNT2.TestTolerance = 0;
RegOutpTAUJ0CNT2.WrittenIn = {};
RegOutpTAUJ0CNT2.WriteType = 'Phy';

RegOutpTAUJ0CNT3 = DataDict.OpSignal;
RegOutpTAUJ0CNT3.LongName = 'Register TAUJ0CNT3';
RegOutpTAUJ0CNT3.Description = 'Register TAUJ0CNT3';
RegOutpTAUJ0CNT3.DocUnits = 'Cnt';
RegOutpTAUJ0CNT3.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CNT3.EngDT = dt.u32;
RegOutpTAUJ0CNT3.EngInit = 0;
RegOutpTAUJ0CNT3.EngMin = 0;
RegOutpTAUJ0CNT3.EngMax = 4294967295;
RegOutpTAUJ0CNT3.TestTolerance = 0;
RegOutpTAUJ0CNT3.WrittenIn = {};
RegOutpTAUJ0CNT3.WriteType = 'Phy';

RegOutpTAUJ0CMUR0 = DataDict.OpSignal;
RegOutpTAUJ0CMUR0.LongName = 'Register TAUJ0CMUR0';
RegOutpTAUJ0CMUR0.Description = 'Register TAUJ0CMUR0';
RegOutpTAUJ0CMUR0.DocUnits = 'Cnt';
RegOutpTAUJ0CMUR0.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CMUR0.EngDT = dt.u08;
RegOutpTAUJ0CMUR0.EngInit = 0;
RegOutpTAUJ0CMUR0.EngMin = 0;
RegOutpTAUJ0CMUR0.EngMax = 255;
RegOutpTAUJ0CMUR0.TestTolerance = 0;
RegOutpTAUJ0CMUR0.WrittenIn = {};
RegOutpTAUJ0CMUR0.WriteType = 'Phy';

RegOutpTAUJ0TIS = DataDict.OpSignal;
RegOutpTAUJ0TIS.LongName = 'Register TAUJ0TIS';
RegOutpTAUJ0TIS.Description = 'Register TAUJ0TIS';
RegOutpTAUJ0TIS.DocUnits = 'Cnt';
RegOutpTAUJ0TIS.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0TIS.EngDT = dt.u08;
RegOutpTAUJ0TIS.EngInit = 0;
RegOutpTAUJ0TIS.EngMin = 0;
RegOutpTAUJ0TIS.EngMax = 1;
RegOutpTAUJ0TIS.TestTolerance = 0;
RegOutpTAUJ0TIS.WrittenIn = {};
RegOutpTAUJ0TIS.WriteType = 'Phy';

RegOutpTAUJ0CMUR1 = DataDict.OpSignal;
RegOutpTAUJ0CMUR1.LongName = 'Register TAUJ0CMUR1';
RegOutpTAUJ0CMUR1.Description = 'Register TAUJ0CMUR1';
RegOutpTAUJ0CMUR1.DocUnits = 'Cnt';
RegOutpTAUJ0CMUR1.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CMUR1.EngDT = dt.u08;
RegOutpTAUJ0CMUR1.EngInit = 0;
RegOutpTAUJ0CMUR1.EngMin = 0;
RegOutpTAUJ0CMUR1.EngMax = 255;
RegOutpTAUJ0CMUR1.TestTolerance = 0;
RegOutpTAUJ0CMUR1.WrittenIn = {};
RegOutpTAUJ0CMUR1.WriteType = 'Phy';

RegOutpTAUJ0CMUR2 = DataDict.OpSignal;
RegOutpTAUJ0CMUR2.LongName = 'Register TAUJ0CMUR2';
RegOutpTAUJ0CMUR2.Description = 'Register TAUJ0CMUR2';
RegOutpTAUJ0CMUR2.DocUnits = 'Cnt';
RegOutpTAUJ0CMUR2.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CMUR2.EngDT = dt.u08;
RegOutpTAUJ0CMUR2.EngInit = 0;
RegOutpTAUJ0CMUR2.EngMin = 0;
RegOutpTAUJ0CMUR2.EngMax = 255;
RegOutpTAUJ0CMUR2.TestTolerance = 0;
RegOutpTAUJ0CMUR2.WrittenIn = {};
RegOutpTAUJ0CMUR2.WriteType = 'Phy';

RegOutpTAUJ0CMUR3 = DataDict.OpSignal;
RegOutpTAUJ0CMUR3.LongName = 'Register TAUJ0CMUR3';
RegOutpTAUJ0CMUR3.Description = 'Register TAUJ0CMUR3';
RegOutpTAUJ0CMUR3.DocUnits = 'Cnt';
RegOutpTAUJ0CMUR3.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CMUR3.EngDT = dt.u08;
RegOutpTAUJ0CMUR3.EngInit = 0;
RegOutpTAUJ0CMUR3.EngMin = 0;
RegOutpTAUJ0CMUR3.EngMax = 255;
RegOutpTAUJ0CMUR3.TestTolerance = 0;
RegOutpTAUJ0CMUR3.WrittenIn = {};
RegOutpTAUJ0CMUR3.WriteType = 'Phy';

RegOutpTAUJ0CSR0 = DataDict.OpSignal;
RegOutpTAUJ0CSR0.LongName = 'Register TAUJ0CSR0';
RegOutpTAUJ0CSR0.Description = 'Register TAUJ0CSR0';
RegOutpTAUJ0CSR0.DocUnits = 'Cnt';
RegOutpTAUJ0CSR0.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CSR0.EngDT = dt.u08;
RegOutpTAUJ0CSR0.EngInit = 0;
RegOutpTAUJ0CSR0.EngMin = 0;
RegOutpTAUJ0CSR0.EngMax = 255;
RegOutpTAUJ0CSR0.TestTolerance = 0;
RegOutpTAUJ0CSR0.WrittenIn = {};
RegOutpTAUJ0CSR0.WriteType = 'Phy';

RegOutpTAUJ0OVF = DataDict.OpSignal;
RegOutpTAUJ0OVF.LongName = 'Register TAUJ0OVF';
RegOutpTAUJ0OVF.Description = 'Register TAUJ0OVF';
RegOutpTAUJ0OVF.DocUnits = 'Cnt';
RegOutpTAUJ0OVF.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0OVF.EngDT = dt.u08;
RegOutpTAUJ0OVF.EngInit = 0;
RegOutpTAUJ0OVF.EngMin = 0;
RegOutpTAUJ0OVF.EngMax = 1;
RegOutpTAUJ0OVF.TestTolerance = 0;
RegOutpTAUJ0OVF.WrittenIn = {};
RegOutpTAUJ0OVF.WriteType = 'Phy';

RegOutpTAUJ0CSR1 = DataDict.OpSignal;
RegOutpTAUJ0CSR1.LongName = 'Register TAUJ0CSR1';
RegOutpTAUJ0CSR1.Description = 'Register TAUJ0CSR1';
RegOutpTAUJ0CSR1.DocUnits = 'Cnt';
RegOutpTAUJ0CSR1.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CSR1.EngDT = dt.u08;
RegOutpTAUJ0CSR1.EngInit = 0;
RegOutpTAUJ0CSR1.EngMin = 0;
RegOutpTAUJ0CSR1.EngMax = 255;
RegOutpTAUJ0CSR1.TestTolerance = 0;
RegOutpTAUJ0CSR1.WrittenIn = {};
RegOutpTAUJ0CSR1.WriteType = 'Phy';

RegOutpTAUJ0CSR2 = DataDict.OpSignal;
RegOutpTAUJ0CSR2.LongName = 'Register TAUJ0CSR2';
RegOutpTAUJ0CSR2.Description = 'Register TAUJ0CSR2';
RegOutpTAUJ0CSR2.DocUnits = 'Cnt';
RegOutpTAUJ0CSR2.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ0CSR2.EngDT = dt.u08;
RegOutpTAUJ0CSR2.EngInit = 0;
RegOutpTAUJ0CSR2.EngMin = 0;
RegOutpTAUJ0CSR2.EngMax = 255;
RegOutpTAUJ0CSR2.TestTolerance = 0;
RegOutpTAUJ0CSR2.WrittenIn = {};
RegOutpTAUJ0CSR2.WriteType = 'Phy';

RegOutpTAUJ0CSR3 = DataDict.OpSignal;
RegOutpTAUJ0CSR3.LongName = 'Register TAUJ0CSR3';
RegOutpTAUJ0CSR3.Description = 'Register TAUJ0CSR3';
RegOutpTAUJ0CSR3.DocUnits = 'Cnt';
RegOutpTAUJ0CSR3.SwcShoName = 'Tauj0CfgAndU

[… truncated after 8000 characters …]
```
