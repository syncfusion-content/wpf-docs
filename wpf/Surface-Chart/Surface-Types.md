---
layout: post
title: Surface Types in WPF Surface Chart control | Syncfusion
description: Learn here all about Surface Types support in Syncfusion WPF Surface Chart (SfSurfaceChart) control and more.
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# Surface Types in WPF Surface Chart (SfSurfaceChart)

Essential Surface Chart provides the following types to plot three dimensional data points.

* Surface
* WireframeSurface
* Contour 
* WireframeContour

### Surface

Surface charts are used to explore the relationship between three dimensional data. 

The following code shows how to set the type of surface.

{% tabs %}

{% highlight xaml %}

   <chart:SfSurfaceChart Type="Surface"/>

{% endhighlight %}

{% highlight c# %}

SfSurfaceChart chart = new SfSurfaceChart();

chart.Type = SurfaceType.Surface;

{% endhighlight %}

{% endtabs %}

![surface_chart_img8](surface_chart_images/surface_chart_img8.jpeg)


### WireframeSurface

You can draw the wireframe or mesh, for the surface chart.

{% tabs %}

{% highlight xaml %}

   <chart:SfSurfaceChart Type="WireframeSurface"/>

{% endhighlight %}

{% highlight c# %}

SfSurfaceChart chart = new SfSurfaceChart();

chart.Type = SurfaceType.WireframeSurface;

{% endhighlight %}

{% endtabs %}

![surface_chart_img9](surface_chart_images/surface_chart_img9.jpeg)


### Contour

Viewing the surface chart from the top is called contour. It is a graphical technique that represents the three dimensional surface in a two dimensional format.  

{% tabs %}

{% highlight xaml %}

<chart:SfSurfaceChart Type="Contour"/>

{% endhighlight %}

{% highlight c# %}

SfSurfaceChart chart = new SfSurfaceChart();

chart.Type = SurfaceType.Contour;

{% endhighlight %}

{% endtabs %}

![surface_chart_img10](surface_chart_images/surface_chart_img10.jpeg)


### WireframeContour

You can draw the wireframe or mesh for the contour chart

{% tabs %}

{% highlight xaml %}

<chart:SfSurfaceChart Type="WireframeContour"/>

{% endhighlight %}

{% highlight c# %}

SfSurfaceChart chart = new SfSurfaceChart();

chart.Type = SurfaceType.WireframeContour;

{% endhighlight %}

{% endtabs %}

![surface_chart_img11](surface_chart_images/surface_chart_img11.jpeg)
