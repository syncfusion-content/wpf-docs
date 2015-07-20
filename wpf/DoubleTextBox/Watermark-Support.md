---
layout: post
title: Watermark-Support
description: watermark support
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Watermark Support

Watermark is the dummy content displayed in the DoubleTextBox when the value is null. The WatermarkText support behavior can be enabled by setting the WatermarkTextIsVisible property to true.



<table>
<tr>
<td>
XAML</td></tr>
<tr>
<td>
<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25"                            WatermarkText="Type Here" WatermarkTextIsVisible="True"                            WatermarkOpacity="0.5" UseNullOption="True"/></td></tr>
</table>


{ ![](Watermark-Support_images/Watermark-Support_img1.png) | markdownify }
{:.image }




WatermarkText automatically collapses when the control is in focus. When the control loses its focus the WatermarkText comes to the visible state if the Value is null and the WatermarkTextIsVisible is true.

## Using the WatermarkTemplate

You can customize the Visual appearance of the WatermarkText by using the WatermarkTemplate property.



XAML



<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25"

            WatermarkText="Type Here" CornerRadius="3" 

            WatermarkTextIsVisible="True" WatermarkOpacity="0.5" 

            UseNullOption="True">

&lt;syncfusion:DoubleTextBox.WatermarkTemplate&gt;

    &lt;DataTemplate&gt;

        &lt;Border Background="LightGray"&gt;

            &lt;TextBlock Text="{Binding}" VerticalAlignment="Center" Margin="5,0,0,0"/&gt;

        &lt;/Border&gt;

    &lt;/DataTemplate&gt;

&lt;/syncfusion:DoubleTextBox.WatermarkTemplate&gt;

&lt;/syncfusion:DoubleTextBox&gt;



{ ![](Watermark-Support_images/Watermark-Support_img2.png) | markdownify }
{:.image }


