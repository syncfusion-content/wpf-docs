---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: SfBarcode
documentation: ug
---

# Getting Started

## Add Barcode control to an Application 

The following assembly reference is required for deploying Barcode.

Namespace: Syncfusion.UI.Xaml.Controls.Barcode

Assembly: Syncfusion.SfBarcode.WPF

To create the SfBarcode control in Visual Studio:

1. Create a new WPF project. 
2. Drag the SfBarcode control from the Toolbox window to the Design View. An instance of the SfBarcode control is created in the Design view.



{ ![](Getting-Started_images/Getting-Started_img1.png) | markdownify }
{:.image }




The following code example shows how to create the Barcode control from XAML:

[XAML]

&lt;Page xmlns:sync="using:Syncfusion.UI.Xaml.Controls.Barcode"&gt;

    &lt;Grid&gt;

        &lt;sync:SfBarcode x:Name="barcode" Text="http://www.syncfusion.com" Symbology="QRBarcode"&gt;

                    &lt;sync:SfBarcode.SymbologySettings&gt;

                        &lt;sync:QRBarcodeSetting XDimension="8"/&gt;

                    &lt;/sync:SfBarcode.SymbologySettings&gt;

                &lt;/sync:SfBarcode&gt;

    &lt;/Grid&gt;

&lt;/Page&gt;



Text

The text to be encoded can be set using the Text property. By default, this original text will be displayed at the bottom of the bar code. The location of the text can be toggled between top and bottom using TextLocation property. The horizontal alignment of the text can be set using TextAlignment. The text brush and other various font customization can also be done using the built-in font properties. Optionally, the user can hide the barcode text by setting the DisplayText property to false.

[XAML]

&lt;sync:SfBarcode x:Name="barcode" Text="http://www.syncfusion.com" DisplayText="False” Symbology="QRBarcode"/&gt;



Rotation

Barcode control can be rotated to save space by using the Rotation property. The barcode can be rotated to 90, 180 and 270 degrees.

