---
title: "Tauj1 Configuration And Use — Tauj1 Registers"
description: "Converted Text Note / Report from Tauj1 Registers.txt (TXT, 75 KB)."
---

:::note
Converted from `CM460A_Tauj1CfgAndUse_Design/Doc/Tauj1 Registers.txt` (Text Note / Report; original TXT, about 75 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM460A_Tauj1CfgAndUse_Design](./)

*Conversion method: ver batim transcription.*

```text
RegOutpTAUJ1CDR0 = DataDict.OpSignal;
RegOutpTAUJ1CDR0.LongName = 'Register TAUJ0CDR0';
RegOutpTAUJ1CDR0.Description = 'Register TAUJ0CDR0';
RegOutpTAUJ1CDR0.DocUnits = 'Cnt';
RegOutpTAUJ1CDR0.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CDR0.EngDT = dt.u32;
RegOutpTAUJ1CDR0.EngInit = 0;
RegOutpTAUJ1CDR0.EngMin = 0;
RegOutpTAUJ1CDR0.EngMax = 4294967295;
RegOutpTAUJ1CDR0.TestTolerance = 0;
RegOutpTAUJ1CDR0.WrittenIn = {};
RegOutpTAUJ1CDR0.WriteType = 'Phy';

RegOutpTAUJ1CDR1 = DataDict.OpSignal;
RegOutpTAUJ1CDR1.LongName = 'Register TAUJ0CDR1';
RegOutpTAUJ1CDR1.Description = 'Register TAUJ0CDR1';
RegOutpTAUJ1CDR1.DocUnits = 'Cnt';
RegOutpTAUJ1CDR1.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CDR1.EngDT = dt.u32;
RegOutpTAUJ1CDR1.EngInit = 0;
RegOutpTAUJ1CDR1.EngMin = 0;
RegOutpTAUJ1CDR1.EngMax = 4294967295;
RegOutpTAUJ1CDR1.TestTolerance = 0;
RegOutpTAUJ1CDR1.WrittenIn = {};
RegOutpTAUJ1CDR1.WriteType = 'Phy';

RegOutpTAUJ1CDR2 = DataDict.OpSignal;
RegOutpTAUJ1CDR2.LongName = 'Register TAUJ0CDR2';
RegOutpTAUJ1CDR2.Description = 'Register TAUJ0CDR2';
RegOutpTAUJ1CDR2.DocUnits = 'Cnt';
RegOutpTAUJ1CDR2.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CDR2.EngDT = dt.u32;
RegOutpTAUJ1CDR2.EngInit = 0;
RegOutpTAUJ1CDR2.EngMin = 0;
RegOutpTAUJ1CDR2.EngMax = 4294967295;
RegOutpTAUJ1CDR2.TestTolerance = 0;
RegOutpTAUJ1CDR2.WrittenIn = {};
RegOutpTAUJ1CDR2.WriteType = 'Phy';

RegOutpTAUJ1CDR3 = DataDict.OpSignal;
RegOutpTAUJ1CDR3.LongName = 'Register TAUJ0CDR3';
RegOutpTAUJ1CDR3.Description = 'Register TAUJ0CDR3';
RegOutpTAUJ1CDR3.DocUnits = 'Cnt';
RegOutpTAUJ1CDR3.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CDR3.EngDT = dt.u32;
RegOutpTAUJ1CDR3.EngInit = 0;
RegOutpTAUJ1CDR3.EngMin = 0;
RegOutpTAUJ1CDR3.EngMax = 4294967295;
RegOutpTAUJ1CDR3.TestTolerance = 0;
RegOutpTAUJ1CDR3.WrittenIn = {};
RegOutpTAUJ1CDR3.WriteType = 'Phy';

RegOutpTAUJ1CNT0 = DataDict.OpSignal;
RegOutpTAUJ1CNT0.LongName = 'Register TAUJ0CNT0';
RegOutpTAUJ1CNT0.Description = 'Register TAUJ0CNT0';
RegOutpTAUJ1CNT0.DocUnits = 'Cnt';
RegOutpTAUJ1CNT0.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CNT0.EngDT = dt.u32;
RegOutpTAUJ1CNT0.EngInit = 0;
RegOutpTAUJ1CNT0.EngMin = 0;
RegOutpTAUJ1CNT0.EngMax = 4294967295;
RegOutpTAUJ1CNT0.TestTolerance = 0;
RegOutpTAUJ1CNT0.WrittenIn = {};
RegOutpTAUJ1CNT0.WriteType = 'Phy';

RegOutpTAUJ1CNT1 = DataDict.OpSignal;
RegOutpTAUJ1CNT1.LongName = 'Register TAUJ0CNT1';
RegOutpTAUJ1CNT1.Description = 'Register TAUJ0CNT1';
RegOutpTAUJ1CNT1.DocUnits = 'Cnt';
RegOutpTAUJ1CNT1.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CNT1.EngDT = dt.u32;
RegOutpTAUJ1CNT1.EngInit = 0;
RegOutpTAUJ1CNT1.EngMin = 0;
RegOutpTAUJ1CNT1.EngMax = 4294967295;
RegOutpTAUJ1CNT1.TestTolerance = 0;
RegOutpTAUJ1CNT1.WrittenIn = {};
RegOutpTAUJ1CNT1.WriteType = 'Phy';

RegOutpTAUJ1CNT2 = DataDict.OpSignal;
RegOutpTAUJ1CNT2.LongName = 'Register TAUJ0CNT2';
RegOutpTAUJ1CNT2.Description = 'Register TAUJ0CNT2';
RegOutpTAUJ1CNT2.DocUnits = 'Cnt';
RegOutpTAUJ1CNT2.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CNT2.EngDT = dt.u32;
RegOutpTAUJ1CNT2.EngInit = 0;
RegOutpTAUJ1CNT2.EngMin = 0;
RegOutpTAUJ1CNT2.EngMax = 4294967295;
RegOutpTAUJ1CNT2.TestTolerance = 0;
RegOutpTAUJ1CNT2.WrittenIn = {};
RegOutpTAUJ1CNT2.WriteType = 'Phy';

RegOutpTAUJ1CNT3 = DataDict.OpSignal;
RegOutpTAUJ1CNT3.LongName = 'Register TAUJ0CNT3';
RegOutpTAUJ1CNT3.Description = 'Register TAUJ0CNT3';
RegOutpTAUJ1CNT3.DocUnits = 'Cnt';
RegOutpTAUJ1CNT3.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CNT3.EngDT = dt.u32;
RegOutpTAUJ1CNT3.EngInit = 0;
RegOutpTAUJ1CNT3.EngMin = 0;
RegOutpTAUJ1CNT3.EngMax = 4294967295;
RegOutpTAUJ1CNT3.TestTolerance = 0;
RegOutpTAUJ1CNT3.WrittenIn = {};
RegOutpTAUJ1CNT3.WriteType = 'Phy';

RegOutpTAUJ1CMUR0 = DataDict.OpSignal;
RegOutpTAUJ1CMUR0.LongName = 'Register TAUJ0CMUR0';
RegOutpTAUJ1CMUR0.Description = 'Register TAUJ0CMUR0';
RegOutpTAUJ1CMUR0.DocUnits = 'Cnt';
RegOutpTAUJ1CMUR0.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CMUR0.EngDT = dt.u08;
RegOutpTAUJ1CMUR0.EngInit = 0;
RegOutpTAUJ1CMUR0.EngMin = 0;
RegOutpTAUJ1CMUR0.EngMax = 255;
RegOutpTAUJ1CMUR0.TestTolerance = 0;
RegOutpTAUJ1CMUR0.WrittenIn = {};
RegOutpTAUJ1CMUR0.WriteType = 'Phy';

RegOutpTAUJ1TIS = DataDict.OpSignal;
RegOutpTAUJ1TIS.LongName = 'Register TAUJ0TIS';
RegOutpTAUJ1TIS.Description = 'Register TAUJ0TIS';
RegOutpTAUJ1TIS.DocUnits = 'Cnt';
RegOutpTAUJ1TIS.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1TIS.EngDT = dt.u08;
RegOutpTAUJ1TIS.EngInit = 0;
RegOutpTAUJ1TIS.EngMin = 0;
RegOutpTAUJ1TIS.EngMax = 1;
RegOutpTAUJ1TIS.TestTolerance = 0;
RegOutpTAUJ1TIS.WrittenIn = {};
RegOutpTAUJ1TIS.WriteType = 'Phy';

RegOutpTAUJ1CMUR1 = DataDict.OpSignal;
RegOutpTAUJ1CMUR1.LongName = 'Register TAUJ0CMUR1';
RegOutpTAUJ1CMUR1.Description = 'Register TAUJ0CMUR1';
RegOutpTAUJ1CMUR1.DocUnits = 'Cnt';
RegOutpTAUJ1CMUR1.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CMUR1.EngDT = dt.u08;
RegOutpTAUJ1CMUR1.EngInit = 0;
RegOutpTAUJ1CMUR1.EngMin = 0;
RegOutpTAUJ1CMUR1.EngMax = 255;
RegOutpTAUJ1CMUR1.TestTolerance = 0;
RegOutpTAUJ1CMUR1.WrittenIn = {};
RegOutpTAUJ1CMUR1.WriteType = 'Phy';

RegOutpTAUJ1CMUR2 = DataDict.OpSignal;
RegOutpTAUJ1CMUR2.LongName = 'Register TAUJ0CMUR2';
RegOutpTAUJ1CMUR2.Description = 'Register TAUJ0CMUR2';
RegOutpTAUJ1CMUR2.DocUnits = 'Cnt';
RegOutpTAUJ1CMUR2.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CMUR2.EngDT = dt.u08;
RegOutpTAUJ1CMUR2.EngInit = 0;
RegOutpTAUJ1CMUR2.EngMin = 0;
RegOutpTAUJ1CMUR2.EngMax = 255;
RegOutpTAUJ1CMUR2.TestTolerance = 0;
RegOutpTAUJ1CMUR2.WrittenIn = {};
RegOutpTAUJ1CMUR2.WriteType = 'Phy';

RegOutpTAUJ1CMUR3 = DataDict.OpSignal;
RegOutpTAUJ1CMUR3.LongName = 'Register TAUJ0CMUR3';
RegOutpTAUJ1CMUR3.Description = 'Register TAUJ0CMUR3';
RegOutpTAUJ1CMUR3.DocUnits = 'Cnt';
RegOutpTAUJ1CMUR3.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CMUR3.EngDT = dt.u08;
RegOutpTAUJ1CMUR3.EngInit = 0;
RegOutpTAUJ1CMUR3.EngMin = 0;
RegOutpTAUJ1CMUR3.EngMax = 255;
RegOutpTAUJ1CMUR3.TestTolerance = 0;
RegOutpTAUJ1CMUR3.WrittenIn = {};
RegOutpTAUJ1CMUR3.WriteType = 'Phy';

RegOutpTAUJ1CSR0 = DataDict.OpSignal;
RegOutpTAUJ1CSR0.LongName = 'Register TAUJ0CSR0';
RegOutpTAUJ1CSR0.Description = 'Register TAUJ0CSR0';
RegOutpTAUJ1CSR0.DocUnits = 'Cnt';
RegOutpTAUJ1CSR0.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CSR0.EngDT = dt.u08;
RegOutpTAUJ1CSR0.EngInit = 0;
RegOutpTAUJ1CSR0.EngMin = 0;
RegOutpTAUJ1CSR0.EngMax = 255;
RegOutpTAUJ1CSR0.TestTolerance = 0;
RegOutpTAUJ1CSR0.WrittenIn = {};
RegOutpTAUJ1CSR0.WriteType = 'Phy';

RegOutpTAUJ1OVF = DataDict.OpSignal;
RegOutpTAUJ1OVF.LongName = 'Register TAUJ0OVF';
RegOutpTAUJ1OVF.Description = 'Register TAUJ0OVF';
RegOutpTAUJ1OVF.DocUnits = 'Cnt';
RegOutpTAUJ1OVF.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1OVF.EngDT = dt.u08;
RegOutpTAUJ1OVF.EngInit = 0;
RegOutpTAUJ1OVF.EngMin = 0;
RegOutpTAUJ1OVF.EngMax = 1;
RegOutpTAUJ1OVF.TestTolerance = 0;
RegOutpTAUJ1OVF.WrittenIn = {};
RegOutpTAUJ1OVF.WriteType = 'Phy';

RegOutpTAUJ1CSR1 = DataDict.OpSignal;
RegOutpTAUJ1CSR1.LongName = 'Register TAUJ0CSR1';
RegOutpTAUJ1CSR1.Description = 'Register TAUJ0CSR1';
RegOutpTAUJ1CSR1.DocUnits = 'Cnt';
RegOutpTAUJ1CSR1.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CSR1.EngDT = dt.u08;
RegOutpTAUJ1CSR1.EngInit = 0;
RegOutpTAUJ1CSR1.EngMin = 0;
RegOutpTAUJ1CSR1.EngMax = 255;
RegOutpTAUJ1CSR1.TestTolerance = 0;
RegOutpTAUJ1CSR1.WrittenIn = {};
RegOutpTAUJ1CSR1.WriteType = 'Phy';

RegOutpTAUJ1CSR2 = DataDict.OpSignal;
RegOutpTAUJ1CSR2.LongName = 'Register TAUJ0CSR2';
RegOutpTAUJ1CSR2.Description = 'Register TAUJ0CSR2';
RegOutpTAUJ1CSR2.DocUnits = 'Cnt';
RegOutpTAUJ1CSR2.SwcShoName = 'Tauj0CfgAndUse';
RegOutpTAUJ1CSR2.EngDT = dt.u08;
RegOutpTAUJ1CSR2.EngInit = 0;
RegOutpTAUJ1CSR2.EngMin = 0;
RegOutpTAUJ1CSR2.EngMax = 255;
RegOutpTAUJ1CSR2.TestTolerance = 0;
RegOutpTAUJ1CSR2.WrittenIn = {};
RegOutpTAUJ1CSR2.WriteType = 'Phy';

RegOutpTAUJ1CSR3 = DataDict.OpSignal;
RegOutpTAUJ1CSR3.LongName = 'Register TAUJ0CSR3';
RegOutpTAUJ1CSR3.Description = 'Register TAUJ0CSR3';
RegOutpTAUJ1CSR3.DocUnits = 'Cnt';
RegOutpTAUJ1CSR3.SwcShoName = 'Tauj0CfgAndU

[… truncated after 8000 characters …]
```
