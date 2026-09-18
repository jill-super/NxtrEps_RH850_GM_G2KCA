---
title: "GENy Network Configuration Framework — WELCOME to CANbedded"
description: "Converted Portable Document (vendor or generated report) from WELCOME to CANbedded.pdf (PDF, 167 KB)."
---

:::note
Converted from `TL104A_GENyFramework/tools/GENy 1.4/WELCOME to CANbedded.pdf` (Portable Document (vendor or generated report); original PDF, about 167 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL104A_GENyFramework](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
1© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
V2.0 2006-09-13
Welcome to CANbedded
Implement Vector’s Delivery.
Within few steps from 
<delivery>.exe to <application>.hex 
These slide show you how to use a CANbedded software component delivery beginning with the 
installation until a first successful test run.

--- Page 2 ---
2© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
2
© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
Slide: 
Agenda
Summary
Step by Step
Delivery
Components and Project Folders
Introduction>

--- Page 3 ---
3© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
3
© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
Slide: 
Application
Introduction
CAN Controller
Transceiver
CAN Bus
Network
Management
Transport Protocol
Communication
Control
Layer
Universal
Measure-
ment
And 
Calibration
Protocol
CAN Driver
Interaction 
Layer
Diagnostics
Layer
Configuration 
Tool

CANbedded Software Components GENy, CANgen
CAN Controller
Transceiver
Your Application
The illustration shows the layer model of the CANbedded components, their basic functions and 
connections. CANbedded consists of a set of source code components (CANbedded Software 
Components) you have to include in your application. The sort of components depends on your delivery.
The Configuration Tool is the connection between the components and your project specific needs. It 
generates files you also have to include in your application.
Configuration Tool
for parameters and configuration of all components
more see Online Help
Communication Control Layer
Software component integration and hardware abstraction. 
CAN Driver
Hardware specific CAN controller characteristics and provision of a standardized application interface
Interaction Layer
with signal interface
Network Management
to control the CAN ECU
Transport Protocol
for data exchange of more than 8 data bytes
Universal Measeurement and Calibration Protocol
Measurement and calibration of the ECU via different bus systems. 
Diagnostics Layer
according to Keyword Protocol 2000 / UDS

--- Page 4 ---
4© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
4
© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
Slide: 
Application
Introduction
CAN Controller
Transceiver
CAN Bus
Configuration 
Tool

CANbedded Software Components GENy, CANgen
CAN Controller
Transceiver
Your Application
BMW
VW/AUDI
DC
 GM
Renault
Porsche
...and others
OEM? 
Controller?
Derivative?
Compiler? 
Dependent on the OEM the delivery and its content can differ. 
Some components do a similar job but have a different name and a different API, e.g. the Interaction 
Layer is different for DaimlerChrysler, BMW and other OEMs.

--- Page 5 ---
5© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
5
© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
Slide: 
Introduction
OEM X
This Delivery is:
Tailored for:
 Controller
 Derivative
 Compiler
Can be used for*:
 Projects for one vehicle manufacturer
 Can be used for multiple projects or car lines for this vehicle 
manufacturer
*right of usage can differ, for specific information refer to the quotation
The delivery is tailored according the questionnaire you filled-out. So the delivery contains all components 
you need tested for you controller/derivative/compiler. 
You can use the delivery not only for one project but for all other projects for this vehicle manufacturer  for 
different car lines.

--- Page 6 ---
6© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
6
© 2006. Vector Informatik GmbH. All rights reserved. Any distribution or copying is subject to prior written approval by Vector.
Slide: 
Introduction
Basic concept is almost the same for all OEM
 C code CANbedded Components
 Configuration Tool
OEM-specific differences in
 Component combinations
 Components
 API
CANbedded component are source code components in C. You can tailor the huge amount of 
functionality of each component by using the configuration tool.

[… 17 further page(s) not extracted …]
