[**Document History 2**](#document-history)

[**Introduction 2**](#introduction)

[**Abbreviations 2**](#abbreviations)

[**Referenced documents 2**](#referenced-documents)

[**Firmware Requirements for core functions
4**](#firmware-requirements-for-core-functions)

> [REQ\_FW\_CF0: Data Acquisition 4](#req_fw_cf0-data-acquisition)
>
> [Description 4](#description)
>
> [Tested by 4](#tested-by)
>
> [REQ\_FW\_CF1: Data Transmission 4](#req_fw_cf1-data-transmission)
>
> [Description 4](#description-1)
>
> [Tested by 4](#tested-by-1)
>
> [REQ\_FW\_CF2: Device Identification
> 5](#req_fw_cf2-device-identification)
>
> [Description 5](#description-2)
>
> [Tested by 5](#tested-by-2)
>
> [REQ\_FW\_CF3: Device Performances for an assembly of main boards and
> buffer
> 5](#req_fw_cf3-device-performances-for-an-assembly-of-main-boards-and-buffer)
>
> [Description 5](#description-3)
>
> [Tested by 5](#tested-by-3)
>
> [REQ\_FW\_CF4: Battery safe-use Performance
> 5](#req_fw_cf4-battery-safe-use-performance)
>
> [Description: 5](#description-4)
>
> [Device shall implement a battery protection mechanism
> 5](#_74ne14sc52wq)
>
> [Tested by 5](#tested-by-4)

[**Firmware Control of Integrity Features
5**](#firmware-control-of-integrity-features)

#  

# Document History

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>version</th>
<th>Description</th>
<th>Author</th>
<th>Date</th>
<th>Reviewer</th>
<th>Date</th>
<th>Approver</th>
<th>Date</th>
</tr>
<tr class="odd">
<th>V1</th>
<th>Creation</th>
<th>Mehdi Zemzem Lead Firmware</th>
<th><p>24/01/2024</p>
<p><img src="./attachments/$myfilename/media/image3.png"
style="width:0.5486in;height:0.23749in" /></p></th>
<th>Emmanuel Lange CTO</th>
<th>approved 26/1/2024<img
src="./attachments/$myfilename/media/image4.png"
style="width:0.63542in;height:0.30556in" /></th>
<th>Mathilde Béal Head Product</th>
<th><p>approved 26/1/2024</p>
<p><img src="./attachments/$myfilename/media/image2.jpg"
style="width:0.58854in;height:0.77718in" /></p></th>
</tr>
<tr class="header">
<th>V2</th>
<th>Add Reference to test document</th>
<th>Mehdi Zemzem Lead Firmware</th>
<th>12/03/2024<br />
<img src="./attachments/$myfilename/media/image3.png"
style="width:0.5486in;height:0.23749in" /></th>
<th>Emmanuel Lange CTO</th>
<th>15/03/2024<img src="./attachments/$myfilename/media/image4.png"
style="width:0.63542in;height:0.30556in" /></th>
<th>Mathilde Béal Head Product</th>
<th><p>15/03/2024</p>
<p><img src="./attachments/$myfilename/media/image2.jpg"
style="width:0.58854in;height:0.77718in" /></p></th>
</tr>
<tr class="odd">
<th>V3</th>
<th><p>Update Reference list</p>
<p>Update REQ_FW_CF4 and REQ_FW_CI1</p></th>
<th>Mehdi Zemzem Lead Firmware</th>
<th>25/03/2024<img src="./attachments/$myfilename/media/image3.png"
style="width:0.5486in;height:0.23749in" /></th>
<th>Emmanuel Lange CTO</th>
<th>29/03/2024<img src="./attachments/$myfilename/media/image4.png"
style="width:0.63542in;height:0.30556in" /></th>
<th>Mathilde Béal Head Product</th>
<th><p>29/03/2024</p>
<p><img src="./attachments/$myfilename/media/image2.jpg"
style="width:0.58854in;height:0.77718in" /></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

# Introduction

This document contains the firmware specifications.

# Abbreviations

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>EEG</th>
<th>ElectroEncephaloGraphy</th>
</tr>
<tr class="odd">
<th>BLE</th>
<th>Bluetooth Low Energy</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

# Referenced documents

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ref</th>
<th>Document</th>
<th>Description</th>
<th>Link</th>
</tr>
<tr class="odd">
<th>R0</th>
<th>[V6xl/Nano_VX_X] REC_TSP_FW_V3</th>
<th>Tests description and template test report</th>
<th>REC_TSP_FW_V4.pdf</th>
</tr>
<tr class="header">
<th>R0</th>
<th colspan="3"><p><strong>EUT</strong> means Electronic unit test</p>
<p><strong>FUT</strong> means Firmware unit test</p>
<p><strong>FT</strong> means Functional tests</p>
<p><strong>ST</strong> means Safety Test</p>
<p><strong>SPT</strong> means Science Proof test</p></th>
</tr>
<tr class="odd">
<th>R1</th>
<th>DDMMYY_DUT_V6XL_VX_X_TSP [VnV_SEEG102] 201.12.1.102 Accuracy of
amplitude and rate of variation test report form</th>
<th>Test description and template test report for Accuracy test</th>
<th>Templates/Accuracy of amplitude and rate of variation test report
form.pdf</th>
</tr>
<tr class="header">
<th>R2</th>
<th>DDMMYY_DUT_V6XL_VX_X_TSP [VnV_SEEG103] 201.12.1.103 Input dynamic
range and differential offset voltage_test report form</th>
<th>Test description and template test report for Dynamic Range
Test</th>
<th>Templates/Accuracy of amplitude and rate of variation test report
form.pdf</th>
</tr>
<tr class="odd">
<th>R3</th>
<th>DDMMYY_DUT_V6XL_VX_X_TSP [VnV_CMMR104] I201.12.1.104 Noise input
test report form</th>
<th>Test description and template test report for Input Noise test</th>
<th>Templates/Accuracy of amplitude and rate of variation test report
form.pdf</th>
</tr>
<tr class="header">
<th>R4</th>
<th>DDMMYY_DUT_V6XL_VX_X_TSP[VnV_SEEG105] 201.12.1.105 Frequency
response test report form</th>
<th>Test description and template test report for Frequency response
test</th>
<th>Templates/Accuracy of amplitude and rate of variation test report
form.pdf</th>
</tr>
<tr class="odd">
<th>R5</th>
<th>DDMMYY_DUT_V6XL_VX_X_TSP[VnV_CMRR106] 201.12.1.106 Common Mode
Rejection test report form</th>
<th>Test description and template test report for Common Mode Rejection
test</th>
<th>Templates/Accuracy of amplitude and rate of variation test report
form.pdf</th>
</tr>
<tr class="header">
<th>R6</th>
<th>REC_IOQ_Whaleteq Devices Description</th>
<th>Description of Whaleteq 2 parts test bench for EEG integrity
Testing</th>
<th>Templates/REC_IOQ_Whaleteq Devices description and initial
setup.pdf</th>
</tr>
<tr class="odd">
<th>R7</th>
<th>REC_REQ sw SIGNAL</th>
<th>description of the middleware/front EEG reader software
requirements</th>
<th>REC_REQ SW SIGNAL V2_REC_TSP sw SIGNAL TSP V2.pdf</th>
</tr>
<tr class="header">
<th>R8</th>
<th>REC_TSP sw SIGNAL</th>
<th>description of the middleware/front EEG reader software tests
acceptance criteria and tests reports</th>
<th>REC_REQ SW SIGNAL V2_REC_TSP sw SIGNAL TSP V2.pdf</th>
</tr>
<tr class="odd">
<th>R9</th>
<th>REC_TSP [VnV_IMPE#1] Impedance check on eartips</th>
<th>test criteria and protocol for checking impedance of dry electrodes
in eartips form</th>
<th>Templates/REC_TSP [VnV_IMPE%231] Impedance check on
eartips.pdf.pdf</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

# Firmware Requirements for core functions

## REQ\_FW\_CF0: Data Acquisition

### Description

NBuds shall acquire EEG data

### Tested by

EUT-0\[R0\], EUT-1\[R0\], EUT-2\[R0\], EUT-5\[R0\], EUT-6\[R0\],
FUT-0\[R0\], FUT-2\[R0\],

## REQ\_FW\_CF1: Data Transmission

### Description

NBuds shall transmit EEG data via BLE

### Tested by

FUT-7\[R0\], FUT-8\[R0\], FU-0\[R0\], FU-1\[R0\], SPT-0\[R0\]

## REQ\_FW\_CF2: Device Identification

### Description

User shall be sure of the device they are using

### Tested by

FT-2\[R0\]

## REQ\_FW\_CF3: Device Performances for an assembly of main boards and buffer

### Description

Device shall comply with 80601-2-26 five performance tests

### Tested by

VnV\_SEEG102\[R1\], VnV\_SEEG103\[R2\], VnV\_CMMR104\[R3\],
VnV\_SEEG105\[R4\], VnV\_CMRR106\[R5\]

## REQ\_FW\_CF4: Battery safe-use Performance

### Description: 

Device shall implement a battery protection mechanism

### Tested by

FUT-1\[R0\] ( Battery Gauge sanity check)

# Firmware Control of Integrity Features

This section presentes the features characterized by systematic
acceptance tests to assess the EEG integrity and quality of the signal
compared to a calibrated emulator (see \[R6\])

REQ\_FW\_CI0: EEG integrity due to hardware external components (pin +
eartips)

Description*:*

Physical Integrity of the Hardware pin with reference electrodes

Tested by

VnV\_SEEG102\[R1\], VnV\_SEEG103\[R2\], VnV\_CMMR104\[R3\],
VnV\_SEEG105\[R4\], VnV\_CMRR106\[R5\] (see REQ\_FW\_CF3: Device
Performance)

REQ\_FW\_CI1: Analog Front End

Description:

The analog front end is composed of:

-   An amplifier circuit

-   A high pass filter

-   A low pass filter

Tested by

EUT-5\[R0\], EUT-6\[R0\], VnV\_SEEG102\[R1\], VnV\_SEEG103\[R2\],
VnV\_CMMR104\[R3\], VnV\_SEEG105\[R4\],
VnV\_CMRR106\[R5[<u>\]</u>](https://docs.google.com/document/d/1Qu2yLahkPxJphc97fyMQ1TKM7sLRty7q/edit?rtpof=true)
(see REQ\_FW\_CF3: Device Performance) and <span class="mark">Functional
Tests described in R8</span>

REQ\_FW\_CI2: dry electrode set up

Description

dry electrodes are part of test acceptance for firmware control of
integrity

Tested by

\[R9\]; \[R8 - science tests\]
