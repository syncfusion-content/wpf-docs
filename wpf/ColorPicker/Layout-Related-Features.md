---
layout: post
title: Layout-Related-Features
description: layout related features
platform: wpf
control: ColorPicker
documentation: ug
---

# Layout Related Features

This section illustrates the Layout-related features of ColorPicker and ColorEdit controls. The following features are discussed:

## Setting Flow Direction

Flow Direction of the ColorPicker and ColorEdit controls is set by using the FlowDirection property.



_Properties table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
FlowDirection</td><td>
Sets the flow direction for the ColorPicker and ColorEdit controls. The options provided are as follows.* LeftToRight* RightToLeft</td></tr>
</table>



Use the following code example to set this property.

<table>
<tr>
<td>
[XAML]<!-- Adding ColorPicker --><syncfusion:ColorPicker FlowDirection="RightToLeft" Name="colorPicker"/><!-- Adding ColorEdit --><syncfusion:ColorEdit FlowDirection="RightToLeft" Name="colorEdit"/></td></tr>
<tr>
<td>
[C#]// Setting flow direction as right to left for ColorEditcolorEdit.FlowDirection = FlowDirection.RightToLeft;// Setting flow direction as right to left for ColorPickercolorPicker.FlowDirection = FlowDirection.RightToLeft;</td></tr>
</table>


{{ '![](Layout-Related-Features_images/Layout-Related-Features_img1.jpeg)' | markdownify }}
{:.image }




## Setting VisualStyle for ColorPicker and ColorEdit Controls  

You can enhance the appearance of the ColorPicker and ColorEdit control, using the VisualStyle property. VisualStyle is an attached property, which gets or sets the value for the visual style. The various built-in visual styles are listed below.

_Properties table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the ColorPicker and ColorEdit controls. The options provided are as follows.BlendOffice2003Office2007BlueOffice2007BlackOffice2007SilverShinyBlueShinyRedSyncOrangeVS2010MetroTransparent</td></tr>
</table>


To set the visual style for the ColorPicker and ColorEdit controls, use the following code.

<table>
<tr>
<td>
[XAML]<!-- Adding ColorPicker --><syncfusion:ColorPicker  syncfusion:SkinStorage.VisualStyle="Office2003" Name="colorPicker"/><!-- Adding ColorEdit --><syncfusion:ColorEdit syncfusion:SkinStorage.VisualStyle="Office2007Blue" Name="colorEdit"/></td></tr>
<tr>
<td>
[C#]//Setting the visual style as Office2007Blue for ColorEdit SkinStorage.SetVisualStyle(colorEdit, "Office2007Blue");  //Setting the visual style as Office2007Blue  for ColorPickerSkinStorage.SetVisualStyle(colorPicker, "Office2007Blue");  </td></tr>
</table>




{{ '![](Layout-Related-Features_images/Layout-Related-Features_img2.jpeg)' | markdownify }}
{:.image }




{{ '![](Layout-Related-Features_images/Layout-Related-Features_img3.jpeg)' | markdownify }}
{:.image }




{{ '![](Layout-Related-Features_images/Layout-Related-Features_img4.jpeg)' | markdownify }}
{:.image }




{{ '![](Layout-Related-Features_images/Layout-Related-Features_img5.jpeg)' | markdownify }}
{:.image }




{{ '![](Layout-Related-Features_images/Layout-Related-Features_img6.jpeg)' | markdownify }}
{:.image }




{{ '![](Layout-Related-Features_images/Layout-Related-Features_img7.jpeg)' | markdownify }}
{:.image }




{{ '![](Layout-Related-Features_images/Layout-Related-Features_img8.png)' | markdownify }}
{:.image }




{{ '![](Layout-Related-Features_images/Layout-Related-Features_img9.png)' | markdownify }}
{:.image }


## Slider Background Color

The sliders available for the ColorEdit control are Alpha, Blue, Green and Red. The control provides options to customize the background of these sliders by using the respective background properties, i.e., BackgroundA, BackgroundB, BackgroundG, BackgroundR. These properties can be used to set the background for the Alpha, Blue, Green and Red sliders respectively.

<table>
<tr>
<td>
[XAML]<Tools:ColorEdit Name="myColorEditor" BackgroundA="DarkBlue" BackgroundB="Yellow" BackgroundG="Black" BackgroundR="Orange"/></td></tr>
<tr>
<td>
[C#]myColorEditor.BackgroundA = Brushes.DarkBlue;myColorEditor.BackgroundB = Brushes.Yellow;myColorEditor.BackgroundG = Brushes.Black;myColorEditor.BackgroundR = Brushes.Orange;</td></tr>
</table>




{{ '![](Layout-Related-Features_images/Layout-Related-Features_img10.jpeg)' | markdownify }}
{:.image }




