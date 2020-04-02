---
layout: post
title: Appearance of the WPF SfDatePicker control | Syncfusion
description: Learn about UI customization, styling, theme support in Syncfusion WPF SfDatePicker control and more details about the control features.
platform: wpf
control: SfDatePicker
documentation: ug
---

# Appearance and Styling in WPF SfDatePicker

This section explains different UI customization, styling, theming options available in [SfDatePicker](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker.html) control.

## Setting the Foreground

We can change a foreground of the `SfDatePicker` by using the `Foreground` property and also we can change the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector.html) items and selected date item foreground by using the `Foreground` and [SfDateSelector.SelectedForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~SelectedForeground.html) properties of `SfDateSelector`.

{% highlight XAML %}

<syncfusion:SfDatePicker Name="sfDatePicker"
                         Foreground="Red"
                         Width="200">
    <syncfusion:SfDatePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfDateSelector">
            <Setter Property="Foreground" Value="Blue"/>
            <Setter Property="SelectedForeground" Value="Yellow"/>
        </Style>
    </syncfusion:SfDatePicker.SelectorStyle>
</syncfusion:SfDatePicker>

{% endhighlight  %}

![SfDatePicker with various foreground](Appearance-and-Styling_images/Foreground.png)


## Setting the Foreground

We can change a background of the `SfDatePicker` by using the `background` property and also we can change the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector.html) items and selected date item background by using the `Background` and [SfDateSelector.AccentBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~AccentBrush.html) properties of `SfDateSelector`.

{% highlight XAML %}

<syncfusion:SfDatePicker Name="sfDatePicker"
                         Background="Red"
                         AccentBrush="Green"
                 Width="200">
    <syncfusion:SfDatePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfDateSelector">
            <Setter Property="Background" Value="Blue"/>
        </Style>
    </syncfusion:SfDatePicker.SelectorStyle>
</syncfusion:SfDatePicker>

{% endhighlight  %}

![SfDatePicker with various background](Appearance-and-Styling_images/Background.png)

## Change flow direction

We can change the flow direction of the `SfDatePicker` control from right to left by setting the `FlowDirection` property value as `RightToLeft`. The Default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDatePicker FlowDirection="RightToLeft" Name="sfDatePicker"/>

{% endhighlight %}
{% highlight C# %}

SfDatePicker sfDatePicker= new SfDatePicker();
sfDatePicker.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![SfDatePicker with RightToLeft flow direction](Appearance-and-Styling_images/Appearance-flowdirection.png)

## Setting WaterMark text

We can prompt the user with some information by using the [Watermark](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~Watermark.html) property. This will apply on when the `SfDatePicker` contains the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~Value.html) property as `null` and [AllowNull](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~AllowNull.html) property as `true` . 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDatePicker Watermark="Select the Date" Name="sfDatePicker"/>

{% endhighlight %}
{% highlight C# %}

SfDatePicker sfDatePicker= new SfDatePicker();
sfDatePicker.Watermark="Select the Date";

{% endhighlight %}
{% endtabs %}

![SfDatePicker with watermark text](Appearance-and-Styling_images/Watermark.png)

### Setting WaterMark Template

We can change the template of the `Watermark` by using the [WatermarkTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~WatermarkTemplate.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDatePicker Name="sfDatePicker" 
                         AllowNull="True" 
                         Value="{x:Null}" 
                         Watermark="Select the Date" >
    <syncfusion:SfDatePicker.WatermarkTemplate >
        <DataTemplate>
            <Border Background="Yellow">
                <TextBlock Foreground="Blue"
                           FontWeight="Bold"  
                           Text="{Binding}" 
                           TextAlignment="Center"/>
            </Border>
        </DataTemplate>
    </syncfusion:SfDatePicker.WatermarkTemplate>
</syncfusion:SfDatePicker>

{% endhighlight %}
{% endtabs %}

![SfDatePicker with watermarktemplate](Appearance-and-Styling_images/WatermarkTemplate.png)

Click [here](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/Apperance) to download the sample that showcases the different UI customization and styling supports.