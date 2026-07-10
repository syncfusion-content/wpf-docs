---
layout: post
title: Symbology Settings in WPF Barcode control | Syncfusion
description: Learn about Symbology Settings in the Syncfusion WPF SfBarcode control and configure barcode-specific encoding options.
platform: wpf
control: SfBarcode
documentation: ug
---

# Symbology Settings in WPF Barcode (SfBarcode)

Each Barcode symbol can be associated with optional settings that may affect that specific barcode. The code sample below shows the settings of a Code39 barcode.

{% highlight xaml %}

<sync:SfBarcode.SymbologySettings>

         <sync:Code39Setting BarHeight="45" EnableCheckDigit="False" EncodeStartStopSymbols="True" NarrowBarWidth="1" ShowCheckDigit="False"/>

</sync:SfBarcode.SymbologySettings>

{% endhighlight %}

## 1D Barcode settings

The one-dimensional barcodes share some common settings, such as `BarHeight`, which modifies the height of the bars, and `NarrowBarWidth`, which modifies the width ratio of the wide and narrow bars.

{% highlight xaml %}

<sync:SfBarcode.SymbologySettings>

         <sync:Code39Setting BarHeight="45" NarrowBarWidth="1"/>

</sync:SfBarcode.SymbologySettings>


{% endhighlight %}

The one-dimensional barcodes also have error detection settings. The `EnableCheckDigit` property enables the redundancy check using a check digit, the decimal equivalent of a binary parity bit. It consists of a single digit computed from the other digits in the message. The check digit can be shown in the barcode or kept hidden by using the `ShowCheckDigit` property.

The `EncodeStartStopSymbols` property adds Start and Stop symbols to signal a barcode reader that a barcode has been scanned.

{% highlight xaml %}

<sync:SfBarcode.SymbologySettings>

         <sync:Code39Setting EnableCheckDigit="False" EncodeStartStopSymbols="True" ShowCheckDigit="False"/>

</sync:SfBarcode.SymbologySettings>

{% endhighlight %}

## 2D Barcode Settings

The two-dimensional barcodes share a common `XDimension` property, which modifies the block size of a two-dimensional barcode.

### DataMatrix Barcode settings

The DataMatrix barcode settings include properties to modify the encoding and size of the DataMatrix barcode.

{% highlight xaml %}

<sync:SfBarcode.SymbologySettings>

         <sync:DataMatrixSetting XDimension="8" Encoding="ASCIINumeric" Size="Size104x104" />

</sync:SfBarcode.SymbologySettings>

{% endhighlight %}

### Encoding

The encoding of the DataMatrix barcode can be modified using the `Encoding` property. The `DataMatrixEncoding` enumeration has the following four encoding schemes.

* ASCII
* ASCIINumeric
* Auto
* Base256

### Size

The DataMatrix barcode settings allow the user to specify the size of the barcode from a set of predefined sizes available in the `DataMatrixSize` enumeration.

Data Matrix size table

