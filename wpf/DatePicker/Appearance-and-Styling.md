---
layout: post
title: Appearance and Styling | SfDatePicker | WPF | Syncfusion
description: Appearance and Styling of SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# Appearance and Styling in WPF SfDatePicker

This section explains different UI customization, styling, theming options available in [SfDatePicker](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker.html) control.

## Setting the Foreground

We can change a foreground of the `SfDatePicker` by using the `Foreground` property and also we can change the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector.html) items and selected date item foreground by using the `Foreground` and [SfDateSelector.SelectedForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~SelectedForeground.html) properties of `SfDateSelector`.

{% highlight XAML %}

<syncfusion:SfDatePicker Name="sfdatePicker"
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

<syncfusion:SfDatePicker Name="sfdatePicker"
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