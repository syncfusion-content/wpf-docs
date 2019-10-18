---
layout: post
title: Appearance in WPF DoubleTextBox control | Syncfusion
description: Learn about Appearance support in Syncfusion WPF DoubleTextBox control and more details about the control features.
platform: wpf
control: DoubleTextBox
documentation: ug
---

# Appearance in WPF DoubleTextBox

## Setting the Foreground

The `DoubleTextBox` control [Foreground](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?view=netframework-4.8) can be modified based on the value of the control. The following are the foreground for `DoubleTextBox` control.

* Positive foreground - We can add and change a positive color to the value of `DoubleTextBox` by setting the [PositiveForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~PositiveForeground.html) property and it will be applied when the `Value` is positive. The default color of `PositiveForeground` is `Black`.

* Negative foreground - We can add and change a negative color to the value of `DoubleTextBox` by setting the [NegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~NegativeForeground.html) property and it will be applied when the [ApplyNegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyNegativeForeground.html) property is `true` and the `Value` is negative. The default color of `NegativeForeground` is `Red`.

* Zero foreground - We may add and change a zero color to the value of `DoubleTextBox` by setting the [ZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ZeroColor.html) property and it will be applied when the [ApplyZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyZeroColor.html) property is `true` and the `Value` is zero.
The default color of `ZeroColor` is `Green`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Value="10" Width="100" Height="25"
                          PositiveForeground="Blue"
                          NegativeForeground="SpringGreen" ApplyNegativeForeground="True"
                          ApplyZeroColor="True" ZeroColor="DarkGoldenrod"/>

{% endhighlight %}
{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.Value = 10;
doubleTextBox.PositiveForeground = Brushes.Blue;            doubleTextBox.ApplyNegativeForeground = true;            doubleTextBox.NegativeForeground = Brushes.SpringGreen;           doubleTextBox.ApplyZeroColor = true;            doubleTextBox.ZeroColor = Brushes.DarkGoldenrod;

{% endhighlight %}
{% endtabs %}

**PositiveForeground = "Blue"**

![DoubleTextBox Positive foreground](Appearance-and-Styling-images/Appearance-and-Styling-img1.jpeg)

**NegativeForeground = "SpringGreen"**

![DoubleTextBox Negative foreground](Appearance-and-Styling-images/Appearance-and-Styling-img2.jpeg)

**ZeroColor = "DarkGoldenrod"**

![DoubleTextBox ZeroColor](Appearance-and-Styling-images/Appearance-and-Styling-img5.jpeg)


## Setting the Background

`DoubleTextBox` allows different brushes to fill the control. The [Background](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.background?view=netframework-4.8) property can be used to modify the control background color. The default color of `Background` is `White`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100"
                          Height="25" Value ="80" Background="LightGreen"/>

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

To rounded the corners of the DoubleTexBox, set the property [CornerRadius](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~CornerRadius.html) with the desired values. The default value of `CornerRadius` property is 1.

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

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.CornerRadius = New CornerRadius(5)

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
