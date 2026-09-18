---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — AN-ISC-8-1074 Possible Loss Of Wakeup Message"
description: "Converted Portable Document (vendor or generated report) from AN-ISC-8-1074_Possible_Loss_Of_Wakeup_Message.pdf (PDF, 167 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/AN-ISC-8-1074_Possible_Loss_Of_Wakeup_Message.pdf` (Portable Document (vendor or generated report); original PDF, about 167 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Possible Loss Of Wakeup Message 
Version 1.0 
2008-02-26 
Application Note  AN-ISC-8-1074 
 
 
 
Author(s) Ralf Fritz 
Restrictions Customer confidential - GM only 
Abstract This application note describes the possibility of loosing a wake-up request in a GMLAN 
Single Wire environment and the possibility to minimize the possibility of occurrence. For 
GM customer only.  
 
 
 
Table of Contents 
 
 1  
Copyright © 2008 - Vector CANtech, Inc. 
Contact Information:   www.vector-informatik.com   or ++49-711-80 670-0 
1.0 Overview ..........................................................................................................................................................1 
2.0 Initialization Of CAN controller.........................................................................................................................2 
2.1 During Startup ...............................................................................................................................................2 
2.2 Switching Baud Rate.....................................................................................................................................2 
2.3 Bus-Off Event ................................................................................................................................................2 
2.4 Before Sleep Mode........................................................................................................................................2 
3.0 Switching Transceiver to Sleep mode .............................................................................................................3 
3.1 Check For Messages ....................................................................................................................................3 
3.2 Use Transceiver Wake Pin............................................................................................................................4 
4.0 Switching CAN cell into sleep mode................................................................................................................4 
5.0 Polling versus Interrupt ....................................................................................................................................5 
6.0 Additional Resources.......................................................................................................................................5 
7.0 Contacts...........................................................................................................................................................5 
 
  
1.0 Overview 
GMLAN uses special messages, so called High Voltage Wake-Up Messages (HVWU), to wake-up sleeping 
modules on the Single Wire CAN bus. Under certain conditions it is possible that these messages are discarded 
and do not cause a wake-up of the ECU like expected. This document describes these possible situations and 
methods of reducing the time period where a HVWU message can be lost. 
 
Note: This document applies to the Single-Wire CAN bus only, because of its special physical 
implementation. The wake-up behavior on a non Single-Wire CAN bus will differ since every 
receive message will cause a CAN cell wake-up if the CAN cell supports sleep wake-up. 
 
Note: The occurrence of this behavior depends on t he hardware platform, the compiler, hardware layout 
and many more parameters. Because of this, this application note cannot specify specific time 
durations. 
 
Note: Any code samples are only examples of implementation proposals. Because these 
functions are meant for demonstration purposes only, Vector’s liability shall be expressly 
excluded in cases of ordinary negligence to the extent admissible by law or statute.

--- Page 2 ---
Possible Loss Of Wakeup Message 
 
   
 
 2 
Application Note  AN-ISC-8-1074 
 
2.0 Initialization Of CAN controller 
The GMLAN handler will initialize the CAN controller at different times during runtime. The CAN controller is 
initialized in the following situations: 
• During startup of the handler 
• Switching baud-rate during flash programming 
• After a Bus-Off event 
• Before the handler tries to enter the sleep mode 
• In case the High Voltage Wake-Up message cannot be sent onto CAN bus 
 
If the CAN cell is initialized, all currently received and not handled receive-messages will be discarded. This means 
that also pending HVWU messages will be discarded and can cause the module not to switch back to 
Communication Enable or Communication Active state as expected. 
The chapters below include a more detailed description of these situations. 
2.1 During Startup 
Vectors GMLAN handler can be configured to initialize the CAN controller during the call of IlInitPowerOn(). 
During this time it is not likely to lose any HVWU message, because this function is only called if the system 
performs a cold start. Please see [1] and [2] for further information when this function needs to be called by the 
application. 
After the call of IlInitPowerOn(), the handler will enter at least the Communication Enable state for 8 seconds, 
this means bus activity can be detected and a lost HVWU frame will not cause the module not to participate in the 
CAN communication. 
2.2 Switching Baud Rate 
To be able to switch the current baud rate to a higher or lower one, the CAN controller needs to be re-initialized 
with the different baud rate settings. During this period, the handler is in the Normal Communication Halted state. 
This means that the module is already awake during this time and will stay awake for at least 4 more seconds. This 
means that if a HVWU frame is lost at this point in time, the handler will still be able to participate in an ongoing 
CAN communication. 
2.3 Bus-Off Event 
To start the CAN cell bus-off recovery sequence and to remove any pending transmit request from the CAN 
controller, the GMLAN handler is calling two CAN Driver interface functions. These functions are 
CanResetBusOffStart() and CanResetBusOffEnd(). One of these functions is usually mapped to a function 
which will re-initialize the CAN cell. In such situations, the handler shall ignore any receive messages, which also 
includes HVWU messages. 
Note: The implementation of the functions CanResetBusOffStart() and CanResetBusOffEnd() 
are depending on the hardware. Please check the related hardware manual [3] for more 
information. 
2.4 Before Sleep Mode  
Vectors GMLAN handler will call CanResetBusSleep() before the CAN controller is put into sleep mode to 
remove any pending transmit request from the CAN hardware.

--- Page 3 ---
Possible Loss Of Wakeup Message 
 
   
 
 3 
Application Note  AN-ISC-8-1074 
 
Note: The implementation of the function CanResetBusSleep() is depending on the hardware. Please 
check the related hardware manual [3] for more information. 
This function is usually mapped to a function which will initialize the CAN controller. The call of this function 
happens when the remainder of the Communication Enable timer reaches a value of 100 ms + 2 times the task 
cycle of the network management task (IlNwmTask()) and the application accepts the sleep request 
(ApplNwmSleepConfirmation returns NmSleepOk). 
Note: 100 ms is the default provided by the generation tool. This value can be calibrated later to a 
different value. Please check your usage. 
If now the delay between the related I-VNMF to the discarded HVWU message is longer then the time set-up, the 
transceivers will be switched into sleep mode before the I-VNMF is sent to the CAN bus. This will prevent the CAN 
controller from receiving the message and the system will stay in sleep mode. This behavior cannot be changed by 
a software or hardware change. 
3.0 Switching Transceiver to Sleep mode 
On a Single Wire bus it is quite normal, that a single ECU will enter the CAN sleep mode and other modules 
continue to communicate on the same physical CAN bus. To be able to do this, the transceivers of these modules 
are switched into sleep mode before the CAN cell is put into sleep mode. This will prevent any normal message 
communication from being passed to the controller and allows it to enter the CAN sleep mode. Vectors GMLAN 
handler does not check, if there is an ongoing CAN message reception while it requests the application to switch 
the transceiver into sleep mode by calling the function ApplTrcvrSleepMode(). If a normal receive message is 
interrupted, this causes no functional issue, since the module already decided that normal message reception must 
be ignored. 
If during this time a HVWU message is received, the message is most likely lost. This is because only parts of the 
physical CAN message are received by the CAN controller. The transceiver will act like a filter after it is put into 
sleep mode and will not pass all bits of the message to the CAN controller (Please check your transceiver manual 
for the exact behavior of your transce
