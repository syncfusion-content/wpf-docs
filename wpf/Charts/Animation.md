---
layout: post
title: Animation in WPF Charts control | Syncfusion
description: Learn here all about Animation support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Animation in WPF Charts (SfChart)

SfChart allows you to animate the chart series on loading, and whenever the ItemsSource changes. Animation in chart can be enabled by setting the EnableAnimation property as True and defining the corresponding animation speed with AnimationDuration property.

The following types of series support Animation.

* Line
* Column
* Bar
* Area
* Scatter
* Bubble
* Spline
* Spline area
* Stacking column
* Stacking bar
* Stacking area
* Pie

The following APIs are used to customize the Animation.


* [`EnableAnimation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_EnableAnimation)-Represents a boolean value to enable the animation for series.
* [`AnimationDuration`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_AnimationDuration)-Represents a TimeSpan value which sets animation speed for the chart.


The following example shows the Animation feature for chart series.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart>

<syncfusion:ColumnSeries EnableAnimation="True" AnimationDuration="00:00:03" 

XBindingPath="Category" YBindingPath="Count" ItemsSource="{Binding}"/>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

        ItemsSource = new ViewModel().Data,

        XBindingPath = "Category",

        YBindingPath = "Count",

        EnableAnimation = true,

        AnimationDuration = new TimeSpan(00, 00, 03)

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

**Column** **Series**

![WPF Chart Column Animation](Animation_images/wpf-chart-column-animation.gif)

**SplineArea** **Series**

![WPF Chart Spline Animation](Animation_images/wpf-chart-spline-animation.gif)

**Scatter** **Series**

![WPF Chart Scatter Animation](Animation_images/wpf-chart-scatter-animation.gif)


N> You can refer to our [WPF Charts](https://www.syncfusion.com/wpf-controls/charts) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Charts example](https://github.com/syncfusion/wpf-demos) to knows various chart types and how to easily configured with built-in support for creating stunning visual effects.