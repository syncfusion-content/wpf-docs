
---
layout: post
title: Bubble and Scatter Charts| SfChart | Wpf | Syncfusion
description: This section explains Bubble and Scatter Charts and its properties for customization in WPF Charts (SfChart)
platform: wpf
control: SfChart
documentation: ug
---

# Bubble and Scatter Charts in WPF Chart (SfChart)

## Bubble 

[`BubbleSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BubbleSeries.html#) is represented by closely packed circles, whose areas are proportional to the quantities. 

The size of the bubble series is relative proportional to the value bind with the series using [`Size`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BubbleSeries~Size.html#)  property. You can set the constraints on this size using [`MinimumRadius`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BubbleSeries~MaximumRadius.html#) and [`MaximumRadius`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BubbleSeries~MaximumRadius.html#).

{% tabs %}

{% highlight xaml %}

<chart:BubbleSeries  ItemsSource="{Binding Fruits}"  XBindingPath="FruitName" 

YBindingPath="People"   Size="Size" MinimumRadius="5" 

MaximumRadius="10"

Interior="#BCBCBC" />

{% endhighlight %}

{% highlight c# %}

BubbleSeries series = new BubbleSeries()
{

    ItemsSource = new ViewModel().Fruits,

    XBindingPath = "FruitName",

    YBindingPath = "People",

    Size = "Size",

    MinimumRadius = 5,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Bubble chart type in WPF](Series_images/bubble.png)

**Show Zero Bubbles**

The zero size bubble segments can be enabled or disabled by using the [`ShowZeroBubbles`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BubbleSeries~ShowZeroBubblesProperty.html) property. By default, the property value is True.
The following code illustrates how to set the value to the property.

{% tabs %}

{% highlight xaml %}

<chart:BubbleSeries ShowZeroBubbles="True" >

</chart:BubbleSeries>

{% endhighlight %}

{% highlight c# %}

BubbleSeries series = new BubbleSeries();

series.ShowZeroBubbles = true;

{% endhighlight %}

{% endtabs %}

![ShowZeroBubbles support in WPF](Series_images/showBubble_true.png)

The following code example and screenshots describes when [`ShowZeroBubbles`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BubbleSeries~ShowZeroBubblesProperty.html) value is false.

{% tabs %}

{% highlight xaml %}

<chart:BubbleSeries ShowZeroBubbles="False" >

</chart:BubbleSeries>

{% endhighlight %}

{% highlight c# %}

BubbleSeries series = new BubbleSeries();

series.ShowZeroBubbles = false;

{% endhighlight %}

{% endtabs %}

![ShowZeroBubbles support in WPF Chart](Series_images/showBubble_false.png)

## Scatter

[`ScatterSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries.html#) is similar to bubble series when each point being represented by an ellipse with equal size. This size can be defined by using [`ScatterHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries~ScatterHeight.html#) and [`ScatterWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries~ScatterWidth.html#) properties.

{% tabs %}

{% highlight xaml %}

<chart:ScatterSeries Interior="#4A4A4A" ScatterHeight="4" ScatterWidth="4" 

ItemsSource="{Binding DataPoints}" XBindingPath="Eruptions" 

YBindingPath="WaitingTime"/>

{% endhighlight %}

{% highlight c# %}

ScatterSeries series = new ScatterSeries()
{

    ItemsSource = new ViewModel().DataPoints,

    XBindingPath = "Eruptions",

    YBindingPath = "WaitingTime",

    ScatterHeight = 4,

    ScatterWidth = 4,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Scatter chart type in WPF](Series_images/scatter.png)


