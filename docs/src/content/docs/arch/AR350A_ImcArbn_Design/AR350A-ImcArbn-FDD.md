---
title: "Internal Motor Control Arbitration — AR350A ImcArbn FDD"
description: "Converted Design / Integration Document from AR350A_ImcArbn_FDD.docx (DOCX, 9282 KB)."
---

:::note
Converted from `AR350A_ImcArbn_Design/Design/AR350A_ImcArbn_FDD.docx` (Design / Integration Document; original DOCX, about 9282 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to AR350A_ImcArbn_Design](./)

*Conversion method: automatic text extraction from the Word document.*

Inter-Micro Communication Arbitration

FDD #AR350A

.

High Level Description

The Inter-Micro Communication (IMC) Arbitration prepares data for transmission to a complimentary ECU through two redundant communication paths.  On the receive side, the Arbitration reads data from the primary source and determines the data validity.  A validity fault on primary source prompts the IMC Arbitration component to evaluate the same signal from the secondary source.  Faulty signals from the primary source will be replaced with signals from the secondary source, as long as they are valid.  If both data sources are invalid the IMC Arbitration outputs the signal status based on never received, missing and invalid conditions.

Function I/O

Input Description

Inputs for this component are provided by IMC signal configurations that are defined based on program requirements. Refer Section 5.23 for more details.

Output Description

Refer Data Dictionary for details.

Sub-Function Data Flow

Imc Arbitration Transmit side data flow

Imc Arbitration Receive side data flow

Rolling Counter Handling

General Description:

Rolling counters are used to ascertain sequence of every Signal Group reception via IMC channels.

Rolling counters are embedded in the start byte with length of 5 bits in every frame on both channels. This sequence is generated for each Rate Group separately with range of 0 to 31.  Roll over will happen once the Rolling counter reaches 31. 

All Signal Groups defined under a Rate Group will have same value of Rolling Counter in a given cycle of transmission. 

On the receiving side Rolling counter evaluation poses following challenges:

Underlying protocols of Primary and Secondary sources have different data handling methods and hence, at any instant, the data received from any of these channels will be different.

Underlying protocols of Primary and Secondary sources have different handling in Software which in turn impacts reception hence, at any instant, the data processed will be different.

Corruption in the channel level causes loss in messages and hence loss in synchronization.

Rolling counter algorithm addresses all these challenges and determines a robust approach to handle these.

Rolling Counter Algorithm description:

The following are addressed by this algorithm:

Validation of the data sequence of Signal Group based on Rolling counter from Primary and Secondary sources

Data Sequence validation from IMC channels which are of same or different characteristics.

Resynchronization of the Rolling counter check during data corruption in the channels.

Resynchronization of the Rolling counter check when the Rolling counter reference changes ( Roll-over cases)

Indicates if a Rolling counter fault needs to be reported.

Further details are indicated in the following generic flowchart.

Variables used in the flowchart are,

DataValid: This is a flag which indicates if valid Data is received from the Communication channel.

GoodDataSource:This indicates which Communication channel ( Primary or Secondary) has Valid data

MessageSkipCounter: This is a counter which indicates the number of missed messages in the form of No data or invalid data.

RollCounterError: Indicates if a rolling counter fault need to be reported

CounterThreshold:This is a value related to the typical amount of latency in data transmission in the communication channel.

ChannelSwitchDelay:This is a value related to the dynamics of the redundant communication channels. This indicates the typical delay in a message reception between the communication channels at any instant.

PreviousRolling Counter:This is the value of the rolling counter of the previously stored valid message. 

RollCounterResyncCounterPrimary: This is a counter which indicates the number of times data is missed because of only Rolling Counter issue on primary channel. 

RollCounterResyncCounterSecondary: This is a counter which indicates the number of times data is missed because of only Rolling Counter issue on Secondary channel.

ResyncThreshold: This is the number of consecutive Rolling counter issues after which it could be assumed that either of the MCUs have lot synchronization of rolling counter, and hence a resync has to happen.

RollCounterPrimaryResync – Previous rolling counter value received during resync period on Primary channel

RollCounterSecondaryResync – Previous rolling counter value received during resync period on Secondary channel

PrimaryResyncActive –  Indicates whether Resync is active on Primary channel

SecondaryResyncActive –  Indicates whether Resync is active on Secondary channel. 

In short, the Rolling counter algorithm behaves as follows, 

Data is considered valid in the following cases, 

For consecutive messages from same Comm. channel, if the new Rolling counter falls within the range 

(ExpectedRollCntrValue  – LowerLimit)  <= CurrentRolling Counter <= (ExpectedRollCntrValue  + CounterThreshold)

