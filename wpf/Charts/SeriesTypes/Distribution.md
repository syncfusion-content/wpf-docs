---
layout: post
title: Distribution charts | SfChart | Wpf | Syncfusion
description: This section explains Distribution charts and its properties for customization in WPF Charts (SfChart)
platform: wpf
control: SfChart
documentation: ug
---

# Distribution chart in WPF (SfChart)

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

![Histogram chart type in WPF](Series_images/histogram.png)


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

![Interval customization support for histogram series in WPF Chart](Series_images/histogram_interval.png)