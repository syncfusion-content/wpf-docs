---
layout: post
title: Appearance in WPF Currency TextBox control | Syncfusion
description: Learn about Appearance support in Syncfusion WPF Currency TextBox control, its elements and more details.
platform: wpf
control: CurrencyTextBox
documentation: ug
---

# Appearance in WPF Currency TextBox

This section deals with the appearance of `CurrencyTextBox` control and contains the following topics.

## Setting the Foreground

The [CurrencyTextBox](https://www.syncfusion.com/wpf-ui-controls/currency-textbox) control [Foreground](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?view=netframework-4.8) can be modified based on the value of the control. The following are the foreground for `CurrencyTextBox` control.

### Foreground for Positive Value

We can change a positive color for the value of `CurrencyTextBox` by setting the [PositiveForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_PositiveForeground) property and it will be applied when the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_Value) is positive. The default color of `PositiveForeground` is `Black`.

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Value="10" Width="100" Height="25" PositiveForeground="Blue" />

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.Value = 10;
currencyTextBox.PositiveForeground = Brushes.Blue;

{% endhighlight %}
{% endtabs %}

![Changing Positive Value Color in WPF CurrencyTextBox](Appearance_images/wpf-currency-textbox-positive-color.png)

### Foreground for Negative Value

We can change a negative color for the value of `CurrencyTextBox` by setting the [NegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_NegativeForeground) property and it will be applied when the [ApplyNegativeForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ApplyNegativeForeground) property is `true` and the `Value` is negative. The default color of `NegativeForeground` is `Red`.

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Value="-10" Width="100" Height="25"
                          NegativeForeground="SpringGreen" ApplyNegativeForeground="True" />

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.Value = -10;
currencyTextBox.ApplyNegativeForeground = true;   
currencyTextBox.NegativeForeground = Brushes.SpringGreen;

{% endhighlight %}
{% endtabs %}

![Changing Negative Value Color in WPF CurrencyTextBox](Appearance_images/wpf-currency-textbox-negative-color.png)

### Foreground for Zero Value

We can change a zero color for the value of `CurrencyTextBox` by setting the [ZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ZeroColor) property and it will be applied when the [ApplyZeroColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_ApplyZeroColor) property is `true` and the `Value` is zero.
The default color of `ZeroColor` is `Green`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Value="0" Width="100" Height="25"
                          ApplyZeroColor="True" ZeroColor="DarkGoldenrod"/>

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.Value = 0;
currencyTextBox.ApplyZeroColor = true;
currencyTextBox.ZeroColor = Brushes.DarkGoldenrod;

{% endhighlight %}
{% endtabs %}

![Changing Zero Value Color in WPF CurrencyTextBox](Appearance_images/wpf-currency-textbox-zero-color.png)

## Setting the Background

`CurrencyTextBox` allows different brushes to fill the control. The [Background](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.background?view=netframework-4.8) property can be used to modify the control background color. The default color of `Background` is `White`.

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Width="100"
                          Height="25" Value ="80" Background="Cyan"/>

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.Background = Brushes.Cyan;

{% endhighlight %}
{% endtabs %}

![WPF CurrencyTextBox with Cyan Bbackground](Appearance_images/wpf-currency-textbox-background.png)

## Setting the Corner Radius

Corner Radius indicates the degree to which the corners of the border can be rounded. To create curved borders for the `CurrencyTextBox`, use [CornerRadius](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_CornerRadius) property. The default value of `CornerRadius` property is 1.

{% tabs %}

{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Width="100" Height="25" CornerRadius="5"/>

{% endhighlight %}

{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.CornerRadius = new CornerRadius(5);  

{% endhighlight %}
{% endtabs %}

![WPF CurrencyTextBox with Corner Radius](Appearance_images/wpf-currency-textbox-corner-radius.png)

## Apply Background for Selection

`CurrencyTextBox` allows different brushes to highlight the selected text by setting the [SelectionBrush](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionbrush?view=netframework-4.8) and [SelectionOpacity](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.selectionopacity?view=netframework-4.8) properties. The `SelectionOpacity` property specifies the opacity of the `SelectionBrush`.

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Width="100" Height="25" SelectionBrush="Red" SelectionOpacity="0.5"/>

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.SelectionBrush = Brushes.Red;
currencyTextBox.SelectionOpacity = 0.3;

{% endhighlight %}
{% endtabs %}

![WPF CurrencyTextBox with Red Selection Background](Appearance_images/wpf-currency-textbox-selection.png)

## Align Value

`CurrencyTextBox` allows to display the value from right or center or left side by setting the [TextAlignment](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.textblock.textalignment?view=netframework-4.8) property to `Right` or `Left` or `Center`. The Default value of `TextAlignment` is `Left`.

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Width="100" Height="25" TextAlignment="Center"/>

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.TextAlignment = TextAlignment.Center;

{% endhighlight %}
{% endtabs %}

![Changing Text Alignment of WPF CurrencyTextBox](Appearance_images/wpf-currency-textbox-text-alignment.png)

## Setting ToolTip

`CurrencyTextBox` provides support for ToolTip to display certain information when the mouse hovers on the `CurrencyTextBox`. You can customize the tooltip information by setting the [ToolTip](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.tooltip?view=netframework-4.8) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Width="100" Height="25" ToolTip="Enter Currency Value"/>

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.ToolTip = "Enter Currency Value";

{% endhighlight %}
{% endtabs %}

![WPF CurrencyTextBox with ToolTip](Appearance_images/wpf-currency-textbox-tooltip.png)

## Theme

CurrencyTextBox supports various built-in themes. Refer to the below links to apply themes for the CurrencyTextBox,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

 ![Applying Theme to WPF CurrencyTextBox](Getting-Started_images/wpf-currency-textbox-theme.png)
