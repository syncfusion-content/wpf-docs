---
layout: post
title: Appearance and Style | DoubleTextBox | WPF | Syncfusion
description: Appearance and styling
platform: wpf
control: DoubleTextBox
documentation: ug
---

# Appearance and Styling

## Positive foreground

DoubleTextBox allows to apply the different brush for the positive values using the [PositiveForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~PositiveForeground.html) property. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Value="10" Width="100" Height="25"
                          PositiveForeground="DeepPink"/>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.Value = 10;
doubleTextBox.EnableFocusColors = true;
doubleTextBox.PositiveForeground = Brushes.DeepPink;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.Value = 10
doubleTextBox.EnableFocusColors = True
doubleTextBox.PositiveForeground = Brushes.DeepPink

{% endhighlight %}

{% endtabs %}

![Positive foreground](Appearance-and-Styling-images/Appearance-and-Styling-img1.jpeg)


## Negative foreground

DoubleTextBox allows to apply the different brush as a foreground for the negative values using the [NegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~NegativeForeground.html) property. 

N> It can be enable by setting [ApplyNegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyNegativeForeground.html) property to true. By default its value is false.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Value="-10" Width="100" Height="25"
                          NegativeForeground="DarkOrange" ApplyNegativeForeground="True"/>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.Value = -10;
doubleTextBox.ApplyNegativeForeground = true;
doubleTextBox.NegativeForeground = Brushes.DarkOrange;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.Value = -10
doubleTextBox.ApplyNegativeForeground = True
doubleTextBox.NegativeForeground = Brushes.DarkOrange

{% endhighlight %}

{% endtabs %}

![Negative foreground](Appearance-and-Styling-images/Appearance-and-Styling-img2.jpeg)


## WaterMark TextForeground

The DoubleTextBox allows to set the desired brush as the foreground for the WaterMarkText using [WaterMarkTextForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTextForeground.html).

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="100"
                          Height="25" UseNullOption="True" WatermarkText="Type here"
                          WatermarkTextIsVisible="True" WatermarkTextForeground="Red"/>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.UseNullOption = true;
doubleTextBox.WatermarkText = "Type Here";
doubleTextBox.WatermarkTextIsVisible = true;
doubleTextBox.WatermarkTextForeground = Brushes.Red;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.UseNullOption = True
doubleTextBox.WatermarkText = "Type Here"
doubleTextBox.WatermarkTextIsVisible = True
doubleTextBox.WatermarkTextForeground = Brushes.Red

{% endhighlight %}

{% endtabs %}

![WaterMark text foreground](Appearance-and-Styling-images/Appearance-and-Styling-img3.jpeg)


## Range adorner

To show the adorner range based on the minimum and maximum values, the [EnableRangeAdorner](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableRangeAdorner.html) property need to set to True. By Default its value is false.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25"
                          Value ="50" MaxValue="100" MinValue="10"
                          EnableRangeAdorner="True"/>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

DoubleTextBox doubleTextBox = new DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.Value = 50;
doubleTextBox.MinValue = 10;
doubleTextBox.MaxValue = 100;
doubleTextBox.EnableRangeAdorner = true;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.Value = 50
doubleTextBox.MinValue = 10
doubleTextBox.MaxValue = 100
doubleTextBox.EnableRangeAdorner = True

{% endhighlight %}

{% endtabs %}

![Range adorner](Appearance-and-Styling-images/Appearance-and-Styling-img9.jpeg)


## Range adorner background

The background color of the range adorner can be set using the [RangeAdornerBackground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~RangeAdornerBackground.html) property.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="50" MaxValue="100"
                          MinValue="10" RangeAdornerBackground="BlueViolet"
                          EnableRangeAdorner="True"/>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 50;
doubleTextBox.MinValue = 10;
doubleTextBox.MaxValue = 100;
doubleTextBox.EnableRangeAdorner = true;
doubleTextBox.RangeAdornerBackground = Brushes.BlueViolet;

{% endhighlight %}


{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 150
doubleTextBox.Height = 25
doubleTextBox.Value = 50
doubleTextBox.MinValue = 10
doubleTextBox.MaxValue = 100
doubleTextBox.EnableRangeAdorner = True
doubleTextBox.RangeAdornerBackground = Brushes.BlueViolet

{% endhighlight %}

{% endtabs %}

![Range adorner background](Appearance-and-Styling-images/Appearance-and-Styling-img4.jpeg)


## Zero color

The [Foreground](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_Control_Foreground) of the DoubleTextBox can be customized based on the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property. When zero is assigned as a value to a [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property, then automatically the [ZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ZeroColor.html) is set to the Foreground property.

N> The [ZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ZeroColor.html) in the DoubleTextBox can be enabled by setting the [ApplyZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyZeroColor.html) property to true.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150"
                          Height="25" Value ="0" ApplyZeroColor="True"
                          ZeroColor="Blue"/>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.ApplyZeroColor = true;
doubleTextBox.ZeroColor = Brushes.Blue;

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.ApplyZeroColor = True
doubleTextBox.ZeroColor = Brushes.Blue

{% endhighlight %}
{% endtabs %}

![Zero color](Appearance-and-Styling-images/Appearance-and-Styling-img5.jpeg)

## WaterMarkTemplate

The Visual appearance of the WatermarkText can be changed using the [WatermarkTemplate](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~WatermarkTemplate.html) property.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25"
                          WatermarkText="Type Here" CornerRadius="3"
                          WatermarkTextIsVisible="True" WatermarkOpacity="0.5"
                          UseNullOption="True">

<syncfusion:DoubleTextBox.WatermarkTemplate>
<DataTemplate>
<Border Background="Red">
<TextBlock Text="{Binding}" VerticalAlignment="Center" Margin="5,0,0,0"/>
</Border>
</DataTemplate>
</syncfusion:DoubleTextBox.WatermarkTemplate>
</syncfusion:DoubleTextBox>

{% endhighlight %}

{% endtabs %}

![Water mark template](Appearance-and-Styling-images/Appearance-and-Styling-img6.jpeg)


## CornerRadius

To rounded the corners of the DoubleTexBox, set the property [CornerRadius](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~CornerRadius.html) with the desired values. This property has no default value.

{% tabs %}

{% highlight XAML %}

<syncfusion:DoubleTextBox x:Name="DoubleTextBox1" Width="100" Height="25" CornerRadius="5"/>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 100;
doubleTextBox.Height = 25;
doubleTextBox.CornerRadius = new CornerRadius(5);  

{% endhighlight %}

{% highlight VB %}

Dim doubleTextBox As Syncfusion.Windows.Shared.DoubleTextBox =  New Syncfusion.Windows.Shared.DoubleTextBox() 
doubleTextBox.Width = 100
doubleTextBox.Height = 25
doubleTextBox.CornerRadius = New CornerRadius(5)

{% endhighlight %}

{% endtabs %}

![Corner radius](Appearance-and-Styling-images/Appearance-and-Styling-img7.jpeg)


## Setting VisualStyle for DoubleTextBox

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
