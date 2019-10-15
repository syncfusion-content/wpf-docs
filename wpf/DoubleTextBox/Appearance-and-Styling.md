---
layout: post
title: Appearance and Style | DoubleTextBox | WPF | Syncfusion
description: Appearance represents the customization of the Foreground, WatermarkText, CornerRadius, RangeAdoner and VisualStyle supports.
platform: wpf
control: DoubleTextBox
documentation: ug
---

# Appearance

## Foreground

### Positive foreground

DoubleTextBox allows to apply the different brush for the positive values using the [PositiveForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~PositiveForeground.html) property. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Value="10" Width="100" Height="25"
                          PositiveForeground="DeepPink" EnableFocusColors ="True"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.Value = 10;
doubleTextBox.EnableFocusColors = true;
doubleTextBox.PositiveForeground = Brushes.DeepPink;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.Value = 10
doubleTextBox.EnableFocusColors = true

doubleTextBox.PositiveForeground = Brushes.DeepPink

{% endhighlight %}

{% endtabs %}

![Positive foreground](Appearance-and-Styling-images/Appearance-and-Styling-img1.jpeg)


### Negative foreground

DoubleTextBox allows to apply the different brush as a foreground for the negative values using the [NegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~NegativeForeground.html) property. 

N> It can be enable by setting [ApplyNegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyNegativeForeground.html) property to true. By default its value is false.

### Default Negative foreground

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Value="-10" Width="100" Height="25"
                          ApplyNegativeForeground="True"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.Value = -10;
doubleTextBox.ApplyNegativeForeground = true;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.Value = -10
doubleTextBox.ApplyNegativeForeground = True

{% endhighlight %}

{% endtabs %}

![Default Negative foreground](Appearance-and-Styling-images/Appearance-and-Styling-img10.png)


### Customized Negative foreground

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Value="-10" Width="100" Height="25"
                          NegativeForeground="DarkOrange" ApplyNegativeForeground="True"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.Value = -10;
doubleTextBox.ApplyNegativeForeground = true;
doubleTextBox.NegativeForeground = Brushes.DarkOrange;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.Value = -10
doubleTextBox.ApplyNegativeForeground = True
doubleTextBox.NegativeForeground = Brushes.DarkOrange

{% endhighlight %}

{% endtabs %}

![Customized Negative foreground](Appearance-and-Styling-images/Appearance-and-Styling-img2.jpeg)

## Zero color

The [Foreground](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_Control_Foreground) of the DoubleTextBox can be customized based on the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property. When zero is assigned as a value to a [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property, then automatically the [ZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ZeroColor.html) is set to the Foreground property.

N> The [ZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ZeroColor.html) in the DoubleTextBox can be enabled by setting the [ApplyZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyZeroColor.html) property to true.


###  Default ZeroColor

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="0" ApplyZeroColor="True"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.Value = 0;
doubleTextBox.ApplyZeroColor = true;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.Value = 0
doubleTextBox.ApplyZeroColor = True

{% endhighlight %}
{% endtabs %}

![Default ZeroColor](Appearance-and-Styling-images/Appearance-and-Styling-img11.png)


###  Customized ZeroColor

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="0" ApplyZeroColor="True"
                          ZeroColor="Blue"/>

{% endhighlight %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.ApplyZeroColor = true;
doubleTextBox.ZeroColor = Brushes.Blue;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.ApplyZeroColor = True
doubleTextBox.ZeroColor = Brushes.Blue

{% endhighlight %}
{% endtabs %}

![Customized ZeroColor](Appearance-and-Styling-images/Appearance-and-Styling-img5.jpeg)


## Background

DoubleTextBox allows different brushes to fill the control.The `Background` property can be used to modify the control background color.

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

{% highlight VB %}

Dim doubleTextBox As DoubleTextBox =  New DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.Background = Brushes.Cyan

{% endhighlight %}
{% endtabs %}

![Background](Appearance-and-Styling-images/Appearance-and-Styling-Background.png)

## CornerRadius

To rounded the corners of the DoubleTexBox, set the property [CornerRadius](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~CornerRadius.html) with the desired values. This property has no default value.

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

![Corner radius](Appearance-and-Styling-images/Appearance-and-Styling-img7.jpeg)


## Theme

The appearance of the DoubleTextBox control can be customized by using the VisualStyle property. The following are the various built-in visual styles for DoubleTextBox control.

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

For example, the blend style applied for the DoubleTextBox as shown in the following code example:

{% tabs %}

{% highlight XAML %}

<Window x:Class="WpfApplication4.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
syncfusion:SkinStorage.VisualStyle="Blend"
Title="MainWindow" Height="350" Width="525">
<Grid x:Name="Grid1">
<syncfusion:DoubleTextBox x:Name="DoubleTextBox1" Width="100" Height="25"/>
</Grid>

{% endhighlight %}

{% highlight C# %}

SkinStorage.SetVisualStyle(this, "Blend");

{% endhighlight %}

{% highlight VB %}

SkinStorage.SetVisualStyle(this, "Blend")

{% endhighlight %}

{% endtabs %}

![Double text box visual style](Appearance-and-Styling-images/Appearance-and-Styling-img8.jpeg)
