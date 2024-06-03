---
layout: post
title: Fast Series in WPF Charts control | Syncfusion
description: Learn here all about Fast Series support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Fast Series in WPF Charts (SfChart)

A fast series is a special kind of line chart that can render a collection with a huge number of data points. Fast series is rendered using a polyline segment.

## Fast Line

The [`FastLineSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastLineSeries.html?tabs=tabid-1) is a special kind of line series that can render a collection with a huge number of datapoints. FastLine is rendered using polyline segment. 

{% tabs %}

{% highlight xaml %}

<chart:FastLineSeries x:Name="FastLineSeries" ItemsSource="{Binding Data}"

XBindingPath="Date" Interior="#7F7F7F"

YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

FastLineSeries series = new FastLineSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "Date",

    YBindingPath = "Value",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x7F))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF FastLine Chart Type](FastChart_Images/wpf-fastline-chart-type.png)

The following line properties are available for FastLineSeries:

* [`Stroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeries.html#Syncfusion_UI_Xaml_Charts_ChartSeries_Stroke)
* [`StrokeDashArray`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastLineSeries.html#Syncfusion_UI_Xaml_Charts_FastLineSeries_StrokeDashArray)
* [`StrokeDashOffset`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastLineSeries.html#Syncfusion_UI_Xaml_Charts_FastLineSeries_StrokeDashOffset)
* [`StrokeDashCap`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastLineSeries.html#Syncfusion_UI_Xaml_Charts_FastLineSeries_StrokeDashCap)
* [`StrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeries.html#Syncfusion_UI_Xaml_Charts_ChartSeries_StrokeThickness)

## Fast Stacking Column

[`FastStackingColumnBitmapSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastStackingColumnBitmapSeries.html) similar to StackingColumnSeries except that it loads faster and provides better performance. 

{% tabs %}

{% highlight xaml %}

<chart:FastStackingColumnBitmapSeries StrokeThickness="5"

ItemsSource="{Binding MedalDetails}”       

XBindingPath="CountryName" YBindingPath="GoldMedals"  

Interior="#4A4A4A" />

{% endhighlight %}

{% highlight c# %}

FastStackingColumnBitmapSeries series = new FastStackingColumnBitmapSeries()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "GoldMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![ WPF FastStackingColumnBitmap Chart Type](FastChart_Images/wpf-faststackingcolumnbitmap-chart-type.png)
