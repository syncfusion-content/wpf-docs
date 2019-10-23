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

### Positive Foreground

We can change a positive color to the value of `DoubleTextBox` by setting the [PositiveForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~PositiveForeground.html) property and it will be applied when the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) is positive. The default color of `PositiveForeground` is `Black`.

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

![DoubleTextBox Positive value Color](Appearance-and-Styling-images/Appearance-and-Styling-img5.jpeg)


### Negative Foreground 

We can change a negative color to the value of `DoubleTextBox` by setting the [NegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~NegativeForeground.html) property and it will be applied when the [ApplyNegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyNegativeForeground.html) property is `true` and the `Value` is negative. The default color of `NegativeForeground` is `Red`.

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

![DoubleTextBox Negative value color](Appearance-and-Styling-images/Appearance-and-Styling-img2.jpeg)


### Zero Foreground 

We can change a zero color to the value of `DoubleTextBox` by setting the [ZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ZeroColor.html) property and it will be applied when the [ApplyZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyZeroColor.html) property is `true` and the `Value` is zero.
The default color of `ZeroColor` is `Green`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Value="10" Width="100" Height="25"
                          ApplyZeroColor="True" ZeroColor="DarkGoldenrod"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.ApplyZeroColor = true;
doubleTextBox.ZeroColor = Brushes.DarkGoldenrod;

{% endhighlight %}
{% endtabs %}

![DoubleTextBox Zero value Color](Appearance-and-Styling-images/Appearance-and-Styling-img1.jpeg)

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

![DoubleTextBox Background](Appearance-and-Styling-images/Appearance-and-Styling-Background.png)

## Setting the Corner Radius

Corner Radius indicates the degree to which the corners of the border can be rounded. To create curved borders for the `DoubleTextBox`, use [CornerRadius](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~CornerRadius.html) property. The default value of `CornerRadius` property is 1.

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

![Corner radius of DoubleTextBox](Appearance-and-Styling-images/Appearance-and-Styling-img7.jpeg)


## Theme

The appearance of the `DoubleTextBox` control can be customized by using the [VisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.SkinStorage~SetVisualStyle.html) property. The following are the various built-in visual styles for `DoubleTextBox` control.

* Blend
* Office2003
* Office2007Blue
* Office2007Black
* Office2007Silver
* ShinyBlue
* ShinyRed
* SyncOrange
* VS2010
* Metro
* Transparent

For example, the `Blend` style applied to the `DoubleTextBox` as shown in the following example code:

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="DoubleTextBox1" Width="100" Height="25" syncfusion:SkinStorage.VisualStyle="Blend"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
SkinStorage.SetVisualStyle(doubleTextBox, "Blend");

{% endhighlight %}
{% endtabs %}

![DoubleTextBox Blend visual style](Appearance-and-Styling-images/Appearance-and-Styling-img8.jpeg)
