---
title: "TSG 31 Configuration And Use — TSG31 Register IO Definitions"
description: "Converted Text Note / Report from TSG31 Register IO Definitions.txt (TXT, 324 KB)."
---

:::note
Converted from `CM475A_TSG31CfgAndUse_Design/Doc/TSG31 Register IO Definitions.txt` (Text Note / Report; original TXT, about 324 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CM475A_TSG31CfgAndUse_Design](./)

*Conversion method: ver batim transcription.*

```text
RegOutpTSG30IOC2 = DataDict.OpSignal;
RegOutpTSG30IOC2.LongName = 'Register TSG30IOC2';
RegOutpTSG30IOC2.Description = 'Register TSG30IOC2';
RegOutpTSG30IOC2.DocUnits = 'Cnt';
RegOutpTSG30IOC2.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30IOC2.EngDT = dt.u16;
RegOutpTSG30IOC2.EngInit = 0;
RegOutpTSG30IOC2.EngMin = 0;
RegOutpTSG30IOC2.EngMax = 65535;
RegOutpTSG30IOC2.TestTolerance = 1;
RegOutpTSG30IOC2.WrittenIn = {};
RegOutpTSG30IOC2.WriteType = 'Phy';

RegOutpTSG30TO1 = DataDict.OpSignal;
RegOutpTSG30TO1.LongName = 'Register TSG30TO1';
RegOutpTSG30TO1.Description = 'Register TSG30TO1';
RegOutpTSG30TO1.DocUnits = 'Cnt';
RegOutpTSG30TO1.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30TO1.EngDT = dt.u08;
RegOutpTSG30TO1.EngInit = 0;
RegOutpTSG30TO1.EngMin = 0;
RegOutpTSG30TO1.EngMax = 1;
RegOutpTSG30TO1.TestTolerance = 1;
RegOutpTSG30TO1.WrittenIn = {};
RegOutpTSG30TO1.WriteType = 'Phy';

RegOutpTSG30TO2 = DataDict.OpSignal;
RegOutpTSG30TO2.LongName = 'Register TSG30TO2';
RegOutpTSG30TO2.Description = 'Register TSG30TO2';
RegOutpTSG30TO2.DocUnits = 'Cnt';
RegOutpTSG30TO2.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30TO2.EngDT = dt.u08;
RegOutpTSG30TO2.EngInit = 0;
RegOutpTSG30TO2.EngMin = 0;
RegOutpTSG30TO2.EngMax = 1;
RegOutpTSG30TO2.TestTolerance = 1;
RegOutpTSG30TO2.WrittenIn = {};
RegOutpTSG30TO2.WriteType = 'Phy';

RegOutpTSG30TO3 = DataDict.OpSignal;
RegOutpTSG30TO3.LongName = 'Register TSG30TO3';
RegOutpTSG30TO3.Description = 'Register TSG30TO3';
RegOutpTSG30TO3.DocUnits = 'Cnt';
RegOutpTSG30TO3.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30TO3.EngDT = dt.u08;
RegOutpTSG30TO3.EngInit = 0;
RegOutpTSG30TO3.EngMin = 0;
RegOutpTSG30TO3.EngMax = 1;
RegOutpTSG30TO3.TestTolerance = 1;
RegOutpTSG30TO3.WrittenIn = {};
RegOutpTSG30TO3.WriteType = 'Phy';

RegOutpTSG30TO4 = DataDict.OpSignal;
RegOutpTSG30TO4.LongName = 'Register TSG30TO4';
RegOutpTSG30TO4.Description = 'Register TSG30TO4';
RegOutpTSG30TO4.DocUnits = 'Cnt';
RegOutpTSG30TO4.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30TO4.EngDT = dt.u08;
RegOutpTSG30TO4.EngInit = 0;
RegOutpTSG30TO4.EngMin = 0;
RegOutpTSG30TO4.EngMax = 1;
RegOutpTSG30TO4.TestTolerance = 1;
RegOutpTSG30TO4.WrittenIn = {};
RegOutpTSG30TO4.WriteType = 'Phy';

RegOutpTSG30TO5 = DataDict.OpSignal;
RegOutpTSG30TO5.LongName = 'Register TSG30TO5';
RegOutpTSG30TO5.Description = 'Register TSG30TO5';
RegOutpTSG30TO5.DocUnits = 'Cnt';
RegOutpTSG30TO5.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30TO5.EngDT = dt.u08;
RegOutpTSG30TO5.EngInit = 0;
RegOutpTSG30TO5.EngMin = 0;
RegOutpTSG30TO5.EngMax = 1;
RegOutpTSG30TO5.TestTolerance = 1;
RegOutpTSG30TO5.WrittenIn = {};
RegOutpTSG30TO5.WriteType = 'Phy';

RegOutpTSG30TO6 = DataDict.OpSignal;
RegOutpTSG30TO6.LongName = 'Register TSG30TO6';
RegOutpTSG30TO6.Description = 'Register TSG30TO6';
RegOutpTSG30TO6.DocUnits = 'Cnt';
RegOutpTSG30TO6.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30TO6.EngDT = dt.u08;
RegOutpTSG30TO6.EngInit = 0;
RegOutpTSG30TO6.EngMin = 0;
RegOutpTSG30TO6.EngMax = 1;
RegOutpTSG30TO6.TestTolerance = 1;
RegOutpTSG30TO6.WrittenIn = {};
RegOutpTSG30TO6.WriteType = 'Phy';

RegOutpTSG30OL1 = DataDict.OpSignal;
RegOutpTSG30OL1.LongName = 'Register TSG30OL1';
RegOutpTSG30OL1.Description = 'Register TSG30OL1';
RegOutpTSG30OL1.DocUnits = 'Cnt';
RegOutpTSG30OL1.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30OL1.EngDT = dt.u08;
RegOutpTSG30OL1.EngInit = 0;
RegOutpTSG30OL1.EngMin = 0;
RegOutpTSG30OL1.EngMax = 1;
RegOutpTSG30OL1.TestTolerance = 1;
RegOutpTSG30OL1.WrittenIn = {};
RegOutpTSG30OL1.WriteType = 'Phy';

RegOutpTSG30OL2 = DataDict.OpSignal;
RegOutpTSG30OL2.LongName = 'Register TSG30OL2';
RegOutpTSG30OL2.Description = 'Register TSG30OL2';
RegOutpTSG30OL2.DocUnits = 'Cnt';
RegOutpTSG30OL2.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30OL2.EngDT = dt.u08;
RegOutpTSG30OL2.EngInit = 0;
RegOutpTSG30OL2.EngMin = 0;
RegOutpTSG30OL2.EngMax = 1;
RegOutpTSG30OL2.TestTolerance = 1;
RegOutpTSG30OL2.WrittenIn = {};
RegOutpTSG30OL2.WriteType = 'Phy';

RegOutpTSG30OL3 = DataDict.OpSignal;
RegOutpTSG30OL3.LongName = 'Register TSG30OL3';
RegOutpTSG30OL3.Description = 'Register TSG30OL3';
RegOutpTSG30OL3.DocUnits = 'Cnt';
RegOutpTSG30OL3.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30OL3.EngDT = dt.u08;
RegOutpTSG30OL3.EngInit = 0;
RegOutpTSG30OL3.EngMin = 0;
RegOutpTSG30OL3.EngMax = 1;
RegOutpTSG30OL3.TestTolerance = 1;
RegOutpTSG30OL3.WrittenIn = {};
RegOutpTSG30OL3.WriteType = 'Phy';

RegOutpTSG30OL4 = DataDict.OpSignal;
RegOutpTSG30OL4.LongName = 'Register TSG30OL4';
RegOutpTSG30OL4.Description = 'Register TSG30OL4';
RegOutpTSG30OL4.DocUnits = 'Cnt';
RegOutpTSG30OL4.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30OL4.EngDT = dt.u08;
RegOutpTSG30OL4.EngInit = 0;
RegOutpTSG30OL4.EngMin = 0;
RegOutpTSG30OL4.EngMax = 1;
RegOutpTSG30OL4.TestTolerance = 1;
RegOutpTSG30OL4.WrittenIn = {};
RegOutpTSG30OL4.WriteType = 'Phy';

RegOutpTSG30OL5 = DataDict.OpSignal;
RegOutpTSG30OL5.LongName = 'Register TSG30OL5';
RegOutpTSG30OL5.Description = 'Register TSG30OL5';
RegOutpTSG30OL5.DocUnits = 'Cnt';
RegOutpTSG30OL5.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30OL5.EngDT = dt.u08;
RegOutpTSG30OL5.EngInit = 0;
RegOutpTSG30OL5.EngMin = 0;
RegOutpTSG30OL5.EngMax = 1;
RegOutpTSG30OL5.TestTolerance = 1;
RegOutpTSG30OL5.WrittenIn = {};
RegOutpTSG30OL5.WriteType = 'Phy';

RegOutpTSG30OL6 = DataDict.OpSignal;
RegOutpTSG30OL6.LongName = 'Register TSG30OL6';
RegOutpTSG30OL6.Description = 'Register TSG30OL6';
RegOutpTSG30OL6.DocUnits = 'Cnt';
RegOutpTSG30OL6.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30OL6.EngDT = dt.u08;
RegOutpTSG30OL6.EngInit = 0;
RegOutpTSG30OL6.EngMin = 0;
RegOutpTSG30OL6.EngMax = 1;
RegOutpTSG30OL6.TestTolerance = 1;
RegOutpTSG30OL6.WrittenIn = {};
RegOutpTSG30OL6.WriteType = 'Phy';

RegOutpTSG30CTL3 = DataDict.OpSignal;
RegOutpTSG30CTL3.LongName = 'Register TSG30CTL3';
RegOutpTSG30CTL3.Description = 'Register TSG30CTL3';
RegOutpTSG30CTL3.DocUnits = 'Cnt';
RegOutpTSG30CTL3.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30CTL3.EngDT = dt.u08;
RegOutpTSG30CTL3.EngInit = 0;
RegOutpTSG30CTL3.EngMin = 0;
RegOutpTSG30CTL3.EngMax = 255;
RegOutpTSG30CTL3.TestTolerance = 1;
RegOutpTSG30CTL3.WrittenIn = {};
RegOutpTSG30CTL3.WriteType = 'Phy';

RegOutpTSG30RMC = DataDict.OpSignal;
RegOutpTSG30RMC.LongName = 'Register TSG30RMC';
RegOutpTSG30RMC.Description = 'Register TSG30RMC';
RegOutpTSG30RMC.DocUnits = 'Cnt';
RegOutpTSG30RMC.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30RMC.EngDT = dt.u08;
RegOutpTSG30RMC.EngInit = 0;
RegOutpTSG30RMC.EngMin = 0;
RegOutpTSG30RMC.EngMax = 1;
RegOutpTSG30RMC.TestTolerance = 1;
RegOutpTSG30RMC.WrittenIn = {};
RegOutpTSG30RMC.WriteType = 'Phy';

RegOutpTSG30RIA = DataDict.OpSignal;
RegOutpTSG30RIA.LongName = 'Register TSG30RIA';
RegOutpTSG30RIA.Description = 'Register TSG30RIA';
RegOutpTSG30RIA.DocUnits = 'Cnt';
RegOutpTSG30RIA.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30RIA.EngDT = dt.u08;
RegOutpTSG30RIA.EngInit = 0;
RegOutpTSG30RIA.EngMin = 0;
RegOutpTSG30RIA.EngMax = 1;
RegOutpTSG30RIA.TestTolerance = 1;
RegOutpTSG30RIA.WrittenIn = {};
RegOutpTSG30RIA.WriteType = 'Phy';

RegOutpTSG30CTL5 = DataDict.OpSignal;
RegOutpTSG30CTL5.LongName = 'Register TSG30CTL5';
RegOutpTSG30CTL5.Description = 'Register TSG30CTL5';
RegOutpTSG30CTL5.DocUnits = 'Cnt';
RegOutpTSG30CTL5.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30CTL5.EngDT = dt.u16;
RegOutpTSG30CTL5.EngInit = 0;
RegOutpTSG30CTL5.EngMin = 0;
RegOutpTSG30CTL5.EngMax = 65535;
RegOutpTSG30CTL5.TestTolerance = 1;
RegOutpTSG30CTL5.WrittenIn = {};
RegOutpTSG30CTL5.WriteType = 'Phy';

RegOutpTSG30AT00 = DataDict.OpSignal;
RegOutpTSG30AT00.LongName = 'Register TSG30AT00';
RegOutpTSG30AT00.Description = 'Register TSG30AT00';
RegOutpTSG30AT00.DocUnits = 'Cnt';
RegOutpTSG30AT00.SwcShoName = 'TSG31CfgAndUse';
RegOutpTSG30AT00.EngDT = dt.u08;
RegOutpTSG30AT00.EngInit = 0;
RegOutpTSG30AT00.EngMin = 0;
RegOutpTSG30AT00.EngMax = 1;
RegOutpTSG30AT00.TestTolerance = 1;
RegOutpTSG30AT00.WrittenIn = {};
RegOutpTSG30AT00.WriteType = 'Phy';

RegOutpTSG30AT01 = DataDict.OpSignal;
RegOutpTSG30AT01.LongName = 'R

[… truncated after 8000 characters …]
```
