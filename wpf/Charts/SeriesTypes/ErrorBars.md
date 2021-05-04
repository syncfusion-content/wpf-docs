---
layout: post
title: ErrorBar Chart in WPF Charts control | Syncfusion
description: Learn here all about ErrorBar Chart support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# ErrorBar Chart in WPF Charts (SfChart)

[ErrorBarSeries](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#) is used to indicate the errors or uncertainty in reported values. This will find the possible variations in measurements, and in Chart control these values are displayed as data points.


The [`HorizontalErrorValue`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_HorizontalErrorValue) and [`VerticalErrorValue`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_VerticalErrorValue) is used to set the error value(variation) to the series.

The following code examples illustrates how to create error bar series:

{% tabs %}

{% highlight xaml %}

<chart:ScatterSeries ScatterWidth="20" ScatterHeight="20"  Label="Coal" 

ItemsSource="{Binding EnergyProductions}" Interior="#BCBCBC"

XBindingPath="ID" YBindingPath="Coal">

</chart:ScatterSeries>

<chart:ErrorBarSeries Name="Errorseries"   ItemsSource="{Binding EnergyProductions}" 

XBindingPath="ID" YBindingPath="Coal" 

VerticalErrorValue="50" HorizontalErrorValue="1" >

</chart:ErrorBarSeries>

{% endhighlight %}

{% highlight c# %}

ScatterSeries series = new ScatterSeries()
{

    ItemsSource = new ViewModel().EnergyProductions,

    XBindingPath = "ID",

    YBindingPath = "Coal",

    ScatterWidth = 20,

    ScatterHeight = 20,

    Label ="Coal",

    ListenPropertyChange=true,

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

ErrorBarSeries errorBar = new ErrorBarSeries()
{

    ItemsSource = new ViewModel().EnergyProductions,

    XBindingPath = "ID",

    YBindingPath = "Coal",

    HorizontalErrorValue = 1,

    VerticalErrorValue = 50

};

chart.Series.Add(series);

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Error bars support in WPF Chart](ErrorBar_images/ErrorBar_1.png)


## Mode

This [`Mode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_Mode) property is used to define whether to identify horizontal error or vertical error. By default, the Mode value is [`Both`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarMode.html), which will display both horizontal and vertical error values.

**Horizontal**

To view horizontal error value, you can set the Mode as Horizontal as shown in the below code example.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries"   ItemsSource="{Binding EnergyProductions}" 

XBindingPath="ID" YBindingPath="Coal"                                  

VerticalErrorValue="50" HorizontalErrorValue="1" 

Mode="Horizontal">

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBar = new ErrorBarSeries()
{

    ItemsSource = new ViewModel().EnergyProductions,

    XBindingPath = "ID",

    YBindingPath = "Coal",

    HorizontalErrorValue = 1,

    VerticalErrorValue = 50,

    Mode = ErrorBarMode.Horizontal

};

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Mode for error bars in WPF Chart](ErrorBar_images/ErrorBar_2.png)


**Vertical**

To view vertical error value, you can set the Mode as Vertical as shown in the below code example.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries"   ItemsSource="{Binding EnergyProductions}" 

XBindingPath="ID" YBindingPath="Coal" 

VerticalErrorValue="50" HorizontalErrorValue="1" 

Mode="Vertical">

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBar = new ErrorBarSeries()
{

    ItemsSource = new ViewModel().EnergyProductions,

    XBindingPath = "ID",

    YBindingPath = "Coal",

    HorizontalErrorValue = 1,

    VerticalErrorValue = 50,

    Mode = ErrorBarMode.Vertical

};

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Mode for error bars in WPF Chart](ErrorBar_images/ErrorBar_3.png)


## Direction

[`ErrorBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html) series allows you to view the horizontal and vertical error values in both positive and negative directions.

**Horizontal direction**

[`HorizontalDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_HorizontalDirection) property of [`ErrorBarSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html) allows you to view the horizontal error value in the following type of directions:

 * [`Both`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarDirection.html) – It indicates the actual data point value along with specific amount of positive and negative error values.
 * [`Minus`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarDirection.html) – It indicates the actual data point value along with specific amount of negative error value.
 * [`Plus`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarDirection.html) – It indicates the actual data point value along with specific amount of positive error value.

**Both**

The following code illustrates how to set the [`HorizontalDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_HorizontalDirectionProperty) value as both.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries" HorizontalDirection="Both">

</chart:ErrorBarSeries>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries();

errorBarSeries.HorizontalDirection = ErrorBarDirection.Both;

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Direction for error bars in WPF Chart](ErrorBar_images/horizontal_both.png)

**Minus**

The following code illustrates how to set the [`HorizontalDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_HorizontalDirectionProperty) value as minus.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries" HorizontalDirection="Minus">

</chart:ErrorBarSeries>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries();

errorBarSeries.HorizontalDirection = ErrorBarDirection.Minus;

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Direction for error bars in WPF Chart](ErrorBar_images/horizontal_minus.png)

**Plus**

The following code illustrates how to set the [`HorizontalDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_HorizontalDirectionProperty) value as plus.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries" HorizontalDirection="Plus">

</chart:ErrorBarSeries>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries();

errorBarSeries.HorizontalDirection = ErrorBarDirection.Plus;

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Direction for error bars in WPF Chart](ErrorBar_images/horizontal_plus.png)

**Vertical direction**

[`VerticalDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_VerticalDirectionProperty) property of [`ErrorBarSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html) allows you to view the vertical error value in following type of directions:

 * Both - It indicates the actual data point value along with specific amount of positive and negative error values.
 * Minus - It indicates the actual data point value along with specific amount of negative error value.
 * Plus - It indicates the actual data point value along with specific amount of positive error value.

**Both**

The following code illustrates how to set the [`VerticalDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_VerticalDirectionProperty) value as both.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries" VerticalDirection="Both" >

</chart:ErrorBarSeries>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries();

errorBarSeries.VerticalDirection= ErrorBarDirection.Both;

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Direction for error bars in WPF Chart](ErrorBar_images/vertical_both.png)

