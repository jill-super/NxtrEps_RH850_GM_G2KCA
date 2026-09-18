---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — Startup GM SLP2"
description: "Converted Portable Document (vendor or generated report) from Startup_GM_SLP2.pdf (PDF, 7172 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/Startup_GM_SLP2.pdf` (Portable Document (vendor or generated report); original PDF, about 7172 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
UserManual
StartupwithGM SLP2
AStepbyStepIntroduction
Version3.0.0forMICROSAR 4Release12
English

--- Page 2 ---
©VectorInformatikGmbH Version3.0.0forRelease12 -2-
Content
1AboutThisManual 10
1.1HistoryInformation 10
1.2FindingInformationQuickly 10
1.3Conventions 10
1.4Certification 11
1.5Warranty 11
1.6Support 12
1.7RegisteredTrademarks 12
1.8ErrataSheetofHardwareManufacturers 13
1.9ExampleCode 13
2Introduction 14
2.1WhatDoYouLearnfromThisManual 14
2.2AnOverallView 14
2.3MICROSAR-Vector'sAUTOSAR Solution 15
2.4AUTOSARLayerModelGMSLP2 16
2.5ConfigurationWorkflowGMSLP2 17
ISTEPbySTEP 18
1STEP1SetupYourProject 19
1.1SituationafterInstallationGuide 19
1.2SetupProjectviaDaVinciConfiguratorPro 19
1.3ResultProjectFolder-resultoftheprojectset-up 21
1.4StartMenu-ResultoftheProjectSet-up 23
1.5DaVinciConfiguratorProProject 23
2STEP2DefineProjectSettings 24
2.1AddInputFiles 24
2.1.1AddSystemDescriptionFiles 25
2.1.2AddDiagnosticDataFiles 27
2.1.3AddStandardConfigurationFiles 28
2.1.4UpdateConfiguration 28
2.2DefineCustomWorkflowStepsandExternalGenerationSteps 30
UserManualStartupwithGMSLP2

--- Page 3 ---
2.2.1CustomWorkflowSteps 30
2.2.2ExternalGenerationSteps 31
2.3ActivateYourBSWModules 32
2.4AddECUCFileReferences 33
3STEP3Validation 34
3.1StartSolveAllMechanism 34
3.2LiveValidation-SolvingActions 34
4STEP4StartBSWConfiguration 36
4.1StartConfigurationwithConfigurationEditors 36
4.2BaseServices 36
4.3Communication 37
4.4Diagnostics 38
4.5I/O 40
4.6Memory 40
4.7ModeManagementEditors 41
4.8NetworkManagement 46
4.9RuntimeSystem 47
4.9.4CreateTasks 49
4.10GoonwithBasicEditor 49
4.11StartSolvingActions 49
4.12StartOn-demandValidation 49
4.13BSW Configurationfinished 51
5STEP5DesignSoftwareComponents 52
5.1SwitchtoDaVinciDeveloper 52
5.2DesignSoftwareComponents 52
6STEP6Mappings 53
6.1PerformDataMappingwithinDaVinciDeveloperorDaVinciConfigurator? 53
6.2DataMappingwithintheDaVinciDeveloper 53
6.2.3DaVinciDeveloper-Saveandclose 56
6.3Switch(back)toDaVinciConfigurator 56
UserManualStartupwithGMSLP2
©VectorInformatikGmbH Version3.0.0forRelease12 -3-

--- Page 4 ---
©VectorInformatikGmbH Version3.0.0forRelease12 -4-
6.4SynchronizeSystemDescription 56
6.5AddComponentConnection 56
6.6Service Mapping 57
6.7AddDataMapping 58
6.8AddMemoryMapping 60
6.9AddTaskMapping 60
7STEP7CodeGeneration 62
7.1StartCustomWorkflowSteps 62
7.2StartCodeGeneration 62
7.3GenerationProcessfinished! 64
8STEP8AddRunnableCode 65
8.1ComponentTemplate 65
8.2ImplementCode 66
9STEP9Compile andLinkYourProject 67
9.1Finishyourprojectwithcompilingandlinking 67
9.2Congratulations,that’sit! 67
IIConcept 68
1General Overview 69
1.1SoftwareComponent 71
1.1.1Atomiccomponents 71
1.1.2Compositions 71
1.2Runnables 71
1.3Ports 72
1.3.1ApplicationPortInterfaces 72
1.3.2ServicePortInterfaces 72
1.4DataElementTypes 72
1.5Connections 73
1.6RTE 73
1.7BSW–BasicSoftwareModules 73
1.8Software,ToolsandFiles 73
UserManualStartupwithGMSLP2

--- Page 5 ---
1.9StructureoftheSIPFolder 75
2Set-UpNewProject 78
2.1DaVinciConfigurator 78
3DefineProjectSettings 83
3.1Inputfiles 83
3.1.1SystemDescriptionFiles 83
3.1.5DiagnosticDataFiles 84
3.1.8StandardConfigurationFiles 84
3.2CustomWorkflowSteps/ExternalGenerationSteps 84
3.3ActivateBSW 85
4Validation 86
4.1ValidationConcept 86
5BSW ConfigurationwithConfigurationEditors 87
5.1DaVinciConfiguratorProEditors 87
6SoftwareComponent(SWC)Design 88
6.1DataExchangebetweenDaVinciDeveloperandDaVinciConfiguratorPro 88
6.2AboutApplicationComponents,Ports,Connections,RunnablesandMore… 88
6.3ApplicationComponents 89
6.4Ports,PortInitValuesandDataElements 98
6.5ConfigureServicePortswithinyourApplicationComponents 103
6.6DefineyourRunnables 104
6.7TriggersfortheRunnables 105
6.8PortAccessoftheRunnables 107
7Mappings 109
7.1DataMapping 109
7.2TaskMapping 110
7.2.1InformationaboutInteractionbetweenRunnable,Re-entranceandTaskMapping 111
7.3MemoryMapping 113
7.4Service Mapping 114
8Generation 116
UserManualStartupwithGMSLP2
©VectorInformatikGmbH Version3.0.0forRelease12 -5-

--- Page 6 ---
©VectorInformatikGmbH Version3.0.0forRelease12 -6-
8.1MICROSAR RteGen 116
9RunnableCode 117
10Compile andLink 119
10.0.1Usingyour"real"hardware 119
IIIAdditionalInformation 120
1UpdateInputFiles 121
1.1SystemDescriptionFiles 121
1.2DiagnosticDataFiles 121
2UpdateProjectSettings 122
3SupportRequestvia DaVinciConfiguratorPro 123
3.1Result 123
4Multiple User Concept 125
4.1General 125
4.2SplitFilesforSoftwareComponentandECUProjectConfiguration 126
4.3ConfigureSoftwareComponentPrototype 128
4.4ConfigureECUproject 128
4.5SplitFilesinDaVinciDeveloper 129
4.6SplitFilesforBSWConfiguration 129
5ConfigurationUpdate 131
5.1Releasex-1toReleasex(necessarystepsforanyupdate) 131
5.2Release8toRelease9 133
5.3Release7toRelease8 133
6UpdateDaVinciTools 135
6.1DaVinciConfiguratorPro 135
6.2DaVinciDeveloper 135
7Non-Volatile Memory Block 136
7.1ConfigureanduseNon-VolatileMemoryBlock 136
7.2PortAccessofyourRunnables 139
7.3MemoryMappinginDaVinciConfiguratorPro 139
7.4ValidatetheRTE 141
UserManualStartupwithGMSLP2

[… 222 further page(s) not extracted …]
