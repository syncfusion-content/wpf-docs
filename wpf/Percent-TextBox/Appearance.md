---
layout: post
title: Appearance in WPF Percent TextBox control | Syncfusion
description: Learn about Appearance support in Syncfusion WPF Percent TextBox control and more.
platform: wpf
control: PercentTextBox
documentation: ug
---

# Appearance in WPF Percent TextBox

This section deals with the appearance of `PercentTextBox` control and contains the following topics.

## Setting the Foreground

The [PercentTextBox](https://www.syncfusion.com/wpf-ui-controls/percent-textbox) control [Foreground](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?view=netframework-4.8) can be modified based on the percent value of the control. The following are the foreground for `PercentTextBox` control.

### Foreground for Positive Value

We can change a positive color for the percent value of `PercentTextBox` by setting the [PositiveForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_PositiveForeground) property and it will be applied when the [PercentValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PercentTextBox.html#Syncfusion_Windows_Shared_PercentTextBox_PercentValue) is positive. The default color of `PositiveForeground` is `Black`.

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

![PercentTextBox displaying value in positive foreground](Appearance_images/positive-foreground.png)

### Foreground for Negative Value

We can change a negative color for the value of `PercentTextBox` by setting the [NegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_NegativeForeground) property and it will be applied when the [ApplyNegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ApplyNegativeForeground) property is `true` and the `PercentValue` is negative. The default color of `NegativeForeground` is `Red`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" PercentValue="10" Width="100" Height="25" PercentValue = "-10" 
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

![PercentTextBox displaying negative value in negative foreground](Appearance_images/negative-foreground.png)

### Foreground for Zero Value

We can change a zero color for the percent value of `PercentTextBox` by setting the [ZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ZeroColor) property and it will be applied when the [ApplyZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ApplyZeroColor) property is `true` and the `PercentValue` is zero.
The default color of `ZeroColor` is `Green`. 

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

![PercentTextBox displaying zero value with zero foreground](Appearance_images/zero-foreground.png)

## Setting the Background

`PercentTextBox` allows different brushes to fill the control. The [Background](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.background?view=netframework-4.8) property can be used to modify the control background color. The default color of `Background` is `White`.

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

![PercentTextBox with cyan background](Appearance_images/background.png)

## Setting the Corner Radius

Corner Radius indicates the degree to which the corners of the border can be rounded. To create curved borders for the `PercentTextBox`, use [CornerRadius](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_CornerRadius) property. The default value of `CornerRadius` property is 1.

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

![PercentTextBox with corner radius](Appearance_images/corner-radius.png)

## Apply Background for Selection

`PercentTextBox` allows different brushes to highlight the selected text by setting the [SelectionBrush](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionbrush?view=netframework-4.8) and [SelectionOpacity](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionopacity?view=netframework-4.8) properties. The `SelectionOpacity` property specifies the opacity of the `SelectionBrush`.

{% tabs %}
{% highlight XAML %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100" Height="25" SelectionBrush="Red" SelectionOpacity="0.5"/>

{% endhighlight %}
{% highlight C# %}

PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 100;
percentTextBox.Height = 25;
percentTextBox.SelectionBrush = Brushes.Red;
percentTextBox.SelectionOpacity = 0.3;

{% endhighlight %}
{% endtabs %}

![PercentTextBox with red selection background](Appearance_images/Selection.png)

## Align Value

`PercentTextBox` allows to display the value from right or center or left side by setting the [TextAlignment](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.textblock.textalignment?view=netframework-4.8) property to `Right` or `Left` or `Center`. The Default value of `TextAlignment` is `Left`.

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

![Center aligned PercentTextBox Value](Appearance_images/TextAlignment.png)

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

![PercentTextBox with tool tip](Appearance_images/ToolTip.png)

## Theme

PercentTextBox supports various built-in themes. Refer to the below links to apply themes for the PercentTextBox,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)
  
  ![Setting theme to WPF PercentTextBox control ](Getting-Started_images/Theme.png)

