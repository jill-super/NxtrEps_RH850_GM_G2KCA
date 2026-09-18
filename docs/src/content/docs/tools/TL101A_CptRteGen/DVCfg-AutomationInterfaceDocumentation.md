---
title: "Component Runtime Environment Generator Support — DVCfg AutomationInterfaceDocumentation"
description: "Converted Portable Document (vendor or generated report) from DVCfg_AutomationInterfaceDocumentation.pdf (PDF, 2626 KB)."
---

:::note
Converted from `TL101A_CptRteGen/tools/Sip/DaVinciConfigurator/Core/AutomationInterface/_doc/DVCfg_AutomationInterfaceDocumentation.pdf` (Portable Document (vendor or generated report); original PDF, about 2626 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL101A_CptRteGen](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
DaVinci Conﬁgurator AutomationInterface
Development Documentation of the AutomationInterface (AI)
DaVinci Conﬁgurator Team
December 9, 2016
© 2016
Vector Informatik GmbH
Ingersheimerstr. 24
70499 Stuttgart

--- Page 2 ---
Contents
1 Introduction 8
1.1 General . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 8
1.2 Facts . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 8
2 Getting started with Script Development 9
2.1 General . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
2.2 Automation Script Development Types . . . . . . . . . . . . . . . . . . . . . . . . 9
2.3 Script File . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
2.4 Script Project . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 11
2.4.1 Script Project Development . . . . . . . . . . . . . . . . . . . . . . . . . . 13
2.4.2 Java JDK Setup . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 13
2.4.3 IntelliJ IDEA Setup . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14
2.4.4 Gradle Setup . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14
3 AutomationInterface Architecture 15
3.1 Components . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
3.2 Languages . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
3.2.1 Why Groovy . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
3.3 Script Structure . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
3.3.1 Scripts . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
3.3.2 Script Tasks . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
3.3.3 Script Locations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
3.4 Script loading . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
3.4.1 Internal Script Reload Behavior . . . . . . . . . . . . . . . . . . . . . . . . 18
3.5 Script editing . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 19
3.6 Licensing . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 19
3.7 Script Coding Conventions and Constraints . . . . . . . . . . . . . . . . . . . . . 19
3.7.1 Usage of static ﬁelds . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 20
3.7.2 Usage of Outer Closure Scope Variables . . . . . . . . . . . . . . . . . . . 21
3.7.3 States over script task execution . . . . . . . . . . . . . . . . . . . . . . . 21
3.7.4 Usage of Threads . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
3.7.5 Usage of DaVinci Conﬁgurator private Classes Methods or Fields . . . . . 21
4 AutomationInterface API Reference 22
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
4.2 Script Creation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
4.2.1 Script Task Creation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
4.2.1.1 Script Creation with IDE Code Completion Support . . . . . . . 24
4.2.1.2 Script Task isExecutableIf . . . . . . . . . . . . . . . . . . . . . . 25
4.2.2 Description and Help . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
4.3 Script Task Types . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27
4.3.1 Available Types . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27
4.3.1.1 Application Types . . . . . . . . . . . . . . . . . . . . . . . . . . 27
4.3.1.2 Project Types . . . . . . . . . . . . . . . . . . . . . . . . . . . . 28
4.3.1.3 UI Types . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
4.3.1.4 Generation Types . . . . . . . . . . . . . . . . . . . . . . . . . . 29
4.4 Script Task Execution . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
4.4.1 Execution Context . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
© 2016, Vector Informatik GmbH 2 of 207

--- Page 3 ---
Contents
4.4.1.1 Code Block Arguments . . . . . . . . . . . . . . . . . . . . . . . 32
4.4.2 Task Execution Sequence . . . . . . . . . . . . . . . . . . . . . . . . . . . 32
4.4.3 Script Path API during Execution . . . . . . . . . . . . . . . . . . . . . . 33
4.4.3.1 Path Resolution by Parent Folder . . . . . . . . . . . . . . . . . 34
4.4.3.2 Path Resolution . . . . . . . . . . . . . . . . . . . . . . . . . . . 34
4.4.3.3 Script Folder Path Resolution . . . . . . . . . . . . . . . . . . . 35
4.4.3.4 Project Folder Path Resolution . . . . . . . . . . . . . . . . . . . 35
4.4.3.5 SIP Folder Path Resolution . . . . . . . . . . . . . . . . . . . . . 36
4.4.3.6 Temp Folder Path Resolution . . . . . . . . . . . . . . . . . . . . 36
4.4.3.7 Other Project and Application Paths . . . . . . . . . . . . . . . 37
4.4.4 Script logging API . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 37
4.4.5 User Interactions and Inputs . . . . . . . . . . . . . . . . . . . . . . . . . 38
4.4.5.1 UserInteraction . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
4.4.6 Script Error Handling . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 40
4.4.6.1 Script Exceptions . . . . . . . . . . . . . . . . . . . . . . . . . . 40
4.4.6.2 Script Task Abortion by Exception . . . . . . . . . . . . . . . . . 40
4.4.6.3 Unhandled Exceptions from Tasks . . . . . . . . . . . . . . . . . 41
4.4.7 User deﬁned Classes and Methods . . . . . . . . . . . . . . . . . . . . . . 42
4.4.8 Usage of Automation API in own deﬁned Classes and Methods . . . . . . 43
4.4.8.1 Access the Automation API like the Script code{} Block . . . . 43
4.4.8.2 Access the Project API of the current active Project . . . . . . . 43
4.4.9 User deﬁned Script Task Arguments in Commandline . . . . . . . . . . . 44
4.4.9.1 Call Script Task with Task Arguments . . . . . . . . . . . . . . . 46
4.4.10 Stateful Script Tasks . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 47
4.5 Project Handling . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
4.5.1 Projects . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
4.5.2 Accessing the active Project . . . . . . . . . . . . . . . . . . . . . . . . . . 49
4.5.3 Creating a new Project . . . . . . . . . . . . . . . . . . . . . . . . . . . . 51
4.5.3.1 Mandatory Settings . . . . . . . . . . . . . . . . . . . . . . . . . 52
4.5.3.2 General Settings . . . . . . . . . . . . . . . . . . . . . . . . . . . 52
4.5.3.3 Target Settings . . . . . . . . . . . . . . . . . . . . . . . . . . . . 53
4.5.3.4 Post Build Settings . . . . . . . . . . . . . . . . . . . . . . . . . 54
4.5.3.5 Folders Settings . . . . . . . . . . . . . . . . . . . . . . . . . . . 54
4.5.3.6 DaVinci Developer Settings . . . . . . . . . . . . . . . . . . . . . 56
4.5.4 Opening an existing Project . . . . . . . . . . . . . . . . . . . . . . . . . . 57
4.5.4.1 Parameterized Project Load . . . . . . . . . . . . . . . . . . . . 58
4.5.4.2 Open Project Details . . . . . . . . . . . . . . . . . . . . . . . . 59
4.5.5 Saving a Project . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 59
4.5.6 Opening AUTOSAR Files as Project . . . . . . . . . . . . . . . . . . . . . 60
4.6 Model . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 62
4.6.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 62
4.6.2 Getting Started . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 62
4.6.2.1 Read the ActiveEcuc . . . . . . . . . . . . . . . . . . . . . . . . 62
4.6.2.2 Write the ActiveEcuc . . . . . . . . . . . . . . . . . . . . . . . . 65
4.6.2.3 Read the SystemDescription . . . . . . . . . . . . . . . . . . . . 67
4.6.2.4 Write the SystemDescription . . . . . . . . . . . . . . . . . . . . 68
4.6.3 BswmdModel in AutomationInterface . . . . . . . . . . . . . . . . . . . . 70
4.6.3.1 BswmdModel Package and Class Names . . . . . . . . . . . . . . 70
4.6.3

--- Page 4 ---
Contents
4.6.3.5 BswmdModel DefRefs . . . . . . . . . . . . . . . . . . . . . . . . 72
4.6.3.6 Switching from Domain Models to BswmdModel . . . . . . . . . 73
4.6.4 MDF Model in AutomationInterface . . . . . . . . . . . . . . . . . . . . . 73
4.6.4.1 Reading the MDF Model . . . . . . . . . . . . . . . . . . . . . . 74
4.6.4.2 Writing the MDF Model . . . . . . . . . . . . . . . . . . . . . . 76
4.6.4.3 Simple Property Changes . . . . . . . . . . . . . . . . . . . . . . 77
4.6.4.4 Creating single Child Members (0:1) . . . . . . . . . . . . . . . . 77
4.6.4.5 Creating and adding Child List Members (0:*) . . . . . . . . . . 78
4.6.4.6 Updating existing Elements . . . . . . . . . . . . . . . . . . . . . 80
4.6.4.7 Deleting Model Objects . . . . . . . . . . . . . . . . . . . . . . . 81
4.6.4.8 Duplicating Model Objec

[… 201 further page(s) not extracted …]
