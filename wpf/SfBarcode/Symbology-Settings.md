---
layout: post
title: Symbology-Settings
description: symbology settings
platform: wpf
control: SfBarcode
documentation: ug
---

## Symbology Settings

Each Barcode symbol can be associated with optional settings that may affect that specific bar code. The code sample below shows the settings of a code39 Barcode.

[XAML]

<sync:SfBarcode.SymbologySettings>

         <sync:Code39Setting BarHeight="45" EnableCheckDigit="False" EncodeStartStopSymbols="True" NarrowBarWidth="1" ShowCheckDigit="False"/>

</sync:SfBarcode.SymbologySettings>



### 1D Barcode settings

The one dimensional barcodes have some of the settings in common, such as BarHeight which modifies the height of the bars and NarrowBarWidth which modifies the width ratio of the wide and narrow bars.

[XAML]

<sync:SfBarcode.SymbologySettings>

         <sync:Code39Setting BarHeight="45" NarrowBarWidth="1"/>

</sync:SfBarcode.SymbologySettings>



The one dimensional barcodes also has the error detection settings. The EnableCheckDigit property enables the redundancy check using a check digit, the decimal equivalent of a binary parity bit. It consists of a single digit computed from the other digits in the message. The check digit can be shown in the barcode or kept hidden by using the ShowCheckDigit property.

The EncodeStartStopSymbols property adds Start and Stop symbols to signal a bar code reader that a bar code has been scanned.

[XAML]

<sync:SfBarcode.SymbologySettings>

         <sync:Code39Setting EnableCheckDigit="False" EncodeStartStopSymbols="True" ShowCheckDigit="False"/>

</sync:SfBarcode.SymbologySettings>



### 2D Barcode Settings

The two dimensional barcodes have a common XDimension property which modifies the block size of a two dimensional barcode.

DataMatrix Barcode settings

The DataMatrix barcode settings has the properties to modify the encoding and size of the DataMatrix barcode.

[XAML]

<sync:SfBarcode.SymbologySettings>

         <sync:DataMatrixSetting XDimension="8" Encoding="ASCIINumeric” Size="Size104x104" />

</sync:SfBarcode.SymbologySettings>



Encoding

The encoding of the DataMatrix barcode can be modified using the ‘Encoding’ property. The DataMatrixEncoding enumeration has the following four encoding schemes.

* ASCII
* ASCIINumeric
* Auto
* Base256

Size

The DataMatrix Barcode settings allow the user to specify the size of the barcode from a set of predefined sizes available in the DataMatrixSize enumeration.

_Data Matrix size Table_

