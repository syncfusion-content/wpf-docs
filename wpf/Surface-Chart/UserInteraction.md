---
layout: post
title: User interaction in WPF Surface Chart | Syncfusion®
description: User interaction in the WPF Surface Chart enables zooming, rotation, and navigation for detailed exploration of three-dimensional data.
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# User interaction in WPF Surface Chart

The Essential Surface Chart allows you to zoom and rotate the chart for better visualization of all the axes and their points.

## Zooming

Zooming of the surface chart is controlled with the [`EnableZooming`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_EnableZooming) property.

The following code shows how to enable zooming on the surface chart.

{% tabs %}

{% highlight xaml %}

    <chart:SfSurfaceChart EnableZooming="True" >
    </chart:SfSurfaceChart>

{% endhighlight %}

{% highlight c# %}

SfSurfaceChart chart = new SfSurfaceChart();
chart.EnableZooming = true;
grid.Children.Add(chart);

{% endhighlight %}

{% endtabs %}

Zooming can either be done with pinch zooming or programmatically using the [`ZoomLevel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ZoomLevel) property.

{% tabs %}

{% highlight xaml %}

    <chart:SfSurfaceChart EnableZooming="True" ZoomLevel="0.5">
    </chart:SfSurfaceChart>

{% endhighlight %}

{% highlight c# %}

SfSurfaceChart chart = new SfSurfaceChart();
chart.EnableZooming = true;
chart.ZoomLevel = 0.5;
grid.Children.Add(chart);

{% endhighlight %}

{% endtabs %}

![Zoom level](surface_chart_images/ZoomLevel.png)


## Rotation

The surface chart can be rotated for better visualization of all the axes and their plots.

This can be controlled using the [`EnableRotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_EnableRotation) property.

{% tabs %}

{% highlight xaml %}

    <chart:SfSurfaceChart EnableRotation="True">
    </chart:SfSurfaceChart>

{% endhighlight %}

{% highlight c# %}

SfSurfaceChart chart = new SfSurfaceChart();
chart.EnableRotation = true;
grid.Children.Add(chart);

{% endhighlight %}

{% endtabs %}

Rotation can either be done with interaction or programmatically using the [`Rotate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_Rotate) property.

{% tabs %}

{% highlight xaml %}

    <chart:SfSurfaceChart EnableRotation="True" Rotate="50">
    </chart:SfSurfaceChart>

{% endhighlight %}

{% highlight c# %}

SfSurfaceChart chart = new SfSurfaceChart();
chart.EnableRotation = true;
chart.Rotate = 50;
grid.Children.Add(chart);

{% endhighlight %}

{% endtabs %}

![Rotation](surface_chart_images/RotatedImage.png)

## Tilt

The surface chart can be tilted to a certain angle using the [`Tilt`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_Tilt) property.

{% tabs %}

{% highlight xaml %}

    <chart:SfSurfaceChart  Tilt="40">
    </chart:SfSurfaceChart>

{% endhighlight %}

{% highlight c# %}

SfSurfaceChart chart = new SfSurfaceChart();
chart.Tilt = 40;
grid.Children.Add(chart);

{% endhighlight %}

{% endtabs %}

![Tilt](surface_chart_images/TiltedImage.png)