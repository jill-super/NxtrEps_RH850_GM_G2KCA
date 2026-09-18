---
title: "Motor Control Manager — MotCtrlMgr DataDictionary Tool User Guide"
description: "Converted Design / Integration Document from MotCtrlMgr DataDictionary Tool User Guide.docx (DOCX, 102 KB)."
---

:::note
Converted from `AR300A_MotCtrlMgr_Impl/tools/DataDictionary/MotCtrlMgr DataDictionary Tool User Guide.docx` (Design / Integration Document; original DOCX, about 102 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to AR300A_MotCtrlMgr_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

Purpose

This document provides details on using the DataDictionary.exe tool for generating and testing the MotCtrlMgr component.

Overview

The MotCtrlMgr component is a project specific, highly configurable component.  The majority of the configuration parameters of the component, however, can be derived from analysis of the collection of data dictionaries that exist within any given project.  A tool was created (DataDictionary.exe) to create a file which contains the bulk of the MotCtrlMgr configuration which can subsequently be imported into the AUTOSAR Configuration Tools (Davinci Configurator).  While this tool can primarily be used at a project configuration level, it also is used at a component level in the MotCtrlMgr component.  The usage at a component level serves two primary purposes:

Generation of the majority of the MotCtrlMgr “test” configuration.  

MotCtrlMgr component defines a “test” configuration.  This test configuration is used for several purposes:

To exercise the .bswmd file containing the configuration parameters of MotCtrlMgr (for property correctness and Davinci Configuration compatibility)

To test for the proper/successful generation of the MotCtrlMgr component’s generated configuration files

To generate test files of all generated files of this component used to run static analysis checks on the generated file output, provide the possibility for unit testing of the generated files, and test compilation of the generated files.

Test of the DataDictionary.exe tool output.

Since the DataDictionary.exe tool is used at a project level with files that will change from project to project as needed, it is useful to have a fixed, known set of test files as inputs to the tool to test that the tool is providing the correct output with a known set of inputs.  These input files can also be tailored to test different combinations of input scenarios to try to provide a robust set of test inputs to the tool.

Usage Steps for MotCtrlMgr Component Development

Unzip TestDataManagement.zip file into AR300A_MotCtrlMgr_Impl\tools\DataDictionary directory

This is needed since Telelogic synergy can’t currently recognize some of the folder names that are in this directory.

Update Data Dictionary input files in AR300A_MotCtrlMgr_Impl\tools\DataDictionary directory

This step is required if there are new or changed configurations that need to be tested.  This step would be manually changing the .m files to add or change the configuration or this could also be done with the aid of matlab data dictionary tools.  

Note: if new configurations include new/changed enumerations, these enumerations will need to be manually added into the “TestDataManagement” folder that was unzipped in step 1. And this update will need to be re-zipped for check-in to Synergy.

Note: if the new configurations include new signal mappings, the Mappings.xml file will need to be manually updated in the AR300A_MotCtrlMgr_Impl\tools\DataDictionary directory.

Rerun tool: AR300A_MotCtrlMgr_Impl\tools\DataDictionary\DataDictionary.exe to create new configuration file needed for the next step

Select “Cals” option from initial Data Dictionary tool options:

Select proper tools settings for generation of MotCtrlMgr configuration file.  (note file paths may not be exactly the same as listed below):

Select “Generate” option in tool to create MotCtrlMgr.arxml configuration file.

Import MotCtrlMgr.arxml into MotCtrlMgr component Davinci Configurator project.

Notes:  It is suggested to remove all configuration containers manually from the old configuration before importing the updated configuration.  This allows easier import to ensure that older configuration is fully removed.  Otherwise, much more care needs to be taken during the merge process to fully replace older configuration with newer configuration.  Additionally, the configuration file does not contain runnable sequence number or header file include needs.  These parameters will have to manually be filled out after the import process is complete (or the old configuration settings for these parameters can be kept).

Generate MotCtrlMgr component in Davinci Configurator.

Update Davinci Developer component for any updates needed from configuration changes.

The Davinci Developer component is manually maintained for MotCtrlMgr even though the source code for this component is generated.  This component needs to be setup properly for any signals that flow between the MotCtrl Interrupt and RTE tasks.  Any changes to Data Dictionary input files (new or changed signals) need to be updated in the Davinci Developer component.  As a tip, the component needs to be properly configured to align with the content in AR300A_MotCtrlMgr_Impl\tools\contract\generate\CDD_MotCtrlMgr.c file.

Regenerate RTE contract headers for Davinci Developer component.

This step is done through the Davinci Configurator custom workflow steps that are configured in Davinci Configurator.