**Minus**

The following code illustrates how to set the [`VerticalDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_VerticalDirectionProperty) value as minus.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries" VerticalDirection="Minus" >

</chart:ErrorBarSeries>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries();

errorBarSeries.VerticalDirection= ErrorBarDirection.Minus;

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Direction for error bars in WPF Chart](ErrorBar_images/vertical_minus.png)

**Plus**

The following code illustrates how to set the [`VerticalDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_VerticalDirectionProperty) value as plus.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries" VerticalDirection="Plus" >

</chart:ErrorBarSeries>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries();

errorBarSeries.VerticalDirection= ErrorBarDirection.Plus;

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Direction for error bars in WPF Chart](ErrorBar_images/vertical_plus.png)


## Type

SfChart supports the following type of error bar series.

* [`Fixed`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarType.html) 
* [`Percentage`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarType.html) 
* [`StandardDeviation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarType.html)
* [`StandardError`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarType.html)

N> The default error bar series is Fixed.

### Fixed

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries"  

ItemsSource="{Binding EnergyProductions}" 

XBindingPath="ID" 

YBindingPath="Coal" 

VerticalErrorValue="40" HorizontalErrorValue="10" 

Mode="Both" Type="Fixed">

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBar = new ErrorBarSeries()
{

    ItemsSource = new ViewModel().EnergyProductions,

    XBindingPath = "ID",

    YBindingPath = "Coal",

    HorizontalErrorValue = 10,

    VerticalErrorValue = 40,

    Mode = ErrorBarMode.Both,

    Type = ErrorBarType.Fixed

};

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Fixed error bar type in WPF Chart](ErrorBar_images/ErrorBar_4.png)

### Percentage

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries"  

ItemsSource="{Binding EnergyProductions}" 

XBindingPath="ID" 

YBindingPath="Coal" 

VerticalErrorValue="40" HorizontalErrorValue="10" 

Mode="Both" Type="Percentage">

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBar = new ErrorBarSeries()
{

    ItemsSource = new ViewModel().EnergyProductions,

    XBindingPath = "ID",

    YBindingPath = "Coal",

    HorizontalErrorValue = 10,

    VerticalErrorValue = 40,

    Mode = ErrorBarMode.Both,

    Type = ErrorBarType.Percentage

};

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}


![Percentage error bar type in WPF Chart](ErrorBar_images/ErrorBar_5.png)


### Standard Deviation

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries"  

ItemsSource="{Binding EnergyProductions}" 

XBindingPath="ID" 

YBindingPath="Coal" 

VerticalErrorValue="40" HorizontalErrorValue="10" 

Mode="Both" Type="StandardDeviation"/>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBar = new ErrorBarSeries()
{

    ItemsSource = new ViewModel().EnergyProductions,

    XBindingPath = "ID",

    YBindingPath = "Coal",

    HorizontalErrorValue = 10,

    VerticalErrorValue = 40,

    Mode = ErrorBarMode.Both,

    Type = ErrorBarType.StandardDeviation

};

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Standard deviation error bar type in WPF Chart](ErrorBar_images/ErrorBar_6.png)

### Standard Errors

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries"  

ItemsSource="{Binding EnergyProductions}" 

XBindingPath="ID" 

YBindingPath="Coal" 

VerticalErrorValue="40" HorizontalErrorValue="10" 

Mode="Both" Type="StandardErrors"/>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBar = new ErrorBarSeries()
{

    ItemsSource = new ViewModel().EnergyProductions,

    XBindingPath = "ID",

    YBindingPath = "Coal",

    HorizontalErrorValue = 10,

    VerticalErrorValue = 40,

    Mode = ErrorBarMode.Both,

    Type = ErrorBarType.StandardErrors

};

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Standard deviation error bar type in WPF Chart](ErrorBar_images/ErrorBar_7.png)


## Custom

If the Type is Custom, you have to bind [`HorizontalErrorPathValue`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_HorizontalErrorPath) and [`VerticalErrorPathValue`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_VerticalErrorPath) as shown in the below code snippet.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries Name="Errorseries"  

ItemsSource="{Binding EnergyProductions}" 

XBindingPath="ID" 

YBindingPath="Coal" 

HorizontalErrorPath="HorizontalErrorValue"

VerticalErrorPath="VerticalErrorValue"

Mode="Both" Type="Custom"/>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBar = new ErrorBarSeries()
{

    ItemsSource = new ViewModel().EnergyProductions,

    XBindingPath = "ID",

    YBindingPath = "Coal",

    HorizontalErrorValue = 10,

    VerticalErrorValue = 40,

    Mode = ErrorBarMode.Both,

    Type = ErrorBarType.Custom

};

chart.Series.Add(errorBar);

{% endhighlight %}

{% endtabs %}

![Custom error bar type in WPF Chart](ErrorBar_images/ErrorBar_8.png)



## Customization 

SfChart provides customization properties for the error bar lines as in the following section.

### Line Style

You can define the LineStyle for the error bar lines using [`HorizontalLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_HorizontalLineStyle) and [`VerticalLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_VerticalLineStyle) properties as in the below code examples.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries.HorizontalLineStyle>

<chart:LineStyle Stroke="Black"  StrokeThickness="2"  >

</chart:LineStyle>

</chart:ErrorBarSeries.HorizontalLineStyle>

{% endhighlight %}

{% highlight c# %}

errorBarSeries.HorizontalLineStyle = new LineStyle()
{

    Stroke = new SolidColorBrush(Colors.Black),

    StrokeThickness = 2

};

{% endhighlight %}

{% endtabs %}

![Error bar lines customization support in WPF Chart](ErrorBar_images/ErrorBar_9.png)

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries.VerticalLineStyle>

<chart:LineStyle Stroke="Black"  StrokeThickness="2"  >

</chart:LineStyle>

</chart:ErrorBarSeries.VerticalLineStyle>

{% endhighlight %}

{% highlight c# %}

errorBarSeries.VerticalLineStyle = new LineStyle()
{

    Stroke = new SolidColorBrush(Colors.Black),

    StrokeThickness = 2

};

{% endhighlight %}

{% endtabs %}

![Error bar lines customization support in WPF Chart](ErrorBar_images/ErrorBar_10.png)


### Line Cap Style

ErrorBar line cap can be customized using [`HorizontalCapLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_HorizontalCapLineStyle) and [`VerticalCapLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ErrorBarSeries.html#Syncfusion_UI_Xaml_Charts_ErrorBarSeries_VerticalCapLineStyle) as in the below code examples.

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries.HorizontalCapLineStyle>

<chart:CapLineStyle Stroke="Black" StrokeThickness="2"  

LineWidth="10"></chart:CapLineStyle>

</chart:ErrorBarSeries.HorizontalCapLineStyle>

{% endhighlight %}

{% highlight c# %}

errorBarSeries.HorizontalCapLineStyle = new CapLineStyle()
{

    Stroke = new SolidColorBrush(Colors.Black),

    StrokeThickness = 2,

    LineWidth = 10

};

{% endhighlight %}

{% endtabs %}

![Error bar lines customization support in WPF Chart](ErrorBar_images/ErrorBar_11.png)

{% tabs %}

{% highlight xaml %}

<chart:ErrorBarSeries.VerticalCapLineStyle>

<chart:CapLineStyle Stroke="Black" StrokeThickness="3"  

LineWidth="15"></chart:CapLineStyle>

</chart:ErrorBarSeries.VerticalCapLineStyle>

{% endhighlight %}

{% highlight c# %}

errorBarSeries.VerticalCapLineStyle = new CapLineStyle()
{

    Stroke = new SolidColorBrush(Colors.Black),

    StrokeThickness = 3,

    LineWidth = 15

};

{% endhighlight %}

{% endtabs %}

![Error bar lines customization support in WPF Chart](ErrorBar_images/ErrorBar_12.png)
