---
layout: post
title: Appearance in WPF DoubleTextBox | Syncfusion®
description: Customize the look and feel of the Syncfusion WPF DoubleTextBox control using built-in themes, custom templates, and styling options.
platform: wpf
control: DoubleTextBox
documentation: ug
---

# Appearance in WPF Double TextBox

This section deals with the appearance of `WPF Double TextBox` control and contains the following topics.

## Setting the Foreground

The foreground of the [WPF Double TextBox](https://www.syncfusion.com/wpf-controls/double-textbox) control can be modified based on the value of the control by using the [Foreground](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?view=netframework-4.8) and the value-specific brushes described below.

### Foreground for Positive Value

You can change the foreground color applied to positive values of `WPF Double TextBox` by setting the [PositiveForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_PositiveForeground) property. It is applied when the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_Value) is positive. The default color of `PositiveForeground` is `Black`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Value="10" Width="100" Height="25" PositiveForeground="Blue" />

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.PositiveForeground = Brushes.Blue;

{% endhighlight %}
{% endtabs %}

![Changing Positive Value Color in WPF DoubleTextBox](Appearance-and-Styling-images/wpf-double-textbox-positive-value.jpeg)

### Foreground for Negative Value

You can change the foreground color applied to negative values of `WPF Double TextBox` by setting the [NegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_NegativeForeground) property. It is applied when the [ApplyNegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ApplyNegativeForeground) property is `true` and the `Value` is negative. The default color of `NegativeForeground` is `Red`. The default value of `ApplyNegativeForeground` is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Value="10" Width="100" Height="25"
                          NegativeForeground="SpringGreen" ApplyNegativeForeground="True" />

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.ApplyNegativeForeground = true;   
doubleTextBox.NegativeForeground = Brushes.SpringGreen;

{% endhighlight %}
{% endtabs %}

![Changing Negative Value Color in WPF DoubleTextBox](Appearance-and-Styling-images/wpf-double-textbox-negative-value.jpeg)

### Foreground for Zero Value

You can change the foreground color applied when the `Value` of `WPF Double TextBox` is zero by setting the [ZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ZeroColor) property. It is applied when the [ApplyZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ApplyZeroColor) property is `true` and the `Value` is zero. The default value of `ApplyZeroColor` is `true`. The default color of `ZeroColor` is `Green`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Value="0" Width="100" Height="25"
                          ApplyZeroColor="True" ZeroColor="DarkGoldenrod"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Value = 0;
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.ApplyZeroColor = true;
doubleTextBox.ZeroColor = Brushes.DarkGoldenrod;

{% endhighlight %}
{% endtabs %}

![Changing Zero Value Color in WPF DoubleTextBox](Appearance-and-Styling-images/wpf-double-textbox-zero-value.jpeg)

## Setting the Background

`WPF Double TextBox` allows different brushes to fill the control. The [Background](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.control.background?view=netframework-4.8) property can be used to modify the control background color. The default color of `Background` is `White`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100"
                          Height="25" Value ="80" Background="Cyan"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.Background = Brushes.Cyan;

{% endhighlight %}
{% endtabs %}

![WPF DoubleTextBox with Cyan Background](Appearance-and-Styling-images/wpf-double-textbox-background.png)

## Setting the Corner Radius

Corner Radius indicates the degree to which the corners of the border can be rounded. To create curved borders for the `WPF Double TextBox`, use the [CornerRadius](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_CornerRadius) property. The default value of `CornerRadius` is 1.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="DoubleTextBox1" Width="100" Height="25" CornerRadius="5"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;
using System.Windows;

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.CornerRadius = new CornerRadius(5);

{% endhighlight %}
{% endtabs %}

![WPF DoubleTextBox with Corner Radius](Appearance-and-Styling-images/wpf-double-textbox-corner-radius.jpeg)

## Apply Background for Selection

`WPF Double TextBox` allows different brushes to highlight the selected text by setting the [SelectionBrush](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionbrush?view=netframework-4.8) and [SelectionOpacity](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionopacity?view=netframework-4.8) properties. The `SelectionOpacity` property specifies the opacity of the `SelectionBrush`. The default value of `SelectionOpacity` is `0.4`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100" Height="25" SelectionBrush="Red" SelectionOpacity="0.5"/>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;
using System.Windows.Media;

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.SelectionBrush = Brushes.Red;
doubleTextBox.SelectionOpacity = 0.5;

{% endhighlight %}
{% endtabs %}

![Highlighting Selected Text Background in WPF DoubleTextBox](Appearance-and-Styling-images/wpf-double-textbox-selection.png)

## Align Value

`WPF Double TextBox` allows you to display the value from the right, center, or left side by setting the [TextAlignment](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.textblock.textalignment?view=netframework-4.8) property to `Right`, `Left`, or `Center`. The default value of `TextAlignment` is `Left`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100" Height="25" TextAlignment="Center"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.TextAlignment = TextAlignment.Center;

{% endhighlight %}
{% endtabs %}

![Changing Text Alignment of WPF DoubleTextBox](Appearance-and-Styling-images/wpf-double-textbox-text-alignment.png)

## Setting ToolTip

`WPF Double TextBox` provides support for a ToolTip to display certain information when the mouse hovers over the control. You can customize the tooltip information by setting the [ToolTip](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.tooltip?view=netframework-4.8) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100" Height="25" ToolTip="Enter Double Value"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.ToolTip = "Enter Double value";

{% endhighlight %}
{% endtabs %}

![WPF DoubleTextBox with ToolTip](Appearance-and-Styling-images/wpf-double-textbox-tooltip.png)

## Theme

The WPF Double TextBox supports various built-in themes. Refer to the links below to apply themes,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Applying Theme to WPF DoubleTextBox](Getting-Started_images/wpf-double-textbox-theme.png)
