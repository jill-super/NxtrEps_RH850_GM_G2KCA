---
title: "DaVinci Configuration Support — AN-ISC-8-1102 IdentityManager MultipleECUs"
description: "Converted Portable Document (vendor or generated report) from AN-ISC-8-1102_IdentityManager_MultipleECUs.pdf (PDF, 296 KB)."
---

:::note
Converted from `TL102A_Davinci/tools/Developer/Docs/AN-ISC-8-1102_IdentityManager_MultipleECUs.pdf` (Portable Document (vendor or generated report); original PDF, about 296 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL102A_Davinci](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Identity Manager - Multiple ECUs 
Version 1.6 
2010-09-09 
Application Note  AN-ISC-8-1102 
 
 
 
Author(s) Christian Weber, Hannes Futter, Marco Wierer 
Restrictions Customer conf idential - Vector decides 
Abstract Configuration of Multiple EC Us with Vector's AUTOSAR BSW stack. 
 
 
Table of Contents 
 
 1  
Copyright © 2010 - Vector Informatik GmbH 
Contact Information:   www.vector.com  or +49-711-80 670-0 
1.0 Overview ..........................................................................................................................................................1 
1.1 What is the “Identity Manager” about?..........................................................................................................2 
1.1.1 Physical Multiple ECU ................................................................................................................................2 
1.1.2 Multiple Configurations ECU.......................................................................................................................3 
1.1.3 (Virtual Multiple ECU) .................................................................................................................................3 
1.2 Operation principle of Physical Multiple ECUs..............................................................................................3 
2.0 Configuring a Multiple ECU .............................................................................................................................4 
2.1 ECUC creation (without overlay)...................................................................................................................4 
2.1.1 What happens in the ECUC?......................................................................................................................5 
2.2 ECUC Creation (with overlay) .......................................................................................................................6 
2.3 Overlay Control File.......................................................................................................................................7 
2.3.4 Signal overlay .............................................................................................................................................8 
2.3.5 Splitting the direction of PDUs....................................................................................................................9 
2.3.6 Example ......................................................................................................................................................9 
2.4 ECUC creation using DaVinci Project Assistant .........................................................................................11 
2.5 Generating the RTE of a Multiple ECU .......................................................................................................11 
3.0 Initialization of the BSW.................................................................................................................................11 
3.1 Creation of the logic for identity selection ...................................................................................................12 
3.2 Prepare the ECUM configuration ................................................................................................................13 
3.3 Provide an user defined ECUM initialization function .................................................................................13 
3.4 Where do I find the initialization structures? ...............................................................................................15 
3.5 Overview of BSW module initialization........................................................................................................15 
4.0 Diagnostics and Multiple ECU Support..........................................................................................................16 
5.0 Supported use cases ...

--- Page 2 ---
Identity Manager - Multiple ECUs 
 
   
 
 2 
Application Note  AN-ISC-8-1102 
 
1.1 What is the “Identity Manager” about? 
With the Identity Manager ECUs can be configured to run in different scenarios without major changes1 in the 
software. The functionality provided by the Identity Manager is not covered by AUTOSAR explicitly. The use cases 
are:  
• Physical Multiple ECU 
• Multiple Configurations ECU 
• (Virtual Multiple ECU) 
 
This document explains about how to use the Physical Multiple ECU feature. 
1.1.1 Physical Multiple ECU 
This aspect covers an ECU within a specific car line of an OEM. If there are several (>1) almost identical instances 
of this ECU which are connected to the same vehicle network at the same time, they are called “Physical Multiple” 
ECUs or “Multiple ECUs” in short. 
Examples: Door Module (DM), Seat Module (SEAT), Adaptive Damping System (ADS) … 
In this application note, we’ll use the Door Modules with the following instances as an example: 
• Front Right DM_FR 
• Front Left DM_FL 
• Rear Right DM_RR 
• Rear Left DM_RL 
 
The physical control units are derived from a common class with respect to the functionality. Hence, all control unit 
instances derived from this class potentially support the same superset of the functional scope. The actual ECU 
instances will be configured according to the position they will have in the network topology when they are built into 
the car. 
 According to the configuration there may be  
• A different functional scope 
o E.g. different MMI (man machine interface) for ea ch ECU instance: Mirror control or special window 
control for all windows only on the Front Left Door  Module, not on the other modules (application 
dependent, not covered by this application note) 
• Different communication properties of the instances: 
o Own NM message to transmit 
o Own signals to transmit and to receive 
o Own messages to receive and to transmit 
 
The System Description of the OEM contains the instances of such Physical Multiple ECU. For each instance, the 
OEM creates a separate ECU Extract of System Description. This set of ECU Extracts is the configuration input of 
the Physical Multiple ECU. 
                                                           
1 no major changes means: No changes in the application, but there are changes in the initialization sequence of 
the basic software which are not covered by AUTOSAR

--- Page 3 ---
Identity Manager - Multiple ECUs 
 
   
 
 3 
Application Note  AN-ISC-8-1102 
 
1.1.2 Multiple Configurations ECU 
Across multiple car lines of an OEM, the communication behavior considerably differs. However, the Multiple 
Configurations ECU is shared among an OEM’s car lines. Therefore there must be a mechanism for the adaptation 
of this ECU to different environments, i.e. different car lines. 
Note: Multiple Configurations ECUs are currently not supported. 
1.1.3 (Virtual Multiple ECU) 
Virtual Multiple ECUs are control units which are only virtually separate ECUs from a logical point of view but 
residing inside one ECU hardware board. An example for this is a combined radio / gateway control unit. 
Note: Virtual Multiple ECUs are currently not supported. 
1.2 Operation principle of Physical Multiple ECUs 
identity2identity1identity2identity1identity2identity1
Com
PduR
CanIf
Can
Rte
id1 id2 id1 id2 id1 id2
PDU overlay RTE fan out
IPDU IPDU IPDUIPDUIPDU
ISIGs
Superset DataElements Merged DataElements DataElements
DataElements = System Signals
Decision: 
IPDU Æ LPDU
Merged 
ISIGs
identity2identity1identity2identity1identity2identity1
Com
PduR
CanIf
Can
Rte
id1id1 id2id2 id1id1 id2id2 id1id1 id2id2
PDU overlayPDU overlay RTE fan outRTE fan out
IPDU IPDU IPDUIPDUIPDU
ISIGs
Superset DataElements Merged DataElements DataElements
DataElements = System Signals
Decision: 
IPDU Æ LPDU
Merged 
ISIGs
 
Figure 1 – Overview of the Multiple ECU feature, Tx path shown only. 
 
In Figure 1, you see an example of the operation p rinciple of a Multiple ECU. Here, the Tx path is shown. The 
leftmost column displays what happens if you have to configure a Multiple ECU sending out different CAN 
messages and cannot use any kind of optimization because the signals for each identity are different. For each set 
of signals which have to be sent, a separate PDU is created and mapped to a corresponding CAN frame which is 
actually sent out. This situation also applies if you have a PDU which is transmitted in one identity and received via 
a different identity. Then, despite having the same signals on application level, two PDUs are created, one for 
transmission in identity1, a second PDU for reception in identity2. 
However, if you have semantically equivalent signals sent in different CAN messages, there is room for 
optimization. This is shown in the middle column. Semantically equivalent signals can be merged into one common 
PDU, the transmission is done in different CAN frames, but their content is eq

[… 12 further page(s) not extracted …]
