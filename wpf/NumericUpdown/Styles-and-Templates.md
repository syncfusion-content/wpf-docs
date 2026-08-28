---
layout: post
title: Styles and Templates in WPF UpDown | Syncfusion®
description: Customize the appearance of the Syncfusion WPF UpDown control using built-in styles and reusable control templates.
platform: wpf
control: UpDown
documentation: ug
---

# Styles and Templates in WPF UpDown

You can customize the background and foreground of the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html) control by editing its style or by setting the exposed properties.

## Positive color

You can customize the background and foreground for positive values using the `Background` and `Foreground` properties of the `UpDown` control.

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

![Changing Positive Value Color in WPF UpDown](StylesandTemplates-images/wpf-updown-positive.png)

## Negative color

You can customize the background and foreground for negative values using the [NegativeBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_NegativeBackground) and [NegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_NegativeForeground) properties of the `UpDown` control. The negative colors are enabled by setting [EnableNegativeColors](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_EnableNegativeColors) to `True`.

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

![Changing Negative Value Color in WPF UpDown](StylesandTemplates-images/wpf-updown-negative.png)

## Zero color

You can change the color of the zero value using the [ZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_ZeroColor) property. The zero color is enabled by setting [ApplyZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_ApplyZeroColor) to `True`.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" ApplyZeroColor="True" ZeroColor="DarkViolet" Value="0" Height="23"  Width="100" />

{% endhighlight %}

{% highlight C# %}

updown.ApplyZeroColor = true;
updown.ZeroColor = Brushes.DarkViolet;

{% endhighlight %}

{% endtabs %}

![Changing Zero Value Color in WPF UpDown](StylesandTemplates-images/wpf-updown-zero.png)

## Focused color

You can customize the background, foreground, and border color for the `UpDown` control while focused using the [FocusedBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_FocusedBackground), [FocusedBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_FocusedBorderBrush), and [FocusedForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_FocusedForeground) properties. These properties take effect only when [EnableFocusedColors](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_EnableFocusedColors) is `True`. The default value of `EnableFocusedColors` is `True`.

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

![Changing Focused Value Color in WPF UpDown](StylesandTemplates-images/wpf-updown-focused.png)

N> While the control is focused, the positive, negative, and zero colors revert to the default focus colors.

## Theme

UpDown supports various built-in themes. Refer to the below links to apply themes for the UpDown,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Applying Theme to WPF UpDown](GettingStarted-images/wpf-updown-theme.png)


