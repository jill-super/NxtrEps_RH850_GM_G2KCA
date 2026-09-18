# Electric Power Steering Controller (General Motors G2KCA Platform, Renesas RH850)

![Language](https://img.shields.io/badge/language-C-blue) ![AUTOSAR](https://img.shields.io/badge/standard-AUTOSAR_Classic_4.0.3-green) ![Microcontroller](https://img.shields.io/badge/microcontroller-Renesas_RH850-orange) ![Safety](https://img.shields.io/badge/safety-ISO_26262_ASIL_D-red) ![License](https://img.shields.io/badge/license-MIT-brightgreen) ![Docs](https://img.shields.io/badge/docs-Astro_Starlight-purple)

[Build status](../../actions) · [Documentation site](./docs) · [License](./LICENSE)

Complete Electric Power Steering control software: precise power-assisted steering control, electric-motor power management, vehicle-communication handling, diagnostics, and functional-safety supervision.

> **Reading convention:** prose uses expanded long names (for example “Assist” for the short name `Assi`, “Handwheel Torque” for `HwTq`, “Arbitration” for `Arbn`). Short names always appear in parentheses or code spans on first mention so the text stays traceable to the folders. The [glossary](./docs/src/content/docs/general/glossary.md) maps every short name.

## Contents

- [Overview](#overview)
- [AUTOSAR layers](#autosar-layers)
- [Module matrix (layer and origin)](#module-matrix-layer-and-origin)
- [Third-party versus in-house code](#third-party-versus-in-house-code)
- [Repository structure](#repository-structure)
- [Installation and build](#installation-and-build)
- [Documentation site](#documentation-site)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository holds the controller firmware for an Electric Power Steering system: Application Software steering functions (Assist, Return, Damping, Stability Compensation, End-of-Travel Protection, Power Limiter and some fifty more), customer vehicle functions for General Motors integration, serial-communication message proxies for the high-speed and chassis-expansion buses, complex device drivers configuring the Renesas RH850 peripherals, electronic sensing and power components, architecture libraries (mathematics, interpolation, fixed-point, filtering), AUTOSAR Basic Software (operating system, state managers, memory stack, diagnostic stack, communication stack, watchdog stack, calibration protocol), the Runtime Environment, host-side tooling, and the top-level controller build.

<details>
<summary>Supported vehicle context (General Motors G2KCA platform family)</summary>

The platform family covers mid-size sedans, compact cars, and plug-in hybrids of the era (for example Malibu-class, Cruze-class, Regal-class, Insignia-class, and Volt-class vehicles). Platform detail does not affect the software layering documented here.

</details>

## AUTOSAR layers

| Layer | Long name | What lives here | Folders |
|---|---|---|---:|

| `asw` | Application Software | Application Software Components: steering functions, customer vehicle functions, message proxies, and motor velocity control. Runs above the Runtime Environment. | 150 |
| `cdd` | Complex Device Drivers and Sensor-Actuator Components | Complex Device Drivers and sensor-actuator components: microcontroller peripheral configuration and usage plus electronic sensing, power, and diagnostic managers that need direct hardware access. | 130 |
| `arch` | Architecture Libraries and Platform Support | Architecture libraries and platform support: mathematics, interpolation, fixed-point, filtering, time utilities, and global parameter components shared across the project. | 18 |
| `bsw-services` | Basic Software Services | Basic Software Services: operating system, mode management, memory, diagnostic event handling, watchdog management, and manufacturing services. | 14 |
| `bsw-communication` | Basic Software Communication Stack | Basic Software Communication Stack: interaction layer, transport protocol, network management, diagnostics, calibration protocol, and the General Motors local area network handler. | 7 |
| `mcal` | Microcontroller Abstraction Layer | Microcontroller Abstraction Layer: drivers for the Renesas RH850 microcontroller peripherals (microcontroller, digital input-output, ports, serial interfaces, flash, watchdog, controller area network). | 8 |
| `ecu-abstraction` | Electronic Control Unit Abstraction Layer | Electronic Control Unit Abstraction Layer: input-output hardware abstraction and memory abstractions that decouple higher layers from microcontroller specifics. | 5 |
| `rte` | Runtime Environment | Runtime Environment: generated communication backbone connecting Application Software Components and Basic Software. | 1 |
| `tools` | Auxiliary Tools and Configuration | Auxiliary host-side tools and configuration support: generators, checkers, scripts, and engineering utilities. Not flashed to the controller. | 11 |
| `integration` | System Integration and Platform | System Integration and Platform: the top-level controller project plus platform-specific identification, checkpoint, and customer diagnostic components. | 4 |

Design folders (`..._Design`) hold functional design artefacts; implementation folders (`..._Impl`) hold compilable sources, AUTOSAR descriptors, and tool projects. The documentation keeps one page per folder so both stay traceable.

## Module matrix (layer and origin)

<details>
<summary>How to read origin</summary>

- **Vector-provided** — third-party communication-stack or tooling delivery (read-only).
- **Renesas-provided** — microcontroller vendor driver (read-only).
- **Custom (in-house)** — project-developed logic; may contain regenerated Runtime Environment scaffolding, which is called out on the page.

</details>


<details>
<summary>Application Software — 150 modules</summary>


| Folder | Long name | Origin |
|---|---|---|

| `CF009A_GmOvrlStMgr_Design` | General Motors Overall State Manager | Custom (in-house) |
| `CF009A_GmOvrlStMgr_Impl` | General Motors Overall State Manager | Custom (in-house) |
| `CF010A_GmTqArbn_Design` | General Motors Torque Arbitration | Custom (in-house) |
| `CF010A_GmTqArbn_Impl` | General Motors Torque Arbitration | Custom (in-house) |
| `CF012A_GmStrtStop_Design` | General Motors Start Stop | Custom (in-house) |
| `CF012A_GmStrtStop_Impl` | General Motors Start Stop | Custom (in-house) |
| `CF016A_GMVehSpdArbn_Impl` | General Motors Vehicle Speed Arbitration | Custom (in-house) |
| `CF016A_GmVehSpdArbn_Design` | General Motors Vehicle Speed Arbitration | Custom (in-house) |
| `CF017A_GMVehPwrMod_Impl` | General Motors Vehicle Power Mode | Custom (in-house) |
| `CF017A_GmVehPwrMod_Design` | General Motors Vehicle Power Mode | Custom (in-house) |
| `CF018A_GmRoadWhlInQlfr_Design` | General Motors Road Wheel Input Qualifier | Custom (in-house) |
| `CF018A_GmRoadWhlInQlfr_Impl` | General Motors Road Wheel Input Qualifier | Custom (in-house) |
| `CF025A_GmFctDiArbn_Design` | General Motors Function Disable Arbitration | Custom (in-house) |
| `CF025A_GmFctDiArbn_Impl` | General Motors Function Disable Arbitration | Custom (in-house) |
| `MM000B_SerlComInpProxy_Impl` | Serial Communication Input Proxy | Custom (in-house) |
| `MM001A_GmMsg0C5BusHiSpd_Impl` | General Motors Message 0x0C5 on High Speed Bus Proxy | Custom (in-house) |
| `MM002A_GmMsg0C9BusHiSpd_Impl` | General Motors Message 0x0C9 on High Speed Bus Proxy | Custom (in-house) |
| `MM004A_GmMsg17DBusHiSpd_Impl` | General Motors Message 0x17D on High Speed Bus Proxy | Custom (in-house) |
| `MM005A_GmMsg180BusHiSpd_Impl` | General Motors Message 0x180 on High Speed Bus Proxy | Custom (in-house) |
| `MM006A_GmMsg1E9BusHiSpd_Impl` | General Motors Message 0x1E9 on High Speed Bus Proxy | Custom (in-house) |
| `MM007A_GmMsg1F1BusHiSpd_Impl` | General Motors Message 0x1F1 on High Speed Bus Proxy | Custom (in-house) |
| `MM008A_GmMsg1F5BusHiSpd_Impl` | General Motors Message 0x1F5 on High Speed Bus Proxy | Custom (in-house) |
| `MM009A_GmMsg214BusHiSpd_Impl` | General Motors Message 0x214 on High Speed Bus Proxy | Custom (in-house) |
| `MM010A_GmMsg232BusHiSpd_Impl` | General Motors Message 0x232 on High Speed Bus Proxy | Custom (in-house) |
| `MM011A_GmMsg348BusHiSpd_Impl` | General Motors Message 0x348 on High Speed Bus Proxy | Custom (in-house) |
| `MM012A_GmMsg34ABusHiSpd_Impl` | General Motors Message 0x34A on High Speed Bus Proxy | Custom (in-house) |
| `MM014A_GmMsg3F1BusHiSpd_Impl` | General Motors Message 0x3F1 on High Speed Bus Proxy | Custom (in-house) |
| `MM016A_GmMsg500BusHiSpd_Impl` | General Motors Message 0x500 on High Speed Bus Proxy | Custom (in-house) |
| `MM017A_GmMsg180BusChassisExp_Impl` | General Motors Message 0x180 on Chassis Expansion Bus Proxy | Custom (in-house) |
| `MM018A_GmMsg182BusChassisExp_Impl` | General Motors Message 0x182 on Chassis Expansion Bus Proxy | Custom (in-house) |
| `MM019A_GmMsg337BusChassisExp_Impl` | General Motors Message 0x337 on Chassis Expansion Bus Proxy | Custom (in-house) |
| `MM020A_GmMsg348BusChassisExp_Impl` | General Motors Message 0x348 on Chassis Expansion Bus Proxy | Custom (in-house) |
| `MM021A_GmMsg34ABusChassisExp_Impl` | General Motors Message 0x34A on Chassis Expansion Bus Proxy | Custom (in-house) |
| `MM022A_GmMsg4D1BusHiSpd_Impl` | General Motors Message 0x4D1 on High Speed Bus Proxy | Custom (in-house) |
| `MM500B_SerlComOutpProxy_Impl` | Serial Communication Output Proxy | Custom (in-house) |
| `MM501A_GmMsg148BusHiSpd_Impl` | General Motors Message 0x148 on High Speed Bus Proxy | Custom (in-house) |
| `MM502A_GmMsg184BusHiSpd_Impl` | General Motors Message 0x184 on High Speed Bus Proxy | Custom (in-house) |
| `MM503A_GmMsg1E5BusHiSpd_Impl` | General Motors Message 0x1E5 on High Speed Bus Proxy | Custom (in-house) |
| `MM504A_GmMsg778BusHiSpd_Impl` | General Motors Message 0x778 on High Speed Bus Proxy | Custom (in-house) |
| `MM505A_GmMsg1CABusChassisExp_Impl` | General Motors Message 0x1CA on Chassis Expansion Bus Proxy | Custom (in-house) |
| `MM506A_GmMsg1E5BusChassisExp_Impl` | General Motors Message 0x1E5 on Chassis Expansion Bus Proxy | Custom (in-house) |
| `MM507A_GmMsg335BusChassisExp_Impl` | General Motors Message 0x335 on Chassis Expansion Bus Proxy | Custom (in-house) |
| `NM100A_MotVelCtrl_Design` | Motor Velocity Control | Custom (in-house) |
| `NM100A_MotVelCtrl_Impl` | Motor Velocity Control | Custom (in-house) |
| `SF001A_Assi_Design` | Assist | Custom (in-house) |
| `SF001A_Assi_Impl` | Assist | Custom (in-house) |
| `SF002A_Rtn_Design` | Return | Custom (in-house) |
| `SF002A_Rtn_Impl` | Return | Custom (in-house) |
| `SF003A_Dampg_Design` | Damping | Custom (in-house) |
| `SF003A_Dampg_Impl` | Damping | Custom (in-house) |
| `SF004B_AssiSumLim_Design` | Assist Summation Limiter | Custom (in-house) |
| `SF004B_AssiSumLim_Impl` | Assist Summation Limiter | Custom (in-house) |
| `SF005A_StOutpCtrl_Design` | Steering Output Control | Custom (in-house) |
| `SF005A_StOutpCtrl_Impl` | Steering Output Control | Custom (in-house) |
| `SF006A_TEstimn_Design` | Torque Estimation | Custom (in-house) |
| `SF006A_TEstimn_Impl` | Torque Estimation | Custom (in-house) |
| `SF007A_SysFricLrng_Design` | System Friction Learning | Custom (in-house) |
| `SF007A_SysFricLrng_Impl` | System Friction Learning | Custom (in-house) |
| `SF009A_DutyCycThermProtn_Design` | Duty Cycle Thermal Protection | Custom (in-house) |
| `SF009A_DutyCycThermProtn_Impl` | Duty Cycle Thermal Protection | Custom (in-house) |
| `SF011A_EotLrng_Design` | End of Travel Learning | Custom (in-house) |
| `SF011A_EotLrng_Impl` | End of Travel Learning | Custom (in-house) |
| `SF012A_HysCmp_Design` | Hysteresis Compensation | Custom (in-house) |
| `SF012A_HysCmp_Impl` | Hysteresis Compensation | Custom (in-house) |
| `SF013A_PullCmpActv_Design` | Pull Compensation Activation | Custom (in-house) |
| `SF013A_PullCmpActv_Impl` | Pull Compensation Activation | Custom (in-house) |
| `SF014A_InertiaCmpVel_Design` | Inertia Compensation by Velocity | Custom (in-house) |
| `SF014A_InertiaCmpVel_Impl` | Inertia Compensation by Velocity | Custom (in-house) |
| `SF015A_WhlImbRejctn_Design` | Wheel Imbalance Rejection | Custom (in-house) |
| `SF015A_WhlImbRejctn_Impl` | Wheel Imbalance Rejection | Custom (in-house) |
| `SF016A_VehSpdLimr_Design` | Vehicle Speed Limiter | Custom (in-house) |
| `SF016A_VehSpdLimr_Impl` | Vehicle Speed Limiter | Custom (in-house) |
| `SF017A_HiLoadStallLimr_Design` | High Load Stall Limiter | Custom (in-house) |
| `SF017A_HiLoadStallLimr_Impl` | High Load Stall Limiter | Custom (in-house) |
| `SF018A_EotProtn_Design` | End of Travel Protection | Custom (in-house) |
| `SF018A_EotProtn_Impl` | End of Travel Protection | Custom (in-house) |
| `SF019B_PwrLimr_Design` | Power Limiter | Custom (in-house) |
| `SF019B_PwrLimr_Impl` | Power Limiter | Custom (in-house) |
| `SF020A_HwAgTrakgServo_Design` | Handwheel Angle Tracking Servo | Custom (in-house) |
| `SF020A_HwAgTrakgServo_Impl` | Handwheel Angle Tracking Servo | Custom (in-house) |
| `SF021A_HwAgTrajGenn_Design` | Handwheel Angle Trajectory Generation | Custom (in-house) |
| `SF021A_HwAgTrajGenn_Impl` | Handwheel Angle Trajectory Generation | Custom (in-house) |
| `SF023A_TunSelnAuthy_Design` | Tune Selection Authority | Custom (in-house) |
| `SF023A_TunSelnAuthy_Impl` | Tune Selection Authority | Custom (in-house) |
| `SF027A_EotProtnFwl_Design` | End of Travel Protection Firewall | Custom (in-house) |
| `SF027A_EotProtnFwl_Impl` | End of Travel Protection Firewall | Custom (in-house) |
| `SF028A_AssiHiFrq_Design` | Assist High Frequency | Custom (in-house) |
| `SF028A_AssiHiFrq_Impl` | Assist High Frequency | Custom (in-house) |
| `SF029A_StabyCmp_Design` | Stability Compensation | Custom (in-house) |
| `SF029A_StabyCmp_Impl` | Stability Compensation | Custom (in-house) |
| `SF031A_CurrReasbnDiagc_Design` | Current Reasonableness Diagnostic | Custom (in-house) |
| `SF031A_CurrReasbnDiagc_Impl` | Current Reasonableness Diagnostic | Custom (in-house) |
| `SF032A_MotTqCmdSca_Design` | Motor Torque Command Scaling | Custom (in-house) |
| `SF032A_MotTqCmdSca_Impl` | Motor Torque Command Scaling | Custom (in-house) |
| `SF033A_VehSigCdng_Design` | Vehicle Signal Coding | Custom (in-house) |
| `SF033A_VehSigCdng_Impl` | Vehicle Signal Coding | Custom (in-house) |
| `SF034A_AssiPahFwl_Design` | Assist Path Firewall | Custom (in-house) |
| `SF034A_AssiPahFwl_Impl` | Assist Path Firewall | Custom (in-house) |
| `SF035A_DampgPahFwl_Design` | Damping Path Firewall | Custom (in-house) |
| `SF035A_DampgPahFwl_Impl` | Damping Path Firewall | Custom (in-house) |
| `SF036A_RtnPahFwl_Design` | Return Path Firewall | Custom (in-house) |
| `SF036A_RtnPahFwl_Impl` | Return Path Firewall | Custom (in-house) |
| `SF038A_LimrCdng_Design` | Limiter Coding | Custom (in-house) |
| `SF038A_LimrCdng_Impl` | Limiter Coding | Custom (in-house) |
| `SF040A_MotVel_Design` | Motor Velocity | Custom (in-house) |
| `SF040A_MotVel_Impl` | Motor Velocity | Custom (in-house) |
| `SF041A_CmplncErr_Design` | Compliance Error | Custom (in-house) |
| `SF041A_CmplncErr_Impl` | Compliance Error | Custom (in-house) |
| `SF042A_HwAgSnsrls_Design` | Handwheel Angle Sensorless Estimation | Custom (in-house) |
| `SF042A_HwAgSnsrls_Impl` | Handwheel Angle Sensorless Estimation | Custom (in-house) |
| `SF043A_TqOscn_Design` | Torque Oscillation | Custom (in-house) |
| `SF043A_TqOscn_Impl` | Torque Oscillation | Custom (in-house) |
| `SF044A_HowDetn_Design` | Hands-Off Detection | Custom (in-house) |
| `SF044A_HowDetn_Impl` | Hands-Off Detection | Custom (in-house) |
| `SF045A_HwAgSysArbn_Design` | Handwheel Angle System Arbitration | Custom (in-house) |
| `SF045A_HwAgSysArbn_Impl` | Handwheel Angle System Arbitration | Custom (in-house) |
| `SF048A_TqLoa_Design` | Torque Loss of Assist | Custom (in-house) |
| `SF048A_TqLoa_Impl` | Torque Loss of Assist | Custom (in-house) |
| `SF049A_LoaMgr_Design` | Loss of Assist Manager | Custom (in-house) |
| `SF049A_LoaMgr_Impl` | Loss of Assist Manager | Custom (in-house) |
| `SF050A_MotTqTranlDampg_Design` | Motor Torque Transient Damping | Custom (in-house) |
| `SF050A_MotTqTranlDampg_Impl` | Motor Torque Transient Damping | Custom (in-house) |
| `SF051A_SnsrOffsLrng_Design` | Sensor Offset Learning | Custom (in-house) |
| `SF051A_SnsrOffsLrng_Impl` | Sensor Offset Learning | Custom (in-house) |
| `SF052A_SnsrOffsCorrn_Design` | Sensor Offset Correction | Custom (in-house) |
| `SF052A_SnsrOffsCorrn_Impl` | Sensor Offset Correction | Custom (in-house) |
| `SF053A_HwAgVehCentrTrim_Design` | Handwheel Angle Vehicle Center Trim | Custom (in-house) |
| `SF053A_HwAgVehCentrTrim_Impl` | Handwheel Angle Vehicle Center Trim | Custom (in-house) |
| `SF054A_PwrpkCmpbltyChk_Design` | Powerpack Compatibility Check | Custom (in-house) |
| `SF054A_PwrpkCmpbltyChk_Impl` | Powerpack Compatibility Check | Custom (in-house) |
| `SF101A_MotQuadDetn_Design` | Motor Quadrature Detection | Custom (in-house) |
| `SF101A_MotQuadDetn_Impl` | Motor Quadrature Detection | Custom (in-house) |
| `SF102A_MotCtrlPrmEstimn_Design` | Motor Control Parameter Estimation | Custom (in-house) |
| `SF102A_MotCtrlPrmEstimn_Impl` | Motor Control Parameter Estimation | Custom (in-house) |
| `SF103A_MotRefMdl_Design` | Motor Reference Model | Custom (in-house) |
| `SF103A_MotRefMdl_Impl` | Motor Reference Model | Custom (in-house) |
| `SF104A_MotCurrRegCfg_Design` | Motor Current Regulator Configuration | Custom (in-house) |
| `SF104A_MotCurrRegCfg_Impl` | Motor Current Regulator Configuration | Custom (in-house) |
| `SF105A_MotCurrRegVltgLimr_Design` | Motor Current Regulator Voltage Limiter | Custom (in-house) |
| `SF105A_MotCurrRegVltgLimr_Impl` | Motor Current Regulator Voltage Limiter | Custom (in-house) |
| `SF106A_MotRplCoggCfg_Design` | Motor Ripple and Cogging Configuration | Custom (in-house) |
| `SF106A_MotRplCoggCfg_Impl` | Motor Ripple and Cogging Configuration | Custom (in-house) |
| `SF107A_MotRplCoggCmd_Design` | Motor Ripple and Cogging Command | Custom (in-house) |
| `SF107A_MotRplCoggCmd_Impl` | Motor Ripple and Cogging Command | Custom (in-house) |
| `SF108A_MotCurrPeakEstimn_Design` | Motor Current Peak Estimation | Custom (in-house) |
| `SF108A_MotCurrPeakEstimn_Impl` | Motor Current Peak Estimation | Custom (in-house) |
| `SF109A_ElecPwrCns_Design` | Electric Power Consumption | Custom (in-house) |
| `SF109A_ElecPwrCns_Impl` | Electric Power Consumption | Custom (in-house) |
| `SF999A_SysGlbPrm_Design` | System Global Parameters | Custom (in-house) |
| `SF999A_SysGlbPrm_Impl` | System Global Parameters | Custom (in-house) |

</details>


<details>
<summary>Complex Device Drivers and Sensor-Actuator Components — 130 modules</summary>


| Folder | Long name | Origin |
|---|---|---|

| `CM010C_GmG2kcaMcuCfg_Design` | General Motors G2KCA Microcontroller Configuration | Custom (in-house) |
| `CM100A_StrtUpSeq_Design` | Startup Sequence | Custom (in-house) |
| `CM101A_ExcpnHndlg_Design` | Exception Handling | Custom (in-house) |
| `CM101A_ExcpnHndlg_Impl` | Exception Handling | Custom (in-house) |
| `CM102A_FlsMem_Design` | Flash Memory Handling | Custom (in-house) |
| `CM102A_FlsMem_Impl` | Flash Memory Handling | Custom (in-house) |
| `CM103A_RamMem_Design` | Random Access Memory Handling | Custom (in-house) |
| `CM103A_RamMem_Impl` | Random Access Memory Handling | Custom (in-house) |
| `CM104A_EcmOutpAndDiagc_Design` | Electronic Control Module Output and Diagnostic | Custom (in-house) |
| `CM104A_EcmOutpAndDiagc_Impl` | Electronic Control Module Output and Diagnostic | Custom (in-house) |
| `CM106A_McuCoreCfgAndDiagc_Design` | Microcontroller Core Configuration and Diagnostic | Custom (in-house) |
| `CM106A_McuCoreCfgAndDiagc_Impl` | Microcontroller Core Configuration and Diagnostic | Custom (in-house) |
| `CM107A_GuardCfgAndDiagc_Design` | Guard Configuration and Diagnostic | Custom (in-house) |
| `CM107A_GuardCfgAndDiagc_Impl` | Guard Configuration and Diagnostic | Custom (in-house) |
| `CM108A_DataAndAdrPar_Design` | Data and Address Parity | Custom (in-house) |
| `CM108A_DataAndAdrPar_Impl` | Data and Address Parity | Custom (in-house) |
| `CM109A_ClkCfgAndMon_Design` | Clock Configuration and Monitoring | Custom (in-house) |
| `CM109A_ClkCfgAndMon_Impl` | Clock Configuration and Monitoring | Custom (in-house) |
| `CM111A_VrfyCritReg_Design` | Verify Critical Registers | Custom (in-house) |
| `CM111A_VrfyCritReg_Impl` | Verify Critical Registers | Custom (in-house) |
| `CM200C_DmaCfgAndUse_Design` | Direct Memory Access Configuration and Usage | Custom (in-house) |
| `CM200C_DmaCfgAndUse_Impl` | Direct Memory Access Configuration and Usage | Custom (in-house) |
| `CM300A_ADC0CfgAndUse_Design` | ADC 0 Configuration And Use | Custom (in-house) |
| `CM300A_Adc0CfgAndUse_Impl` | Analog to Digital Converter 0 Configuration And Use | Custom (in-house) |
| `CM320A_Adc1CfgAndUse_Design` | Analog to Digital Converter 1 Configuration And Use | Custom (in-house) |
| `CM320A_Adc1CfgAndUse_Impl` | Analog to Digital Converter 1 Configuration And Use | Custom (in-house) |
| `CM340A_AdcDiagc_Design` | Analog to Digital Converter Diagnostic | Custom (in-house) |
| `CM340A_AdcDiagc_Impl` | Analog to Digital Converter Diagnostic | Custom (in-house) |
| `CM410B_SnsrMeasStrt_Design` | Sensor Measurement Start | Custom (in-house) |
| `CM410B_SnsrMeasStrt_Impl` | Sensor Measurement Start | Custom (in-house) |
| `CM455A_Tauj0CfgAndUse_Design` | Tauj0 Configuration And Use | Custom (in-house) |
| `CM455A_Tauj0CfgAndUse_Impl` | Tauj0 Configuration And Use | Custom (in-house) |
| `CM460A_Tauj1CfgAndUse_Design` | Tauj1 Configuration And Use | Custom (in-house) |
| `CM460A_Tauj1CfgAndUse_Impl` | Tauj1 Configuration And Use | Custom (in-house) |
| `CM475A_TSG31CfgAndUse_Design` | TSG 31 Configuration And Use | Custom (in-house) |
| `CM475A_TSG31CfgAndUse_Impl` | TSG 31 Configuration And Use | Custom (in-house) |
| `CM510A_MotAg3Meas_Design` | Motor Ag3 Measurement | Custom (in-house) |
| `CM510A_MotAg3Meas_Impl` | Motor Ag3 Measurement | Custom (in-house) |
| `CM515A_MotAg4Meas_Design` | Motor Ag4 Measurement | Custom (in-house) |
| `CM515A_MotAg4Meas_Impl` | Motor Ag4 Measurement | Custom (in-house) |
| `CM600A_CSIG0CfgAndUse_Design` | CSIG 0 Configuration And Use | Custom (in-house) |
| `CM610A_CSIH0CfgAndUse_Design` | CSIH 0 Configuration And Use | Custom (in-house) |
| `CM620C_MotAg0Meas_Design` | Motor Ag0 Measurement | Custom (in-house) |
| `CM620C_MotAg0Meas_Impl` | Motor Ag0 Measurement | Custom (in-house) |
| `CM630A_CSIH2CfgAndUse_Design` | CSIH 2 Configuration And Use | Custom (in-house) |
| `CM640C_MotAg1Meas_Design` | Motor Ag1 Measurement | Custom (in-house) |
| `CM640C_MotAg1Meas_Impl` | Motor Ag1 Measurement | Custom (in-house) |
| `CM650A_HwTq0Meas_Design` | Handwheel Tq0 Measurement | Custom (in-house) |
| `CM650A_HwTq0Meas_Impl` | Handwheel Tq0 Measurement | Custom (in-house) |
| `CM660A_HwTq1Meas_Design` | Handwheel Tq1 Measurement | Custom (in-house) |
| `CM660A_HwTq1Meas_Impl` | Handwheel Tq1 Measurement | Custom (in-house) |
| `CM670A_HwAg1Meas_Design` | Handwheel Ag1 Measurement | Custom (in-house) |
| `CM670A_HwAg1Meas_Impl` | Handwheel Ag1 Measurement | Custom (in-house) |
| `CM680A_HwTq2Meas_Design` | Handwheel Tq2 Measurement | Custom (in-house) |
| `CM680A_HwTq2Meas_Impl` | Handwheel Tq2 Measurement | Custom (in-house) |
| `CM690A_HwAg0Meas_Design` | Handwheel Ag0 Measurement | Custom (in-house) |
| `CM690A_HwAg0Meas_Impl` | Handwheel Ag0 Measurement | Custom (in-house) |
| `CM700A_HwTq3Meas_Design` | Handwheel Tq3 Measurement | Custom (in-house) |
| `CM700A_HwTq3Meas_Impl` | Handwheel Tq3 Measurement | Custom (in-house) |
| `CM745A_Sci30CfgAndUse_Design` | Sci30 Configuration And Use | Custom (in-house) |
| `CM745A_Sci30CfgAndUse_Impl` | Sci30 Configuration And Use | Custom (in-house) |
| `CM800A_SyncCrc_Design` | Synchronous Cyclic Redundancy Check | Custom (in-house) |
| `CM800A_SyncCrc_Impl` | Synchronous Cyclic Redundancy Check | Custom (in-house) |
| `DF001A_FltInj_Design` | Fault Injection | Custom (in-house) |
| `DF001A_FltInj_Impl` | Fault Injection | Custom (in-house) |
| `DF002A_Swp_Design` | Software Programming Support | Custom (in-house) |
| `DF002A_Swp_Impl` | Software Programming Support | Custom (in-house) |
| `DF003A_McuErrInj_Impl` | Microcontroller Error Injection | Custom (in-house) |
| `ES002A_McuDiagc_Design` | Microcontroller Diagnostic | Custom (in-house) |
| `ES002A_McuDiagc_Impl` | Microcontroller Diagnostic | Custom (in-house) |
| `ES003A_PwrDiscnct_Design` | Power Disconnect | Custom (in-house) |
| `ES003A_PwrDiscnct_Impl` | Power Disconnect | Custom (in-house) |
| `ES004A_PwrUpSeq_Design` | Power Up Sequence | Custom (in-house) |
| `ES004A_PwrUpSeq_Impl` | Power Up Sequence | Custom (in-house) |
| `ES005A_TmplMonr_Design` | Temperature Monitoring | Custom (in-house) |
| `ES005A_TmplMonr_Impl` | Temperature Monitoring | Custom (in-house) |
| `ES006A_NvM_Design` | Non-Volatile M | Custom (in-house) |
| `ES006A_NvM_Impl` | Non-Volatile M | Custom (in-house) |
| `ES008A_PwrSply_Design` | Power Supply | Custom (in-house) |
| `ES008A_PwrSply_Impl` | Power Supply | Custom (in-house) |
| `ES011A_DualEcuIdn_Design` | Dual Electronic Control Unit Identification | Custom (in-house) |
| `ES011A_DualEcuIdn_Impl` | Dual Electronic Control Unit Identification | Custom (in-house) |
| `ES100A_SysStMod_Design` | System State Mode | Custom (in-house) |
| `ES100A_SysStMod_Impl` | System State Mode | Custom (in-house) |
| `ES101A_DiagcMgr_Design` | Diagnostic Manager | Custom (in-house) |
| `ES101A_DiagcMgr_Impl` | Diagnostic Manager | Custom (in-house) |
| `ES102A_PolarityCfg_Design` | Polarity Configuration | Custom (in-house) |
| `ES102A_PolarityCfg_Impl` | Polarity Configuration | Custom (in-house) |
| `ES105A_StHlthSigNormn_Design` | State Health Signal Normalization | Custom (in-house) |
| `ES105A_StHlthSigNormn_Impl` | State Health Signal Normalization | Custom (in-house) |
| `ES106A_StHlthSigStc_Design` | State Health Signal Static | Custom (in-house) |
| `ES106A_StHlthSigStc_Impl` | State Health Signal Static | Custom (in-house) |
| `ES200A_CurrMeas_Design` | Current Measurement | Custom (in-house) |
| `ES200A_CurrMeas_Impl` | Current Measurement | Custom (in-house) |
| `ES208A_CurrMeasArbn_Design` | Current Measurement Arbitration | Custom (in-house) |
| `ES208A_CurrMeasArbn_Impl` | Current Measurement Arbitration | Custom (in-house) |
| `ES209A_CurrMeasCorrln_Design` | Current Measurement Correlation | Custom (in-house) |
| `ES209A_CurrMeasCorrln_Impl` | Current Measurement Correlation | Custom (in-house) |
| `ES210A_EcuTMeas_Design` | Electronic Control Unit Temperature Measurement | Custom (in-house) |
| `ES210A_EcuTMeas_Impl` | Electronic Control Unit Temperature Measurement | Custom (in-house) |
| `ES228A_HwTqArbn_Design` | Handwheel Torque Arbitration | Custom (in-house) |
| `ES228A_HwTqArbn_Impl` | Handwheel Torque Arbitration | Custom (in-house) |
| `ES229A_HwTqCorrln_Design` | Handwheel Torque Correlation | Custom (in-house) |
| `ES229A_HwTqCorrln_Impl` | Handwheel Torque Correlation | Custom (in-house) |
| `ES238B_HwAgArbn_Design` | Handwheel Angle Arbitration | Custom (in-house) |
| `ES238B_HwAgArbn_Impl` | Handwheel Angle Arbitration | Custom (in-house) |
| `ES239B_HwAgCorrln_Design` | Handwheel Angle Correlation | Custom (in-house) |
| `ES239B_HwAgCorrln_Impl` | Handwheel Angle Correlation | Custom (in-house) |
| `ES247A_MotAgCmp_Design` | Motor Angle Comparison | Custom (in-house) |
| `ES247A_MotAgCmp_Impl` | Motor Angle Comparison | Custom (in-house) |
| `ES248B_MotAgArbn_Design` | Motor Angle Arbitration | Custom (in-house) |
| `ES248B_MotAgArbn_Impl` | Motor Angle Arbitration | Custom (in-house) |
| `ES249B_MotAgCorrln_Design` | Motor Angle Correlation | Custom (in-house) |
| `ES249B_MotAgCorrln_Impl` | Motor Angle Correlation | Custom (in-house) |
| `ES250A_BattVltg_Design` | Battery Voltage | Custom (in-house) |
| `ES250A_BattVltg_Impl` | Battery Voltage | Custom (in-house) |
| `ES259A_BattVltgCorrln_Design` | Battery Voltage Correlation | Custom (in-house) |
| `ES259A_BattVltgCorrln_Impl` | Battery Voltage Correlation | Custom (in-house) |
| `ES300A_SinVltgGenn_Design` | Sine Voltage Generation | Custom (in-house) |
| `ES300A_SinVltgGenn_Impl` | Sine Voltage Generation | Custom (in-house) |
| `ES311A_GateDrv0Ctrl_Design` | Gate Driver 0 Control | Custom (in-house) |
| `ES311A_GateDrv0Ctrl_Impl` | Gate Driver 0 Control | Custom (in-house) |
| `ES312A_GateDrv1Ctrl_Design` | Gate Driver 1 Control | Custom (in-house) |
| `ES312A_GateDrv1Ctrl_Impl` | Gate Driver 1 Control | Custom (in-house) |
| `ES320A_MotDrvDiagc_Design` | Motor Driver Diagnostic | Custom (in-house) |
| `ES320A_MotDrvDiagc_Impl` | Motor Driver Diagnostic | Custom (in-house) |
| `ES400A_TunSelnMngt_Design` | Tune Selection Management | Custom (in-house) |
| `ES400A_TunSelnMngt_Impl` | Tune Selection Management | Custom (in-house) |
| `ES999A_ElecGlbPrm_Design` | Electrical Global Parameters | Custom (in-house) |
| `ES999A_ElecGlbPrm_Impl` | Electrical Global Parameters | Custom (in-house) |

</details>


<details>
<summary>Architecture Libraries and Platform Support — 18 modules</summary>


| Folder | Long name | Origin |
|---|---|---|

| `AR100A_NxtrMath_Impl` | Nexteer Mathematics Library | Custom (in-house) |
| `AR101A_NxtrIntrpn_Design` | Nexteer Interpolation Library | Custom (in-house) |
| `AR101A_NxtrIntrpn_Impl` | Nexteer Interpolation Library | Custom (in-house) |
| `AR102A_NxtrTi_Design` | Nexteer Time Library | Custom (in-house) |
| `AR102A_NxtrTi_Impl` | Nexteer Time Library | Custom (in-house) |
| `AR103A_NxtrFixdPt_Impl` | Nexteer Fixed Point Library | Custom (in-house) |
| `AR104A_NxtrFil_Impl` | Nexteer Filter Library | Custom (in-house) |
| `AR200A_ArSuprt_Impl` | AUTOSAR Support | Custom (in-house) |
| `AR201A_ArCplrSuprt_Impl` | AUTOSAR Coupler Support | Custom (in-house) |
| `AR202A_MicroCtrlrSuprt_Impl` | Microcontroller Support | Custom (in-house) |
| `AR300A_MotCtrlMgr_Design` | Motor Control Manager | Custom (in-house) |
| `AR300A_MotCtrlMgr_Impl` | Motor Control Manager | Custom (in-house) |
| `AR350A_ImcArbn_Design` | Internal Motor Control Arbitration | Custom (in-house) |
| `AR350A_ImcArbn_Impl` | Internal Motor Control Arbitration | Custom (in-house) |
| `AR998A_NxtrDet_Design` | Nexteer Detection Library | Custom (in-house) |
| `AR998A_NxtrDet_Impl` | Nexteer Detection Library | Custom (in-house) |
| `AR999A_ArchGlbPrm_Design` | Architecture Global Parameters | Custom (in-house) |
| `AR999A_ArchGlbPrm_Impl` | Architecture Global Parameters | Custom (in-house) |

</details>


<details>
<summary>Basic Software Services — 14 modules</summary>


| Folder | Long name | Origin |
|---|---|---|

| `BswM` | Basic Software Mode Manager | Vector-provided |
| `Crc` | Cyclic Redundancy Check Library | Vector-provided |
| `Dem` | Diagnostic Event Manager | Vector-provided |
| `Det` | Development Error Tracer | Vector-provided |
| `EcuM` | Electronic Control Unit State Manager | Vector-provided |
| `NM001A_CmnMfgSrv_Impl` | Common Manufacturing Service | Custom (in-house) |
| `NM002A_CmnMfgSrvIf_Impl` | Common Manufacturing Service Interface | Custom (in-house) |
| `NM003A_NxtrSwIds_Impl` | Nexteer Software Identifications | Custom (in-house) |
| `NM004A_NxtrCalIds_Impl` | Nexteer Calibration Identifications | Custom (in-house) |
| `NM010A_ProgMfgSrv_Impl` | Programming Manufacturing Service | Custom (in-house) |
| `NvM` | Non-Volatile Random Access Memory Manager | Vector-provided |
| `Os` | Operating System | Vector-provided |
| `VectorBswSuprt` | Vector Basic Software Support Library | Vector-provided |
| `WdgM` | Watchdog Manager | Vector-provided |

</details>


<details>
<summary>Basic Software Communication Stack — 7 modules</summary>


| Folder | Long name | Origin |
|---|---|---|

| `Diag` | Diagnostic Gateway Addon | Vector-provided |
| `ES104A_XcpIf_Impl` | Universal Measurement and Calibration Protocol Interface | Custom (in-house) |
| `GM_000A_GMLAN3.1MchRH850_Impl` | General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 | Vector-provided |
| `Il` | Interaction Layer (Signal Communication) | Vector-provided |
| `Nm` | Network Management | Vector-provided |
| `Tp` | Transport Protocol (ISO 15765-2) | Vector-provided |
| `Xcp` | Universal Measurement and Calibration Protocol | Vector-provided |

</details>


<details>
<summary>Microcontroller Abstraction Layer — 8 modules</summary>


| Folder | Long name | Origin |
|---|---|---|

| `Can` | Controller Area Network Driver | Vector-provided |
| `Dio` | Digital Input Output Driver | Renesas-provided |
| `Fls` | Flash Memory Driver | Renesas-provided |
| `Mcu` | Microcontroller Unit Driver | Renesas-provided |
| `Port` | Port Pin Driver | Renesas-provided |
| `RenesasMcalSuprt` | Renesas Microcontroller Abstraction Support | Renesas-provided |
| `Spi` | Serial Peripheral Interface Driver | Renesas-provided |
| `Wdg` | Watchdog Driver | Renesas-provided |

</details>


<details>
<summary>Electronic Control Unit Abstraction Layer — 5 modules</summary>


| Folder | Long name | Origin |
|---|---|---|

| `EcuC` | Electronic Control Unit Configuration | Vector-provided |
| `Fee` | Flash EEPROM Emulation | Vector-provided |
| `IoHwAb` | Input Output Hardware Abstraction | Vector-provided |
| `MemIf` | Memory Abstraction Interface | Vector-provided |
| `WdgIf` | Watchdog Interface | Vector-provided |

</details>


<details>
<summary>Runtime Environment — 1 modules</summary>


| Folder | Long name | Origin |
|---|---|---|

| `Rte` | Runtime Environment | Vector-provided |

</details>


<details>
<summary>Auxiliary Tools and Configuration — 11 modules</summary>


| Folder | Long name | Origin |
|---|---|---|

| `TL100A_QACSuprt` | Static Analysis Support (Quality Assurance for C) | Custom (in-house) |
| `TL101A_CptRteGen` | Component Runtime Environment Generator Support | Vector-provided |
| `TL102A_Davinci` | DaVinci Configuration Support | Vector-provided |
| `TL103A_CplrSuprt` | Coupler Support Tooling | Custom (in-house) |
| `TL104A_GENyFramework` | GENy Network Configuration Framework | Vector-provided |
| `TL105A_Artt` | Architecture Tooling | Custom (in-house) |
| `TL106A_HexView` | Hex File Viewer Tooling | Custom (in-house) |
| `TL109A_SwcSuprt` | Software Component Support Tooling | Custom (in-house) |
| `TL111A_CmnChksTool` | Common Checks Tooling | Custom (in-house) |
| `TL112A_Python` | Python Engineering Utilities | Custom (in-house) |
| `TL113A_MfgSrvSuprt` | Manufacturing Service Support Tooling | Custom (in-house) |

</details>


<details>
<summary>System Integration and Platform — 4 modules</summary>


| Folder | Long name | Origin |
|---|---|---|

| `GM_001A_ChkPt_Impl` | Checkpoint Handling | Custom (in-house) |
| `GM_002A_PartNr_Impl` | Part Number Handling | Custom (in-house) |
| `GM_003A_CustDiagc_Impl` | Customer Diagnostic Handling | Custom (in-house) |
| `GM_G2KCA_EPS_RH850` | Top-Level Controller Project (G2KCA Electric Power Steering on RH850) | Custom (in-house) |

</details>

## Third-party versus in-house code

Vendor deliveries are identified by their copyright and generator banners. Interaction-layer, transport-protocol, network-management, diagnostic-addon, memory-stack, operating-system, state-manager, and calibration-protocol modules are Vector deliveries; digital-input-output, port, serial-interface, flash, watchdog, microcontroller-unit, and controller-area-network drivers are Renesas deliveries (the controller-area-network driver carries the vendor toolchain banner). Everything else — steering functions, vehicle functions, message proxies, peripheral-configuration wrappers, sensing and power components, architecture libraries, manufacturing services, and the top-level build — is in-house logic whose Runtime Environment scaffolding is regenerated with the Vector tools rather than hand-edited. The documentation site marks every module with an origin badge and explains the policy in [Third-party versus in-house code](./docs/src/content/docs/general/vector-vs-custom.md).

## Repository structure

```text
.                          # firmware sources, tool projects, design notes
├── docs/                    # Astro documentation site (project root of the site)
│   ├── astro.config.mjs     # Starlight configuration, address derived automatically
│   ├── package.json         # site dependencies and scripts
│   └── src/content/docs/    # content by AUTOSAR layer (asw, cdd, arch, bsw-*, mcal, ...)
├── LICENSE                  # MIT License
└── README.md                # this file
```

Each component folder typically contains `src/` and `include/` (or equivalent), `autosar/` descriptors, `tools/` Green Hills project files and generation contracts, and design or integration notes (converted into the documentation site). Host-side utilities live in the tooling folders and are not flashed to the controller.

## Installation and build

<details>
<summary>Prerequisites</summary>

- Green Hills MULTI toolchain for the Renesas RH850 target.
- DaVinci Configurator and GENy for configuration and generation.
- Node.js 18 or newer only for previewing or building this documentation (not for the firmware).

</details>

### Firmware

1. Clone the repository.
2. Open the configuration tools, edit the DaVinci or GENy model as needed, and regenerate the affected components (never hand-edit generated files).
3. Open the top-level Green Hills project in `GM_G2KCA_EPS_RH850/tools/` (variant project files for the first controller instance, the second instance, and the combined build) and build the required variant.
4. Flash the resulting image to the Renesas RH850 controller following the hardware setup notes.

### Documentation site

```sh
cd docs
npm install
npm run dev    # local preview
npm run build  # static output in docs/dist/
```

Publishing details (address auto-detection, Pages outline) are in [Deployment](./docs/src/content/docs/general/deployment.md). Automation files are intentionally left untouched.

## Contributing

Contributions are welcome via pull requests. Keep vendor deliveries and generated files untouched; change models and regenerate. Add or update the converted design notes beside the code when behaviour changes so the documentation site stays faithful.

## License

This project is licensed under the MIT License — see the [LICENSE](./LICENSE) file for the full text.
