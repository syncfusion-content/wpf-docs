---
layout: post
title: Appearance of the WPF SfTimePicker control | Syncfusion
description: Learn about UI customization, styling, theme support in Syncfusion WPF SfTimePicker control and more details about the control features.
platform: wpf
control: SfTimePicker
documentation: ug
---

# Appearance and Styling in WPF SfTimePicker

This section explains different UI customization, styling, theming options available in [SfTimePicker](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker.html) control.

## Setting the Foreground

We can change a foreground of the `SfTimePicker` by using the `Foreground` property and also we can change the [SfTimeSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector.html) items and selected time item foreground by using the `Foreground` and [SfTimeSelector.SelectedForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector~SelectedForeground.html) properties of `SfTimeSelector`.

{% highlight XAML %}

<syncfusion:SfTimePicker Name="sfTimePicker"
                         Foreground="Red"
                         Width="200">
    <syncfusion:SfTimePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfTimeSelector">
            <Setter Property="Foreground" Value="Blue"/>
            <Setter Property="SelectedForeground" Value="Yellow"/>
        </Style>
    </syncfusion:SfTimePicker.SelectorStyle>
</syncfusion:SfTimePicker>

{% endhighlight  %}

![SfTimePicker with various foreground](Features_images/Foreground.png)

## Setting the Background

We can change a background of the `SfTimePicker` by using the `background` property and also we can change the [SfTimeSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector.html) items and selected time item background by using the `Background` and [SfTimeSelector.AccentBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~AccentBrush.html) properties of `SfTimeSelector`.

{% highlight XAML %}

<syncfusion:SfTimePicker Name="sfTimePicker"
                         Background="Red"
                         AccentBrush="Green"
                 Width="200">
    <syncfusion:SfTimePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfTimeSelector">
            <Setter Property="Background" Value="Blue"/>
        </Style>
    </syncfusion:SfTimePicker.SelectorStyle>
</syncfusion:SfTimePicker>

{% endhighlight  %}

![SfTimePicker with various background](Features_images/Background.png)

## Change flow direction

We can change the flow direction of the `SfTimePicker` control from right to left by setting the `FlowDirection` property value as `RightToLeft`. The Default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTimePicker FlowDirection="RightToLeft" Name="sfTimePicker"/>

{% endhighlight %}
{% highlight C# %}

SfTimePicker sfTimePicker= new SfTimePicker();
sfTimePicker.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![SfTimePicker with RightToLeft flow direction](Features_images/Appearance-flowdirection.png)

## Setting WaterMark text

We can prompt the user with some information by using the [Watermark](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~Watermark.html) property. This will apply on when the `SfTimePicker` contains the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~Value.html) property as `null` and [AllowNull](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~AllowNull.html) property as `true`.  After selecting the time, the Watermark will automatically hide.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTimePicker Watermark="Select the Time"
                         AllowNull="True"  
                         Value="{x:Null}"
                         Name="sfTimePicker" >
</syncfusion:SfTimePicker>

{% endhighlight %}
{% highlight C# %}

SfTimePicker sfTimePicker = new SfTimePicker();
sfTimePicker.Watermark = "Select the Time";
sfTimePicker.AllowNull = true;
sfTimePicker.Value = null;

{% endhighlight %}
{% endtabs %}

![SfTimePicker with watermark text](Features_images/Watermark.png)

### Setting WaterMark Template

We can change the template of the `Watermark` by using the [WatermarkTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~WatermarkTemplate.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTimePicker Name="sfTimePicker" 
                         AllowNull="True" 
                         Value="{x:Null}" 
                         Watermark="Select the Time" >
    <syncfusion:SfTimePicker.WatermarkTemplate >
        <DataTemplate>
            <Border Background="Yellow">
                <TextBlock Foreground="Blue"
                           FontWeight="Bold"  
                           Text="{Binding}" 
                           TextAlignment="Center"/>
            </Border>
        </DataTemplate>
    </syncfusion:SfTimePicker.WatermarkTemplate>
</syncfusion:SfTimePicker>

{% endhighlight %}
{% endtabs %}

![SfTimePicker with watermarktemplate](Features_images/WatermarkTemplate.png)

Click [here](https://github.com/SyncfusionExamples/wpf-time-picker-examples/tree/master/Samples/Apperance) to download the sample that showcases the different UI customization and styling supports.