---
layout: post
title: Watermark Support| DoubleTextBox  | Wpf | Syncfusion
description: watermark support
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Watermark Support

Watermark is the dummy content displayed in the DoubleTextBox when the value is null. The [WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) support behavior can be enabled by setting the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextIsVisible.html) property to true.



{% tabs %}
{% highlight xaml %} XAML {% endhighlight %} 

{% highlight xaml %} <syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25"                            WatermarkText="Type Here" WatermarkTextIsVisible="True"                            WatermarkOpacity="0.5" UseNullOption="True"/> {% endhighlight %} 
{% endtabs %}


![Watermark support](Watermark-Support_images/Watermark-Support_img1.png)





[WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) automatically collapses when the control is in focus. When the control loses its focus the WatermarkText comes to the visible state if the Value is null and the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextIsVisible.html) is true.

## Using the WatermarkTemplate

You can customize the Visual appearance of the WatermarkText by using the [WatermarkTemplate](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTemplate.html) property.



{% highlight xaml %}



<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25"

WatermarkText="Type Here" CornerRadius="3" 

WatermarkTextIsVisible="True" WatermarkOpacity="0.5" 

UseNullOption="True">

<syncfusion:DoubleTextBox.WatermarkTemplate>

<DataTemplate>

<Border Background="LightGray">

<TextBlock Text="{Binding}" VerticalAlignment="Center" Margin="5,0,0,0"/>

</Border>

</DataTemplate>

</syncfusion:DoubleTextBox.WatermarkTemplate>

</syncfusion:DoubleTextBox>

{% endhighlight %}

![Watermark template](Watermark-Support_images/Watermark-Support_img2.png)



