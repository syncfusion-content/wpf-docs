---
layout: post
title: Appearance in WPF DoubleTextBox control | Syncfusion
description: Learn about Appearance support in Syncfusion WPF DoubleTextBox control and more details about the control features.
platform: wpf
control: DoubleTextBox
documentation: ug
---

# Appearance in WPF DoubleTextBox

This section deals with the appearance of `DoubleTextBox` control and contains the following topics.

## Setting the Foreground

The [DoubleTextBox](https://www.syncfusion.com/wpf-ui-controls/double-textbox) control [Foreground](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?view=netframework-4.8) can be modified based on the value of the control. The following are the foreground for `DoubleTextBox` control.

### Foreground for Positive Value

We can change a positive color for the value of `DoubleTextBox` by setting the [PositiveForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_PositiveForeground) property and it will be applied when the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DoubleTextBox.html#Syncfusion_Windows_Shared_DoubleTextBox_Value) is positive. The default color of `PositiveForeground` is `Black`.

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

![DoubleTextBox displaying value in positive foreground](Appearance-and-Styling-images/Appearance-and-Styling-img5.jpeg)

### Foreground for Negative Value

We can change a negative color for the value of `DoubleTextBox` by setting the [NegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_NegativeForeground) property and it will be applied when the [ApplyNegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ApplyNegativeForeground) property is `true` and the `Value` is negative. The default color of `NegativeForeground` is `Red`.

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

![DoubleTextBox displaying negative value in negative foreground](Appearance-and-Styling-images/Appearance-and-Styling-img2.jpeg)

### Foreground for Zero Value

We can change a zero color for the value of `DoubleTextBox` by setting the [ZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ZeroColor) property and it will be applied when the [ApplyZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ApplyZeroColor) property is `true` and the `Value` is zero.
The default color of `ZeroColor` is `Green`. 

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

![DoubleTextBox displaying zero value with zero foreground](Appearance-and-Styling-images/Appearance-and-Styling-img1.jpeg)

## Setting the Background

`DoubleTextBox` allows different brushes to fill the control. The [Background](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.background?view=netframework-4.8) property can be used to modify the control background color. The default color of `Background` is `White`.

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

![DoubleTextBox with cyan background](Appearance-and-Styling-images/Appearance-and-Styling-Background.png)

## Setting the Corner Radius

Corner Radius indicates the degree to which the corners of the border can be rounded. To create curved borders for the `DoubleTextBox`, use [CornerRadius](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_CornerRadius) property. The default value of `CornerRadius` property is 1.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="DoubleTextBox1" Width="100" Height="25" CornerRadius="5"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.CornerRadius = new CornerRadius(5);  

{% endhighlight %}
{% endtabs %}

![DoubleTextBox with corner radius](Appearance-and-Styling-images/Appearance-and-Styling-img7.jpeg)

## Apply Background for Selection

`DoubleTextBox` allows different brushes to highlight the selected text by setting the [SelectionBrush](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionbrush?view=netframework-4.8) and [SelectionOpacity](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionopacity?view=netframework-4.8) properties. The `SelectionOpacity` property specifies the opacity of the `SelectionBrush`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100" Height="25" SelectionBrush="Red" SelectionOpacity="0.5"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.SelectionBrush = Brushes.Red;
doubleTextBox.SelectionOpacity = 0.3;

{% endhighlight %}
{% endtabs %}

![DoubleTextBox with red selection background](Appearance-and-Styling-images/Selection.png)

## Align Value

`DoubleTextBox` allows to display the value from right or center or left side by setting the [TextAlignment](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.textblock.textalignment?view=netframework-4.8) property to `Right` or `Left` or `Center`. The Default value of `TextAlignment` is `Left`.

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

![Center aligned DoubleTextBox Value](Appearance-and-Styling-images/TextAlignment.png)

## Setting ToolTip

`DoubleTextBox` provides support for ToolTip to display certain information when the mouse hovers on the `DoubleTextBox`. You can customize the tooltip information by setting the [ToolTip](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.tooltip?view=netframework-4.8) property.

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

![DoubleTextBox with tool tip](Appearance-and-Styling-images/ToolTip.png)

## Theme

DoubleTextBox supports various built-in themes. Refer to the below links to apply themes for the DoubleTextBox,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![DoubleTextBox Blend visual style](Appearance-and-Styling-images/Appearance-and-Styling-img8.jpeg)
