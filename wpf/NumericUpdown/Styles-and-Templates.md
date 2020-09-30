---
layout: post
title: Styles and Templates of WPF UpDown control | Syncfusion
description: This section describes about how to change the background and foreground color in WPF UpDown control.
platform: wpf
control: UpDown
documentation: ug
---

# Styles and Templates


The background and foreground of the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html) control can be customized by editing its style or by using the properties exposed by the `UpDown` control.


## Positive color

The background and foreground for the positive value can be customized using the `Background` and `Foreground` properties of the UpDown control.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Background="MediumBlue" Foreground="White" Value="10" Height="23"  Width="100" />

{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();
updown.Height = 23;
updown.Width = 100;
updown.Value = 10;
updown.Background = Brushes.MediumBlue;
updown.Foreground = Brushes.White;
grid.Children.Add(updown);

{% endhighlight %}

{% endtabs %}

![Applied background and forecolor to positive value in WPF UpDown](StylesandTemplates-images/wpf-updown-positive.png)

## Negative color

The background and foreground for the negative value can be customized using the [NegativeBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_NegativeBackground) and [NegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_NegativeForeground) properties of UpDown control. The `NegativeBackground` and `NegativeForeground` properties are enabled by setting the [EnableNegativeColors](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_EnableNegativeColors) property is set to `True`.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" EnableNegativeColors="True" NegativeBackground="Yellow" NegativeForeground="BlueViolet" Value="-2" Height="23"  Width="100" />

{% endhighlight %}

{% highlight C# %}

updown.Value = -2;
updown.EnableNegativeColors = true;
updown.NegativeBackground = Brushes.Yellow;
updown.NegativeForeground = Brushes.BlueViolet;

{% endhighlight %}

{% endtabs %}

![Applied background and forecolor to positive value in WPF UpDown](StylesandTemplates-images/wpf-updown-negative.png)

## Zero color

The color of zero value can be changed by using the [ZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_ZeroColor) property. The `ZeroColor` property can be enabled by setting the [ApplyZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_ApplyZeroColor) property is set to `True`.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" ApplyZeroColor="True" ZeroColor="DarkViolet" Value="0" Height="23"  Width="100" />

{% endhighlight %}

{% highlight C# %}

updown.ApplyZeroColor = true;
updown.ZeroColor = Brushes.DarkViolet;

{% endhighlight %}

{% endtabs %}

![Applied color to zero value in WPF UpDown](StylesandTemplates-images/wpf-updown-zero.png)

## Focused color

The background, foreground and border color for the UpDown control can be customized using the [FocusedBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_FocusedBackground), [FocusedBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_FocusedBorderBrush) and [FocusedForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_FocusedForeground) property when the control get focused. These properties are enabled by setting the [EnableFocusedColors](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_EnableFocusedColors) property is set to `True`.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" EnableFocusedColors="True" FocusedBackground="BurlyWood" FocusedForeground="White" FocusedBorderBrush="Green" Value="10" Height="23"  Width="100" />

{% endhighlight %}

{% highlight C# %}

updown.Value = 10;
updown.EnableFocusedColors = true;
updown.FocusedBackground = Brushes.BurlyWood;
updown.FocusedForeground = Brushes.White;
updown.FocusedBorderBrush = Brushes.Green;

{% endhighlight %}

{% endtabs %}

![Applied color to focused value in WPF UpDown](StylesandTemplates-images/wpf-updown-focused.png)

N> The positive, negative and zero value colors get default color of the control while focusing the Updown control.

## Visual styles

The skins can be applied to the UpDown control by setting the `VisualStyle` property defined in SkinStorage class, refer [here](https://help.syncfusion.com/wpf/skinmanager/overview).

Below example explains how to apply the `Blend` theme or style for `UpDown` control.

1) Add the following reference **Syncfusion.Shared.WPF.dll**.

2) Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** or add namespace **Syncfusion.Windows.Shared** and set `SkinStorage.VisualStyle` attached property to window or UpDown.

{% tabs %}

{% highlight XAML %}

<Window x:Class="Application_New.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:shared="clr-namespace:Syncfusion.Windows.Tools.Controls;assembly=Syncfusion.Shared.Wpf"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
syncfusion:SkinStorage.VisualStyle="Blend"
Title="MainWindow" Height="350" Width="525">

<Grid x:Name="grid">
    <syncfusion:UpDown x:Name="upDown" Width="100" Height="23"/>
</Grid>

</Window>

{% endhighlight %}

{% highlight C# %}

SkinStorage.SetVisualStyle(updown, "Blend");

{% endhighlight %}

{% endtabs %}

![Applied Blend style into WPF UpDown](StylesandTemplates-images/wpf-updown-blendstyle.jpeg)


