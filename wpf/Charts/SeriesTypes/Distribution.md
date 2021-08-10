---
layout: post
title: Histogram Chart in WPF Charts control | Syncfusion
description: Learn here all about Histogram Chart support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Histogram in WPF Charts (SfChart)

## Histogram Chart

[`HistogramSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.HistogramSeries.html#) is one of the seven basic tools of quality control to Visualize the frequency distribution of data over a certain time period. HistogramSeries is often used to plot the density of data.
 
The following code example shows how to add the HistogramSeries:

{% tabs %}

{% highlight xaml %}

<chart:HistogramSeries x:Name="histogramSeries" 

HistogramInterval="5" 

Interior="#BCBCBC"

ItemsSource="{Binding Product}"

XBindingPath="Price" 

YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

HistogramSeries series = new HistogramSeries()
{

    ItemsSource = new ViewModel().Product,

    XBindingPath = "Price",

    YBindingPath = "Value",

    HistogramInterval = 5,

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Histogram Chart](Series_images/wpf-histogram-chart.png)


You can customize interval using [`HistogramInterval`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.HistogramSeries.html#Syncfusion_UI_Xaml_Charts_HistogramSeries_HistogramInterval) property and the normal distribution curve can be collapsed using [`ShowNormalDistributionCurve`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.HistogramSeries.html#Syncfusion_UI_Xaml_Charts_HistogramSeries_ShowNormalDistributionCurve).

{% tabs %}

{% highlight xaml %}

<chart:HistogramSeries x:Name="histogramSeries" 

HistogramInterval="5"

ShowNormalDistributionCurve="False"

Interior="#BCBCBC"

ItemsSource="{Binding Product}"

XBindingPath="Price" 

YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

HistogramSeries series = new HistogramSeries()
{

    ItemsSource = new ViewModel().Product,

    XBindingPath = "Price",

    YBindingPath = "Value",

    HistogramInterval = 5,

    ShowNormalDistributionCurve = false,

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Customizing Interval for WPF Histogram Chart](Series_images/wpf-histogram-chart-interval.png)

**CurveLineStyle**

You can customize the normal distribution curve by using the [`CurveLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.HistogramSeries.html#Syncfusion_UI_Xaml_Charts_HistogramSeries_CurveLineStyle) property.

{% tabs %}

{% highlight xaml %}
...
<Style TargetType="Polyline" x:Key="CurveColorStyle">
    <Setter Property="Stroke" Value="LightSeaGreen"/>
    <Setter Property="StrokeThickness" Value="3"/>
    <Setter Property="StrokeDashArray" Value="1,2" />
</Style>
...

<chart:HistogramSeries x:Name="histogramSeries" 

HistogramInterval="5"

ShowNormalDistributionCurve="True"

CurveLineStyle="{StaticResource CurveColorStyle}"

Interior="LightSkyBlue"

ItemsSource="{Binding Product}"

XBindingPath="Price" 

YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

...
HistogramSeries series = new HistogramSeries()
{

    ItemsSource = new ViewModel().Product,

    XBindingPath = "Price",

    YBindingPath = "Value",

    HistogramInterval = 5,

    ShowNormalDistributionCurve = True,

    CurveLineStyle = histogramChart.Resources["CurveColorStyle"] as Style,

    Interior = new SolidColorBrush(new SolidColorBrush(Colors.LightSkyBlue))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Customizing Curve Line Style in WPF Chart](Series_images/wpf-chart-curve-line-style.png)

N> You can explore our [WPF Histogram Chart](https://www.syncfusion.com/wpf-controls/charts/wpf-histogram-chart) feature tour page for its groundbreaking features. You can also explore our [WPF Histogram Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Other%20Charts/Histogram.xaml) to know how to represent time-dependent data, showing trends in data at equal intervals.