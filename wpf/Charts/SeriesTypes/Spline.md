---
layout: post
title: Spline Chart in WPF Charts control | Syncfusion
description: Learn here all about Spline Chart support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Spline Chart in WPF Charts (SfChart)

## Spline Chart

[`SplineSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineSeries.html#) resembles line series, but the difference between them is that instead of connecting the data points with line segments, the data points are connected by smooth Bezier curves.

{% tabs %}

{% highlight xaml %}

<chart:SplineSeries  XBindingPath="Year"     

ItemsSource="{Binding List}" YBindingPath="India"               

Interior="#4A4A4A"/>

<chart:SplineSeries  XBindingPath="Year"     

ItemsSource="{Binding List}" YBindingPath="America"               

Interior="#4A4A4A"/>

{% endhighlight %}

{% highlight c# %}

SplineSeries series1 = new SplineSeries()
{

    ItemsSource = new ViewModel().List,

    XBindingPath = "Year",

    YBindingPath = "India",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

SplineSeries series2 = new SplineSeries()
{

    ItemsSource = new ViewModel().List,

    XBindingPath = "Year",

    YBindingPath = "America",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Spline chart type in WPF](Series_images/spline.png)

**Dashed Lines**

[`StrokeDashArray`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineSeries.html#Syncfusion_UI_Xaml_Charts_SplineSeries_StrokeDashArray) property of the [`SplineSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineSeries.html#) is used to render spline series with dashes.

{% tabs %}

{% highlight xaml %}

<chart:SplineSeries ItemsSource="{Binding List}" XBindingPath="Year" YBindingPath="India" StrokeDashArray="5,3" />

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries()
{
    ItemsSource = new ViewModel().List,
    XBindingPath = "Year",
    YBindingPath = "India"
};

DoubleCollection doubleCollection = new DoubleCollection();
doubleCollection.Add(5);
doubleCollection.Add(3);
series.StrokeDashArray = doubleCollection;
chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

## Spline Area Chart

[`SplineAreaSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineAreaSeries.html#) connects a series of data points using smooth Bezier line curves, with the underlying areas filled. 

{% tabs %}

{% highlight xaml %}

<chart:SplineAreaSeries Interior="#7F7F7F"              

ItemsSource="{Binding Products}" XBindingPath="ProdName"     

YBindingPath="Price" />

{% endhighlight %}

{% highlight c# %}

SplineAreaSeries series = new SplineAreaSeries()
{

    ItemsSource = new ViewModel().Products,

    XBindingPath = "ProdName",

    YBindingPath = "Price",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x7F))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![SplineArea chart type in WPF](Series_images/splinearea.png)

## Spline Type

[`Spline`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineSeries.html) and [`SplineArea`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineAreaSeries.html) series provide support for various spline type. The spline type of the series can be changed by using its [`SplineType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineSeries.html#Syncfusion_UI_Xaml_Charts_SplineSeries_SplineTypeProperty) property. The following spline types are supported by Spline and SplineArea series:

* [`Natural`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineType.html) 
* [`Monotonic`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineType.html) 
* [`Cardinal`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineType.html)
* [`Clamped`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineType.html)

**Cardinal**

The following code illustrates how to set the [`SplineType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineSeries.html#Syncfusion_UI_Xaml_Charts_SplineSeries_SplineType) value as [`Cardinal`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineType.html).

{% tabs %}

{% highlight xaml %}

<chart:SplineSeries SplineType="Cardinal">

</chart:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries();

series.SplineType = SplineType.Cardinal;

{% endhighlight %}

{% endtabs %}

![Cardinal spline support in WPF Chart](Series_images/cardinal.png)

**Monotonic**

The following code illustrates how to set the [`SplineType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineSeries.html#Syncfusion_UI_Xaml_Charts_SplineSeries_SplineTypeProperty) value as Monotonic.

{% tabs %}

{% highlight xaml %}

<chart:SplineSeries SplineType="Monotonic">

</chart:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries();

series.SplineType = SplineType.Monotonic;

{% endhighlight %}

{% endtabs %}

![Monotonic spline support in WPF Chart](Series_images/monotonic.png)

**Clamped**

The following code illustrates how to set the [`SplineType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SplineSeries.html#Syncfusion_UI_Xaml_Charts_SplineSeries_SplineTypeProperty) value as Clamped.

{% tabs %}

{% highlight xaml %}

<chart:SplineSeries SplineType="Clamped">

</chart:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries();

series.SplineType = SplineType.Clamped;

{% endhighlight %}

{% endtabs %}

![Clamped spline support in WPF Chart](Series_images/clamped.png)
