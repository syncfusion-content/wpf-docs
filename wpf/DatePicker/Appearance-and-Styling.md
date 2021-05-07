---
layout: post
title: Appearance in WPF DatePicker control | Syncfusion
description: Learn here all about Appearance support in Syncfusion WPF DatePicker (SfDatePicker) control and more.
platform: wpf
control: SfDatePicker
documentation: ug
---

# Appearance in WPF DatePicker (SfDatePicker)

This section explains different UI customization, styling, theming options available in [SfDatePicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDatePicker.html) control.

## Setting the Foreground

We can change a foreground of the `SfDatePicker` by using the `Foreground` property and also we can change the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDateSelector.html) items and selected date item foreground by using the `Foreground` and [SfDateSelector.SelectedForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDateSelector.html#Syncfusion_Windows_Controls_Input_SfDateSelector_SelectedForeground) properties of `SfDateSelector`.

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

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/Apperance)

## Setting the Background

We can change a background of the `SfDatePicker` by using the `background` property and also we can change the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDateSelector.html) items and selected date item background by using the `Background` and [SfDateSelector.AccentBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDatePicker.html#Syncfusion_Windows_Controls_Input_SfDatePicker_AccentBrush) properties of `SfDateSelector`.

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

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/Apperance)

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

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/Apperance)

## Theme

SfDatePicker supports various built-in themes. Refer to the below links to apply themes for the SfDatePicker,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)
  
![Setting theme to WPF DatePicker](Appearance-and-Styling_images/Theme.png)
