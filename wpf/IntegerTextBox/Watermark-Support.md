---
layout: post
title: Watermark Support | IntegerTextBox | wpf | Syncfusion
description: watermark support
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Watermark Support

Watermark is the dummy content displayed in the IntegerTextBox when the value is null. The [WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) support behavior can be enabled by setting the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextIsVisible.html) property to true.

{% tabs %}
{% highlight xaml %}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="150" Height="25" 
                           WatermarkText="Type Here" WatermarkTextIsVisible="True" 
                           WatermarkOpacity="0.5" UseNullOption="True"/>

{% endhighlight %}
{% endtabs %}

![Watermark support](Watermark-Support_images/Watermark-Support_img1.png)



[WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) automatically collapses when the control is in focus. On Lost Focus the [WatermarkText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkText.html) comes to the visible state if the Value is null and the [WatermarkTextIsVisible](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextIsVisible.html) is true.

## Using the WatermarkTemplate

You can customize the Visual appearance of the Watermark Text by using the [WatermarkTemplate](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTemplate.html) property.

{% tabs %}
{% highlight xaml %}

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

{% endhighlight %}
{% endtabs %}

![Watermark template](Watermark-Support_images/Watermark-Support_img2.png)



