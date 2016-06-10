---
layout: post
title: Supported-Barcode-types
description: supported barcode types
platform: js
control: Barcode
documentation: ug
---

# Supported Barcode types

The following table contains the supported types and associated valid characters.

<table>
<tr>
<th>Symbol</th>
<th>Enum Value</th>
<th>Supported characters</th>
<th>Length</th>
</tr>
<tr>
<td>
{{'[QR Code](https://en.wikipedia.org/wiki/QR_code)'| markdownify }}</td><td>
QRBarcode</td><td>
[0–9]; [A–Z (upper-case only)]; [space $ % * + - . / , :]; [Shift JIS characters]</td><td>
variable</td></tr>
<tr>
<td>
{{'[DataMatrix](https://en.wikipedia.org/wiki/Data_Matrix)'| markdownify }}</td><td>
DataMatrix</td><td>
All ASCII characters</td><td>
</td></tr>
<tr>
<td>
{{'[Code 39](https://en.wikipedia.org/wiki/Code_39)'| markdownify }}</td><td>
Code39</td><td>
[0-9]; [A-Z]; [- . $ / + % SPACE]</td><td>
variable</td></tr>
<tr>
<td>
{{'[Code 39 Extended](https://en.wikipedia.org/wiki/Code_39#Full_ASCII_Code_39)'| markdownify }}</td><td>
Code39Extended</td><td>
[0-9]; [A-Z]; [a-z]</td><td>
variable</td></tr>
<tr>
<td>
{{'[Code 11](https://en.wikipedia.org/wiki/Code_11)'| markdownify }}</td><td>
Code11</td><td>
[0-9]; [-]</td><td>
variable</td></tr>
<tr>
<td>
{{'[Codabar](https://en.wikipedia.org/wiki/Codabar)'| markdownify }}</td><td>
Codabar</td><td>
[0-9]; [- $ : / . +]</td><td>
variable</td></tr>
<tr>
<td>
Code 32</td><td>
Code32</td><td>
[0-9]</td><td>
8</td></tr>
<tr>
<td>
{{'[Code 93](https://en.wikipedia.org/wiki/Code_93)'| markdownify }}</td><td>
Code93</td><td>
[0-9]; [A-Z]; [- . $ / + % SPACE]</td><td>
variable</td></tr>
<tr>
<td>
{{'[Code 93 Extended](https://en.wikipedia.org/wiki/Code_93#Full_ASCII_Code_93)'| markdownify }}</td><td>
Code93Extended</td><td>
All 128 ASCII characters</td><td>
variable</td></tr>
<tr>
<td>
{{'[Code 128A](https://en.wikipedia.org/wiki/Code_128)'| markdownify }}</td><td>
Code128A</td><td>
[0-9]; [A-Z]; [NUL (0x00) SOH (0x01) STX (0x02) ETX (0x03) EOT(0x04) ENQ (0x05) ACK (0x06) BEL (0x07) BS (0x08) HT (0x09) LF (0x0A) VT(0x0B) FF (0x0C) CR (0x0D) SO (0x0E) SI (0x0F) DLE (0x10) DC1 (0x11) DC2(0x12) DC3 (0x13) DC4 (0x14) NAK (0x15) SYN (0x16) ETB (0x17) CAN(0x18) EM (0x19) SUB (0x1A) ESC (0x1B) FS (0x1C) GS (0x1D) RS (0x1E) US(0x1F) SPACE (0x20)]; [" ! # $ % & ' ( ) * + , - . / ; &lt; = &gt; ? @ [ / ]^ _ ]</td><td>
variable</td></tr>
<tr>
<td>
{{'[Code 128B](https://en.wikipedia.org/wiki/Code_128)'| markdownify }}</td><td>
Code128B</td><td>
[0-9]; [A-Z]; [a-z]; [SPACE (0x20) ! " # $ % & ' ( ) * + , - . / :; &lt; = &gt; ? @ [ / ]^ _ `  { | } ~ DEL (•) ]</td><td>
variable</td></tr>
<tr>
<td>
{{'[Code 128C](https://en.wikipedia.org/wiki/Code_128)'| markdownify }}</td><td>
Code128C</td><td>
ASCII 00-99(encodes each two digit with one code)</td><td>
variable</td></tr>
</table>
