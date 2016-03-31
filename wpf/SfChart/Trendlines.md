---
layout: post
title: Trendlines| SfChart | Wpf | Syncfusion
description: trendlines
platform: wpf
control: SfChart
documentation: ug
---

# Trendlines

Trendlines are used to analyze and display the trends in the data graphically. It is built on the assumptions based on current and past price trends. 

The following code examples illustrate how to add trend lines to the chart.

{% highlight xaml %}

<syncfusion:ScatterSeries Interior="#4A4A4A" XBindingPath="Year" Label="Series"

ItemsSource="{Binding List}" YBindingPath="India"

ScatterHeight="15" ScatterWidth="15">

<syncfusion:ScatterSeries.Trendlines>

<syncfusion:Trendline Label="Trend" />

</syncfusion:ScatterSeries.Trendlines>

</syncfusion:ScatterSeries>

{% endhighlight %}

![](Trendlines_images/trendline_1.png)


You can get the [`Slope`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.TrendlineBase~Slope.html# "") and [`Intercept`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.TrendlineBase~Intercept.html# "") of the drawn trend line. 

The visibility of the trend line is defined using [`IsTrendlineVisible`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.TrendlineBase~IsTrendlineVisible.html# "") property as in the following code examples.

{% highlight xaml %}

<syncfusion:ScatterSeries Interior="#4A4A4A" XBindingPath="Year" Label="Series"

ItemsSource="{Binding List}" YBindingPath="India"

ScatterHeight="15" ScatterWidth="15">

<syncfusion:ScatterSeries.Trendlines>

<syncfusion:Trendline Label="Trend" IsTrendlineVisible="False"/>

</syncfusion:ScatterSeries.Trendlines>

</syncfusion:ScatterSeries>

{% endhighlight %}

![](Trendlines_images/trendline_2.png)


N> Here we have enabled the [`CheckBoxVisibility`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartLegend~CheckBoxVisibility.html# "") for the Legend. The CheckBox state indicates that trendline is not visible. You can enable trendline dynamically using this checkbox.

## Types of Trendlines

SfChart supports the following type of Trendlines.

* Linear
* Exponential
* Power
* Logarithmic
* Polynomial

### Linear

This shows when something is increasing or decreasing at a steady rate. This is the default trend line to be drawn for the chart.

The linear trend line will be calculated using the below formula:

__yValue__ __=__ __Intercept__ __+__ __Slope__ __*__ __xValue__ (__where__ __xValue__ __is__ __X__ __data__).

The following is the code example of this trend line.

{% highlight xaml %}

<syncfusion:FatLineSeries XBindingPath="Date"

YBindingPath="Value" 

Interior="#7F7F7F"

ItemsSource="{Binding StockPriceDetails}">

<syncfusion:FastLineSeries.Trendlines>

<syncfusion:Trendline Stroke="Black" Type="Linear"/>

</syncfusion:FastLineSeries.Trendlines>

</syncfusion:FastLineSeries>

{% endhighlight %}

![](Trendlines_images/trendline_3.png)


### Exponential

This trend line is used when there is a constant increasing or decreasing in values. This is a curved line.

The linear trend line will be calculated using the below formula:

(__Intercept__ __*__ __Math__.__Exp__ __(__Slope__ __*__ __xValue__)__) (__where__ __xValue__ __is__ __X__ __data__).

The following code example defines the exponential trendline.

{% highlight xaml %}

<syncfusion:FastLineSeries XBindingPath="Date"

YBindingPath="Value" 

Interior="#7F7F7F"

ItemsSource="{Binding StockPriceDetails}">

<syncfusion:FastLineSeries.Trendlines>

<syncfusion:Trendline Stroke="Black" Type="Exponential"/>

</syncfusion:FastLineSeries.Trendlines>

</syncfusion:FastLineSeries>

{% endhighlight %}

![](Trendlines_images/trendline_4.png)


N> This is not recommended for the data values having zero and negative value.

### Power

This trend line is used for comparing multiple sets of data that increase at specific rate. 

This will be calculates using the following formula:

__(__Intercept__ __*__ __Math__.__Pow__(__xValue__,__ __Slope__))__ __(__Where__ __xValue__ __is__ __X__ __data__).

The following code example explains how to define the power trendline.

{% highlight xaml %}

<syncfusion:FastLineSeries XBindingPath="Date"

YBindingPath="Value" 

Interior="#7F7F7F"

ItemsSource="{Binding StockPriceDetails}">

<syncfusion:FastLineSeries.Trendlines>

<syncfusion:Trendline Stroke="Black" Type="Power"/>

</syncfusion:FastLineSeries.Trendlines>

</syncfusion:FastLineSeries>

{% endhighlight %}

![](Trendlines_images/trendline_5.png)

### Logarithmic

This is used when there is a quick change in the data, either increasing or decreasing and then levels out. 

The will be calculated using the below formula:

__Intercept__ __+__ __Slope__ __*__ __Math__.__Log__(__xValue__)__ __(__where__ __xValue__ __is__ __X__ __data__).

The following code example illustrates the use of logarithmic trend line.

{% highlight xaml %}

<syncfusion:FastLineSeries XBindingPath="Date"

YBindingPath="Value" 

Interior="#7F7F7F"

ItemsSource="{Binding StockPriceDetails}">

<syncfusion:FastLineSeries.Trendlines>

<syncfusion:Trendline Stroke="Black" Type="Logarithmic"/>

</syncfusion:FastLineSeries.Trendlines>

</syncfusion:FastLineSeries>

{% endhighlight %}

![](Trendlines_images/trendline_6.png)

### Polynomial

The polynomial trendline is a curved line that is used when there are more data fluctuations. 

The polynomial trendline is calculated using the below formula:

__PolynomialSlopes__.__Select__(__(__value__,__ __index__)__ __=>__ __value__*__Math__.__Pow__(__xValue__,__ __(__double__)__ __index__)__).__Sum__()__ __where__ __xValue__ __is__ __X__ __data__

To define the polynomial trendline, you can use the following code example.

{% highlight xaml %}

<syncfusion:FastLineSeries XBindingPath="Date"

YBindingPath="Value" 

Interior="#7F7F7F"

ItemsSource="{Binding StockPriceDetails}">

<syncfusion:FastLineSeries.Trendlines>

<syncfusion:Trendline Stroke="Black" Type="Polynomial"/>

</syncfusion:FastLineSeries.Trendlines>

</syncfusion:FastLineSeries>

{% endhighlight %}

![](Trendlines_images/trendline_7.png)

#### Polynomial Order

You can set the Polynomial order for this trendline. Polynomial order calculates order based on the equation and this value should fall between 2 and 6.

{% highlight xaml %}

<syncfusion:FastLineSeries XBindingPath="Date"

YBindingPath="Value" 

Interior="#7F7F7F"

ItemsSource="{Binding StockPriceDetails}">

<syncfusion:FastLineSeries.Trendlines>

<syncfusion:Trendline Stroke="Black" Type="Polynomial"

PolynomialOrder="5"/>

</syncfusion:FastLineSeries.Trendlines>

</syncfusion:FastLineSeries>

{% endhighlight %}

![](Trendlines_images/trendline_8.png)

## Forecasting

Chart supports forecasting for the trendline, which is used to display trends about the future and the past. 

The following two types of forecasting available in SfChart:

* Forward Forecasting
* Backward Forecasting

### Forward Forecast

For determining the future trends (in forward direction). The following code example explains the how to set the value for forward forecast.

{% highlight xaml %}

<syncfusion:FastLineSeries XBindingPath="Date" YBindingPath="Value" 

Label="Stock Price"   Interior="#7F7F7F"

ItemsSource="{Binding StockPriceDetails}">

<syncfusion:FastLineSeries.Trendlines>

<syncfusion:Trendline Stroke="Black"

Type="Polynomial" PolynomialOrder="3" ForwardForecast="5" />

</syncfusion:FastLineSeries.Trendlines>

</syncfusion:FastLineSeries>

{% endhighlight %}

![](Trendlines_images/trendline_9.png)

### Backward Forecast

For determining the future trends (in backward direction). The following code example explains the how to set the value for forward forecast.

{% highlight xaml %}

<syncfusion:FastLineSeries XBindingPath="Date" YBindingPath="Value" 

Label="Stock Price"   Interior="#7F7F7F"

ItemsSource="{Binding StockPriceDetails}">

<syncfusion:FastLineSeries.Trendlines>

<syncfusion:Trendline Stroke="Black"

Type="Polynomial" PolynomialOrder="3"  BackwardForecast="5"  />

</syncfusion:FastLineSeries.Trendlines>

</syncfusion:FastLineSeries>

{% endhighlight %}

![](Trendlines_images/trendline_10.png)


## Customization 

You can customize the trendline [`Stroke`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.TrendlineBase~Stroke.html# ""), [`StrokeThickness`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.TrendlineBase~StrokeDashArray.html# "") and [`StrokeDashArray`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.TrendlineBase~StrokeThickness.html# "") as in below code example.

{% highlight xaml %}

<syncfusion:FastLineSeries XBindingPath="Date" YBindingPath="Value" 

Label="Stock Price"   Interior="#7F7F7F"

ItemsSource="{Binding StockPriceDetails}">

<syncfusion:FastLineSeries.Trendlines>

<syncfusion:Trendline Stroke="Black" Type="Linear"  

StrokeDashArray="4,4" StrokeThickness="2" />

</syncfusion:FastLineSeries.Trendlines>

</syncfusion:FastLineSeries>

{% endhighlight %}

![](Trendlines_images/trendline_11.png)


