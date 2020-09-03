---
layout: post
title: Animation| SfChart | Wpf | Syncfusion
description: Animation support for SfChart
platform: wpf
control: SfChart
documentation: ug
---

# Animation

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

![Animation support in WPF SfChart](Animation_images/column.gif)

**SplineArea** **Series**

![Animation support in WPF SfChart](Animation_images/spline.gif)

**Scatter** **Series**

![Animation support in WPF SfChart](Animation_images/scatter.gif)