Where ExpectedRollCntrValue = PreviousRolling Counter + MessageSkipCounter + 1, 

LowerLimit = CounterThreshold if it is lesser than MessageSkipCounter else, LowerLimit = MessageSkipCounter

For consecutive messages from different Comm. channel, if the new RL falls within a range specified by

(ExpectedRollCntrValue – LowerLimit)  <= CurrentRolling Counter <= (ExpectedRollCntrValue  + (CounterThreshold + ChannelSwitchDelay))

Where ExpectedRollCntrValue = PreviousRolling Counter + MessageSkipCounter + 1,

LowerLimit = CounterThreshold + ChannelSwitchDelay if it is lesser than MessageSkipCounter else, LowerLimit = MessageSkipCounter

Rolling Counter error will not be set in the following cases,

For consecutive messages from same Comm. channel, if the new Rolling counter falls within the range 

(ExpectedRollCntrValue  – CounterThreshold)  <= CurrentRolling Counter <= (ExpectedRollCntrValue  + CounterThreshold)

Where ExpectedRollCntrValue = PreviousRolling Counter + MessageSkipCounter + 1

For consecutive messages from different Comm. channel, if the new RL falls within a range specified by

(ExpectedRollCntrValue – (CounterThreshold + ChannelSwitchDelay))  <= CurrentRolling Counter <= (ExpectedRollCntrValue  + (CounterThreshold + ChannelSwitchDelay))

Where ExpectedRollCntrValue = PreviousRolling Counter + MessageSkipCounter + 1

On every skip of message (includes missing, CRC error and No data) MessageSkipCounter is incremented. The next rolling counter is expected to have a value bigger than the previous rolling counter value by this counter amount. Any active resynchronization will be cleared as next rolling counter value will not be just next to currently stored value. 

If consecutive ResyncThreshold amount of rolling counter issues occur (cases when old or invalid CurrentRollingCounter detected) in a channel, then it is assumed that either of the MCUs have lot synchronization of rolling counter on the particular channel, and hence a resynchronization is triggered.

Following pseudo code ex

Input Name | Description
<Signal1>…<Signal#> | All RTE signals coming from any periodic that are required to be read by IMC Arbitration scheduled runnables.  The list of signals can change from program to program based on program dataflow requirements.
ImcArbnInit1 | ImcArbnInit1
Function scope | Global, Init function
Description | Initialized Signal Group and Signal related buffers. Gets start time of the component and saves it in a PIM
Parameters | None
Return value | None
Affected static and global variables | Reads / Writes  to following variables  in functions
Affected static and global variables | SigGroupNeverRxd
Affected static and global variables | PrimSrcRollgCntrResync
Affected static and global variables | SecdrySrcRollgCntrResync
Affected static and global variables | RxdSigDataExtdSts
Affected static and global variables | RxdSigDataSrc
Affected static and global variables | SigGroupDataSrc
Affected inter-runnable variable | None
Exclusive area access | None
Configuration access | Accesses following configuration data
Configuration access | IMCARBN_TOTALNROFSIG_CNT_U16
Configuration access | IMCARBN_TOTALNROFSIGGROUP_CNT_U08
Calibration data access | None
Called local functions | None
External Interface call | None
Called by | Called by following functions
Called by | Init Task
ImcArbnTx | ImcArbnTx
Function scope | Local
Description | 1) This function collects signal data for all Signal Groups configured in the ImcArbn_SigGroupConfig_Rec for given Rate Group and packs each signal to the specified start bit in each Signal Group as defined in the configuration.
2) A Pattern Identification flag, Rolling Counter, Signal Group ID, CRC, Compliment Pattern ID and Compliment Rolling Counter are added for each Signal Group.
3) The resulting signal group is put into a transmit data buffer for for the GetTxSigGroup or GetTxRateGroup client calls to access.
Parameters | Requires following parameters
Parameters | RateGroup - Rate Group Id provided by IMC Arbitration Configuration
Type: uint8
Range: 
IMCARBN_RATEGROUPID2MILLISEC_CNT_U08     (0U)
IMCARBN_RATEGROUPID10MILLISEC_CNT_U08    (1U)
IMCARBN_RATEGROUPID100MILLISEC_CNT_U08   (2U)
All other values are invalid
Return value | None
Affected static and global variables | Writes to following variables
Affected static and global variables | TxBuf
Affected static and global variables | RollgCntr
Affected inter-runnable variable | None
Exclusive area access | Needed to update Transmit data buffer
Configuration access | Accesses following configuration data
Configuration access | SIGGROUPCONFIG_REC
Configuration access | RATEGROUPOFFS_CNT_U08
Configuration access | NRSIGGROUPINRATEGROUP_CNT_U08
Calibration data access | None
