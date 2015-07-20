---
layout: post
title: Watermark-Support
description: watermark support
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Watermark Support

Watermark is the dummy content displayed in the IntegerTextBox when the value is null. The WatermarkText support behavior can be enabled by setting the WatermarkTextIsVisible property to true.

XAML



<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="150" Height="25" 

                           WatermarkText="Type Here" WatermarkTextIsVisible="True" 

                           WatermarkOpacity="0.5" UseNullOption="True"/>



{{ '![](Watermark-Support_images/Watermark-Support_img1.png)' | markdownify }}
{:.image }


WatermarkText automatically collapses when the control is in focus. On Lost Focus the WatermarkText comes to the visible state if the Value is null and the WatermarkTextIsVisible is true.

## Using the WatermarkTemplate

You can customize the Visual appearance of the Watermark Text by using the WatermarkTemplate property.

XAML



<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="150" Height="25"

                           WatermarkText="Type Here" CornerRadius="3" 

                           WatermarkTextIsVisible="True" WatermarkOpacity="0.5" 

                           UseNullOption="True">

    <syncfusion:IntegerTextBox.WatermarkTemplate>

        <DataTemplate>

            <Border Background="LightGray">

                <TextBlock Text="{Binding}" VerticalAlignment="Center" Margin="5,0,0,0"/>

            </Border>

        </DataTemplate>

    </syncfusion:IntegerTextBox.WatermarkTemplate>

</syncfusion:IntegerTextBox>



{{ '![](Watermark-Support_images/Watermark-Support_img2.png)' | markdownify }}
{:.image }


