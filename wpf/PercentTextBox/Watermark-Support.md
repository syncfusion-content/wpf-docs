---
layout: post
title: Watermark Support| PercentTextBox  | Wpf | Syncfusion
description: watermark support
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Watermark Support

Watermark is the dummy content displayed in the PercentTextBox when the value is null. The WatermarkText support behavior can be enabled by setting the WatermarkTextIsVisible property to true.

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="150" Height="25" 
            WatermarkText="Type Here" WatermarkTextIsVisible="True" 
            WatermarkOpacity="0.5" UseNullOption="True"/>

{% endhighlight %}
{% endtabs %}

![](Watermark-Support_images/Watermark-Support_img1.png)


WatermarkText automatically collapses when the control is in focus. When the control loses its focus the WatermarkText comes to the visible state if the PercentValue is null and the WatermarkTextIsVisible is true.

## Using the WatermarkTemplate

You can customize the Visual appearance of the WatermarkText by using the WatermarkTemplate property.

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="150" Height="25" 
WatermarkText="Type Here" CornerRadius="3" 
WatermarkTextIsVisible="True" WatermarkOpacity="0.5" 
UseNullOption="True">
<syncfusion:PercentTextBox.WatermarkTemplate>
<DataTemplate>
<Border Background="LightGray">
<TextBlock Text="{Binding}" VerticalAlignment="Center" Margin="5,0,0,0"/>
</Border>
</DataTemplate>
</syncfusion:PercentTextBox.WatermarkTemplate>
</syncfusion:PercentTextBox>

{% endhighlight %}
{% endtabs %}

![](Watermark-Support_images/Watermark-Support_img2.png)