<table>
<tr>
<th>
Data Matrix Size</th><th>
Description</th></tr>
<tr>
<td>
Auto</td><td>
Size is chosen based on the input data</td></tr>
<tr>
<td>
Size10x10</td><td>
Square matrix with 10 rows and 10 columns.</td></tr>
<tr>
<td>
Size12x12</td><td>
Square matrix with 12 rows and 12 columns.</td></tr>
<tr>
<td>
Size14x14</td><td>
Square matrix with 14 rows and 14 columns.</td></tr>
<tr>
<td>
Size16x16</td><td>
Square matrix with 16 rows and 16 columns.</td></tr>
<tr>
<td>
Size18x18</td><td>
Square matrix with 18 rows and 18 columns.</td></tr>
<tr>
<td>
Size20x20</td><td>
Square matrix with 20 rows and 20 columns.</td></tr>
<tr>
<td>
Size22x22</td><td>
Square matrix with 22 rows and 22 columns.</td></tr>
<tr>
<td>
Size24x24</td><td>
Square matrix with 24 rows and 24 columns.</td></tr>
<tr>
<td>
Size26x26</td><td>
Square matrix with 26 rows and 26 columns.</td></tr>
<tr>
<td>
Size32x32</td><td>
Square matrix with 32 rows and 32 columns.</td></tr>
<tr>
<td>
Size36x36</td><td>
Square matrix with 36 rows and 36 columns.</td></tr>
<tr>
<td>
Size40x40</td><td>
Square matrix with 40 rows and 40 columns.</td></tr>
<tr>
<td>
Size44x44</td><td>
Square matrix with 44 rows and 44 columns.</td></tr>
<tr>
<td>
Size48x48</td><td>
Square matrix with 48 rows and 48 columns.</td></tr>
<tr>
<td>
Size52x52</td><td>
Square matrix with 52 rows and 52 columns.</td></tr>
<tr>
<td>
Size64x64</td><td>
Square matrix with 64 rows and 64 columns.</td></tr>
<tr>
<td>
Size72x72</td><td>
Square matrix with 72 rows and 72 columns.</td></tr>
<tr>
<td>
Size80x80</td><td>
Square matrix with 80 rows and 80 columns.</td></tr>
<tr>
<td>
Size88x88</td><td>
Square matrix with 88 rows and 88 columns.</td></tr>
<tr>
<td>
Size96x96</td><td>
Square matrix with 96 rows and 96 columns.</td></tr>
<tr>
<td>
Size104x104</td><td>
Square matrix with 104 rows and 104 columns.</td></tr>
<tr>
<td>
Size120x120</td><td>
Square matrix with 120 rows and 120 columns.</td></tr>
<tr>
<td>
Size132x132</td><td>
Square matrix with 132 rows and 132 columns.</td></tr>
<tr>
<td>
Size144x144</td><td>
Square matrix with 144 rows and 144 columns.</td></tr>
<tr>
<td>
Size8x18</td><td>
Rectangular matrix with 8 rows and 18 columns.</td></tr>
<tr>
<td>
Size8x32</td><td>
Rectangular matrix with 8 rows and 32 columns.</td></tr>
<tr>
<td>
Size12x26</td><td>
Rectangular matrix with 12 rows and 26 columns.</td></tr>
<tr>
<td>
Size12x36</td><td>
Rectangular matrix with 12 rows and 36 columns.</td></tr>
<tr>
<td>
Size16x36</td><td>
Rectangular matrix with 16 rows and 36 columns.</td></tr>
<tr>
<td>
Size16x48</td><td>
Rectangular matrix with 16 rows and 48 columns.</td></tr>
</table>


### QRBarcode settings

The QRBarcode settings include properties to modify the version, error correction level, and input mode of the QRBarcode.

{% highlight xaml %}

<sync:SfBarcode.SymbologySettings>

    <sync:QRBarcodeSetting XDimension="8" ErrorCorrectionLevel="High" InputMode="BinaryMode"  Version="Auto" />

</sync:SfBarcode.SymbologySettings>

{% endhighlight %}


## Version

The QR Barcode uses versions from 1 to 40. Version 1 measures 21 modules × 21 modules, Version 2 measures 25 modules × 25 modules, and so on, increasing in steps of 4 modules per side up to Version 40, which measures 177 modules × 177 modules. Each version has its own capacity. By default, the QR Version is `Auto`, which automatically sets the version according to the input text length.

## Error correction level

The QR Barcode employs error correction to generate a series of error correction codewords that are added to the data codeword sequence to enable the symbol to withstand damage without loss of data. There are four user-selectable levels of error correction, as shown in the table, offering the capability of recovery from the following amounts of damage. By default, the error correction level is **Low**.

Error correction level table

<table>
<tr>
<th>
Error Correction Level</th><th>
Recovery Capacity % (approx.)</th></tr>
<tr>
<td>
L</td><td>
7</td></tr>
<tr>
<td>
M</td><td>
15</td></tr>
<tr>
<td>
Q</td><td>
25</td></tr>
<tr>
<td>
H</td><td>
30</td></tr>
</table>

## Input mode

There are three input modes, as defined in the table. Each mode supports a specific set of input characters. The user may select the most suitable input mode. By default, the input mode is **Binary Mode**.

Input mode table

<table>
<tr>
<th>
Input mode</th><th>
Possible characters</th></tr>
<tr>
<td>
Numeric Mode</td><td>
0, 1, 2, 3, 4, 5, 6, 7, 8, 9</td></tr>
<tr>
<td>
Alphanumeric Mode</td><td>
0–9, A–Z (upper-case only), space, $, %, *, +, -, ., /, :</td></tr>
<tr>
<td>
Binary Mode</td><td>
Shift JIS characters</td></tr>
</table>
