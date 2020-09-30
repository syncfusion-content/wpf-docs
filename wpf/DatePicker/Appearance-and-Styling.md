---
layout: post
title: Appearance of the WPF SfDatePicker control | Syncfusion
description: Learn about UI customization, styling, theme support in Syncfusion WPF SfDatePicker control and more details about the control features.
platform: wpf
control: SfDatePicker
documentation: ug
---

# Appearance and Styling in WPF SfDatePicker

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

You can customize the appearance of the `SfDatePicker` control by using the [SfSkinManager.SetVisualStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinmanager.SfSkinmanager.html#Syncfusion_SfSkinManager_SfSkinManager_SetVisualStyle_System_Windows_DependencyObject_Syncfusion_SfSkinManager_VisualStyles_) method. The following are the various built-in visual styles for `SfDatePicker` control.

* Blend
* Lime
* MaterialDark
* MaterialDarkBlue
* MaterialLight
* MaterialLightBlue
* Metro
* Office2010Black
* Office2010Blue
* Office2010Silver
* Office2013DarkGray
* Office2013LightGray
* Office2013White
* Office2016Colorful
* Office2016DarkGray
* Office2016White
* Office2019Black
* Office2019Colorful
* Office365
* Saffron
* VisualStudio2013
* VisualStudio2015

{% tabs %}
{% highlight XAML %}

<Window>
    <!--Theme Namespace-->
    xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF">
    <Grid>
        <syncfusion:SfDatePicker syncfusionskin:SfSkinManager.VisualStyle="MaterialDark" 
                                 Name="sfDatePicker" />
    </Grid>
</Window>

{% endhighlight %}
{% highlight C# %}

//Namespace for the SfSkinManager.
using Syncfusion.SfSkinManager;

SfDatePicker sfDatePicker = new SfDatePicker();
SfSkinManager.SetVisualStyle(sfDatePicker, VisualStyles.MaterialDark);

{% endhighlight %}
{% endtabs %}

![SfDatePicker with MaterialDark visual style](Appearance-and-Styling_images/Theme.png)

Here, the `MaterialDark` style is applied to the `SfDatePicker`.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/Themes)