<table>
<tr>
<th>
Data Matrix Size</th><th>
Description</th></tr>
<tr>
<th>
Auto</th><th>
Size is chosen based on the input data</th></tr>
<tr>
<th>
Size10x10</th><th>
Square matrix with 10 rows and 10 columns.</th></tr>
<tr>
<th>
Size12x12</th><th>
Square matrix with 12 rows and 12 columns.</th></tr>
<tr>
<th>
Size14x14</th><th>
Square matrix with 14 rows and 14 columns.</th></tr>
<tr>
<th>
Size16x16</th><th>
Square matrix with 16 rows and 16 columns.</th></tr>
<tr>
<th>
Size18x18</th><th>
Square matrix with 18 rows and 18 columns.</th></tr>
<tr>
<th>
Size20x20</th><th>
Square matrix with 20 rows and 20 columns.</th></tr>
<tr>
<th>
Size22x22</th><th>
Square matrix with 22 rows and 22 columns.</th></tr>
<tr>
<th>
Size24x24</th><th>
Square matrix with 24 rows and 24 columns.</th></tr>
<tr>
<th>
Size26x26</th><th>
Square matrix with 26 rows and 26 columns.</th></tr>
<tr>
<th>
Size32x32</th><th>
Square matrix with 32 rows and 32 columns.</th></tr>
<tr>
<th>
Size36x36</th><th>
Square matrix with 36 rows and 36 columns.</th></tr>
<tr>
<th>
Size40x40</th><th>
Square matrix with 40 rows and 40 columns.</th></tr>
<tr>
<th>
Size44x44</th><th>
Square matrix with 44 rows and 44 columns.</th></tr>
<tr>
<th>
Size48x48</th><th>
Square matrix with 48 rows and 48 columns.</th></tr>
<tr>
<th>
Size52x52</th><th>
Square matrix with 52 rows and 52 columns.</th></tr>
<tr>
<th>
Size64x64</th><th>
Square matrix with 64 rows and 64 columns.</th></tr>
<tr>
<th>
Size72x72</th><th>
Square matrix with 72 rows and 72 columns.</th></tr>
<tr>
<th>
Size80x80</th><th>
Square matrix with 80 rows and 80 columns.</th></tr>
<tr>
<th>
Size88x88</th><th>
Square matrix with 88 rows and 88 columns.</th></tr>
<tr>
<th>
Size96x96</th><th>
Square matrix with 96 rows and 96 columns.</th></tr>
<tr>
<th>
Size104x104</th><th>
Square matrix with 104 rows and 104 columns.</th></tr>
<tr>
<th>
Size120x120</th><th>
Square matrix with 120 rows and 120 columns.</th></tr>
<tr>
<th>
Size132x132</th><th>
Square matrix with 132 rows and 132 columns.</th></tr>
<tr>
<th>
Size144x144</th><th>
Square matrix with 144 rows and 144 columns.</th></tr>
<tr>
<th>
Size8x18</th><th>
Rectangular matrix with 8 rows and 18 columns.</th></tr>
<tr>
<th>
Size8x32</th><th>
Rectangular matrix with 8 rows and 32 columns.</th></tr>
<tr>
<th>
Size12x26</th><th>
Rectangular matrix with 12 rows and 26 columns.</th></tr>
<tr>
<th>
Size12x36</th><th>
Rectangular matrix with 12 rows and 36 columns.</th></tr>
<tr>
<th>
Size16x36</th><th>
Rectangular matrix with 16 rows and 36 columns.</th></tr>
<tr>
<th>
Size16x48</th><th>
Rectangular matrix with 16 rows and 48 columns.</th></tr>
</table>


QRBarcode settings

The QRBarcode settings has properties to modify the version, error correction level and Input mode of the QRBarcode.

[XAML]

<sync:SfBarcode.SymbologySettings>

         <sync:QRBarcodeSetting XDimension="8" ErrorCorrectionLevel="High” InputMode="BinaryMode”  Version="Auto" />

</sync:SfBarcode.SymbologySettings>





Version

The QR Barcode uses version from 1 to 40.Version 1 measures 21 modules x 21 modules, Version 2 measures 25 modules x 25 modules and so on increasing in steps of 4 modules per side up to Version 40 which measures 177 modules x 177 modules. Each version has its own capacity.  By default the QR Version is Auto, which will automatically set the version according to the input text length.

Error correction level

The QR Barcode employs error correction to generate a series of error correction codewords which are added to the data code word sequence in order to enable the symbol to withstand damage without loss of data. There are four user–selectable levels of error correction, as shown in the table, offering the capability of recovery from the following amounts of damage. By default the Error correction level is Low.

_Error Correction Level Table_

<table>
<tr>
<th>
Error Correction Level</th><th>
Recovery Capacity % (approx.)</th></tr>
<tr>
<th>
L</th><th>
7</th></tr>
<tr>
<th>
M</th><th>
15</th></tr>
<tr>
<th>
Q</th><th>
25</th></tr>
<tr>
<th>
H</th><th>
30</th></tr>
</table>
Input mode

There are three modes for the input as defined in the table. Each mode supports the specific set of Input characters. User may select the most suitable input mode. By default the Input mode is Binary Mode.

_Input Mode Table_

<table>
<tr>
<th>
Input Mode</th><th>
Possible characters</th></tr>
<tr>
<th>
Numeric Mode</th><th>
0,1,2,3,4,5,6,7,8,9</th></tr>
<tr>
<th>
Alphanumeric Mode</th><th>
0–9, A–Z (upper-case only), space, $, %, *, +, -,., /, :</th></tr>
<tr>
<th>
Binary Mode</th><th>
Shift JIS characters</th></tr>
</table>




