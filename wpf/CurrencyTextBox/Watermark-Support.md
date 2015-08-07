---
layout: post
title: Watermark-Support
description: watermark support
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Watermark Support

Watermark is the dummy content displayed in the CurrencyTextBox when the value is null. The WatermarkText support behavior can be enabled by setting the WatermarkTextIsVisible property to true.


{% highlight xml %}

[XAML]



<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Width="150" Height="25" 

            WatermarkText="Type Here" WatermarkTextIsVisible="True" 

            WatermarkOpacity="0.5" UseNullOption="True"/>

{% endhighlight %}

![](Watermark-Support_images/Watermark-Support_img1.png)





WatermarkText automatically collapses when the control is in focus. When the control loses its focus the WatermarkText comes to visible state if Value is null and WatermarkTextIsVisible is true.

## Using the WatermarkTemplate

You can customize the Visual appearance of the WatermarkText by using the WatermarkTemplate property.



{% highlight xml %}

[XAML]



<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Width="150" Height="25" 

                            WatermarkText="Type Here" CornerRadius="3" 

                            WatermarkTextIsVisible="True" WatermarkOpacity="0.5" 

                            UseNullOption="True">

    <syncfusion:CurrencyTextBox.WatermarkTemplate>

        <DataTemplate>

            <Border Background="LightGray">

                <TextBlock Text="{Binding}" VerticalAlignment="Center" Margin="5,0,0,0"/>

            </Border>

        </DataTemplate>

    </syncfusion:CurrencyTextBox.WatermarkTemplate>

</syncfusion:CurrencyTextBox>

{% endhighlight %}

![](Watermark-Support_images/Watermark-Support_img2.png)



