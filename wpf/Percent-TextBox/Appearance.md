---
layout: post
title: Appearance in WPF Percent TextBox control | Syncfusion®
description: Learn about Appearance support in Syncfusion® Essential Studio® WPF Percent TextBox control, its elements and more.
platform: WPF
control: PercentTextBox
documentation: ug
---

# Appearance in WPF Percent TextBox

This section deals with the appearance of `PercentTextBox` control and contains the following topics.

## Setting the Foreground

The [PercentTextBox](https://www.syncfusion.com/wpf-ui-controls/percent-textbox) control [Foreground](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?view=netframework-4.8) can be modified based on the percent value of the control. The following are the foreground for `PercentTextBox` control.

### Foreground for Positive Value

You can change the color for positive percent values of `PercentTextBox` by setting the [PositiveForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_PositiveForeground) property; it will be applied when the [PercentValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_PercentValue) is positive. The default color of `PositiveForeground` is `Black`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100" Height="25" PercentValue = "10" PositiveForeground="Blue" />

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.PercentValue = 10;
percentTextBox.PositiveForeground = Brushes.Blue;

{% endhighlight %}
{% endtabs %}

![Changing Positive Value Color in WPF PercentTextBox](Appearance_images/wpf-percent-textbox-positive-color.png)

### Foreground for Negative Value

You can change the color for negative percent values of `PercentTextBox` by setting the [NegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_NegativeForeground) property; it will be applied when the [ApplyNegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ApplyNegativeForeground) property is `true` and the `PercentValue` is negative. The default color of `NegativeForeground` is `Red`. The default value of `ApplyNegativeForeground` is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100" Height="25" PercentValue="-10"
                          NegativeForeground="SpringGreen" ApplyNegativeForeground="True" />

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.PercentValue = -10;
percentTextBox.ApplyNegativeForeground = true;   
percentTextBox.NegativeForeground = Brushes.SpringGreen;

{% endhighlight %}
{% endtabs %}

![Changing Negative Value Color in WPF PercentTextBox](Appearance_images/wpf-percent-textbox-negative-color.png)

### Foreground for Zero Value

You can change the color for zero percent values of `PercentTextBox` by setting the [ZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ZeroColor) property; it will be applied when the [ApplyZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ApplyZeroColor) property is `true` and the `PercentValue` is zero. The default color of `ZeroColor` is `Green`. The default value of `ApplyZeroColor` is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" PercentValue="0" Width="100" Height="25"
                          ApplyZeroColor="True" ZeroColor="DarkGoldenrod"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.PercentValue = 0;
percentTextBox.ApplyZeroColor = true;
percentTextBox.ZeroColor = Brushes.DarkGoldenrod;

{% endhighlight %}
{% endtabs %}

![Changing Zero Color in WPF PercentTextBox](Appearance_images/wpf-percent-textbox-zero-color.png)

## Setting the Background

`PercentTextBox` allows different brushes to fill the control. The [Background](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.background?view=netframework-4.8) property can be used to modify the control background color. The default color of `Background` is `White`.

> The C# sample below requires the `using System.Windows.Media;` namespace for `Brushes`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100"
                          Height="25" Background="Cyan"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.Background = Brushes.Cyan;

{% endhighlight %}
{% endtabs %}

![WPF PercentTextBox with Cyan Background](Appearance_images/wpf-percent-textbox-background.png)

## Setting the Corner Radius

Corner Radius indicates the degree to which the corners of the border can be rounded. To create curved borders for the `PercentTextBox`, use the [CornerRadius](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_CornerRadius) property. The default value of the `CornerRadius` property is 1.

> The C# sample below requires the `using System.Windows;` namespace for the `CornerRadius` struct.

{% tabs %}

{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100" Height="25" CornerRadius="5"/>

{% endhighlight %}

{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.CornerRadius = new CornerRadius(5);  

{% endhighlight %}
{% endtabs %}

![WPF PercentTextBox with Corner Radius](Appearance_images/corner-radius.png)

## Apply Background for Selection

`PercentTextBox` allows different brushes to highlight the selected text by setting the [SelectionBrush](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionbrush?view=netframework-4.8) and [SelectionOpacity](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionopacity?view=netframework-4.8) properties. The `SelectionOpacity` property specifies the opacity of the `SelectionBrush`.

> The C# sample below requires the `using System.Windows.Media;` namespace for `Brushes`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100" Height="25" SelectionBrush="Red" SelectionOpacity="0.5"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.SelectionBrush = Brushes.Red;
percentTextBox.SelectionOpacity = 0.5;

{% endhighlight %}
{% endtabs %}

![WPF PercentTextBox with Red Selection Background](Appearance_images/wpf-percent-textbox-selection-background.png)

## Aligning the Value

`PercentTextBox` allows you to display the value on the right, left, or center by setting the [TextAlignment](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.textblock.textalignment?view=netframework-4.8) property to `Right`, `Left`, or `Center`. The default value of `TextAlignment` is `Left`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100" Height="25" TextAlignment="Center"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.TextAlignment = TextAlignment.Center;

{% endhighlight %}
{% endtabs %}

![Changing Text Alignment of WPF PercentTextBox](Appearance_images/wpf-percent-textbox-text-alignment.png)

## Setting ToolTip

`PercentTextBox` provides support for ToolTip to display certain information when the mouse hovers on the `PercentTextBox`. You can customize the tooltip information by setting the [ToolTip](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.tooltip?view=netframework-4.8) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100" Height="25" ToolTip="Enter Percentage Value"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.ToolTip = "Enter Percentage value";

{% endhighlight %}
{% endtabs %}

![WPF PercentTextBox with ToolTip](Appearance_images/wpf-percent-textbox-tooltip.png)

## Theme

PercentTextBox supports various built-in themes. Refer to the below links to apply themes for the PercentTextBox,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)
  
  ![Applying Theme to WPF PercentTextBox](Getting-Started_images/wpf-percent-textbox-theme.png)

