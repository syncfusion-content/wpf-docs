---
layout: post
title: Column and Bar Chart in WPF Charts control | Syncfusion
description: Learn here all about Column and Bar Chart support in Syncfusion WPF Charts (SfChart) control and more.
platform: wpf
control: SfChart
documentation: ug
---

# Column and Bar in WPF Charts (SfChart)

## Column Chart

[Column Charts](https://www.syncfusion.com/wpf-controls/charts/wpf-column-chart) plot discrete rectangles for the given values. The following code example demonstrates the usage of [`ColumnSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ColumnSeries.html#).

{% tabs %}

{% highlight xaml %}

<chart:ColumnSeries Interior="#7F7F7F" ItemsSource="{Binding SneakersDetail}"           

XBindingPath="Brand" YBindingPath="ItemsCount1"   />

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().SneakersDetail,

    XBindingPath = "Brand",

    YBindingPath = "ItemsCount1",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x7F))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Column Chart](Series_images/wpf-column-chart.png)

N> You can also explore our [WPF Column Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Basic%20Charts/Column.xaml) to know how to render and configure the column chart.

## Bar Chart

[Bar Charts](https://www.syncfusion.com/wpf-controls/charts/wpf-bar-chart) are similar to column series, excepts its orientation. The following code examples shows how to use [`BarSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BarSeries.html#).

{% tabs %}

{% highlight xaml %}

<chart:BarSeries ItemsSource="{Binding CategoricalDatas}" XBindingPath="Category" 

YBindingPath="Value" Interior="#7F7F7F" />

{% endhighlight %}

{% highlight c# %}

BarSeries series = new BarSeries()
{

    ItemsSource = new ViewModel().CategoricalDatas,

    XBindingPath = "Category",

    YBindingPath = "Value",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x7F))

};

{% endhighlight %}

{% endtabs %}

![WPF Bar Chart](Series_images/wpf-bar-chart.png)

N> You can also explore our [WPF Bar Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Basic%20Charts/Bar.xaml) to know how to render and configure the bar chart.

### Spacing

[`Spacing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_SpacingProperty) property of series is used to decide the width of a segment. [`Spacing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_SpacingProperty) value ranges from 0 to 1. The following code illustrates how to set [`Spacing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_SpacingProperty) property of the series,

{% tabs %}

{% highlight xaml %}

<Chart:ColumnSeries Chart:ChartSeriesBase.Spacing="0.8"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()

ChartSeriesBase.SetSpacing(series, 0.8);

{% endhighlight %}

{% endtabs %}

![WPF Chart displays Spacing between Columns](Series_images/wpf-chart-spacing.png)

**Segment Spacing**

[`SegmentSpacing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ColumnSeries.html#Syncfusion_UI_Xaml_Charts_ColumnSeries_SegmentSpacing) property is used to set the spacing among the segments, when multiple series are added in chart. Its value ranges from 0 to 1. The following code illustrates how to use the [`SegmentSpacing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ColumnSeries.html#Syncfusion_UI_Xaml_Charts_ColumnSeries_SegmentSpacing) property in series,

{% tabs %}

{% highlight xaml %}

<Chart:SfChart >

<Chart:ColumnSeries SegmentSpacing="0.6"/>

<Chart:ColumnSeries SegmentSpacing="0.6"/>

</Chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

ColumnSeries series1 = new ColumnSeries()

{

    SegmentSpacing = 0.6,

};

chart.Series.Add(series1);

ColumnSeries series2 = new ColumnSeries()

{

    SegmentSpacing = 0.6

};

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![WPF Chart displays Column Segment Spacing](Series_images/wpf-chart-segment-spacing.png)
