---
layout: post
title: Appearance in WPF TimePicker | Syncfusion
description: Learn about appearance customization and styling options available in WPF TimePicker control easily.
platform: scheduler-sdk
control: SfTimePicker
documentation: ug
---

# Appearance in WPF TimePicker

This section explains different UI customization, styling, theming options available in [SfTimePicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimePicker.html) control.

## Setting the Foreground

We can change the foreground of the `SfTimePicker` by using the `Foreground` property and also we can change the [SfTimeSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimeSelector.html) items and selected time item foreground by using the `Foreground` and [SfTimeSelector.SelectedForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimeSelector.html#Syncfusion_Windows_Controls_Input_SfTimeSelector_SelectedForeground) properties of `SfTimeSelector`.

{% highlight XAML %}

<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
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
</Window>

{% endhighlight  %}

![SfTimePicker with various foreground](Features_images/Foreground.png)

## Setting the Background

We can change the background of the `SfTimePicker` by using the `Background` property and also we can change the [SfTimeSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimeSelector.html) items and selected time item background by using the `Background` and [SfTimeSelector.AccentBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimePicker.html#Syncfusion_Windows_Controls_Input_SfTimePicker_AccentBrush) properties of `SfTimeSelector`.

{% highlight XAML %}

<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
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
</Window>

{% endhighlight  %}

![SfTimePicker with various background](Features_images/Background.png)

## Change flow direction

We can change the flow direction of the `SfTimePicker` control from right to left by setting the `FlowDirection` property value as `RightToLeft`. The default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight xaml %}

<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:SfTimePicker FlowDirection="RightToLeft" Name="sfTimePicker"/>
</Window>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Controls.Input;

SfTimePicker sfTimePicker= new SfTimePicker();
sfTimePicker.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![SfTimePicker with RightToLeft flow direction](Features_images/Appearance-flowdirection.png)

Click [here](https://github.com/SyncfusionExamples/wpf-time-picker-examples/tree/master/Samples/Apperance) to download the sample that showcases the different UI customization and styling supports.

## Theme

SfTimePicker supports various built-in themes. Refer to the below links to apply themes for the SfTimePicker,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Setting theme to WPF TimePicker](Features_images/Theme.png)
