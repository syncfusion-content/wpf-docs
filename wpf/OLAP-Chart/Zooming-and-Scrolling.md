---
layout: post
title: Zooming and Scrolling in WPF Olap Chart control | Syncfusion
description: Learn about Zooming and Scrolling support in Syncfusion WPF Olap Chart control, its elements and more details.
platform: wpf
control: OLAP Chart
 documentation: ug
---

# Zooming and Scrolling in WPF Olap Chart

The OLAP chart for WPF allows you to zoom in to a narrower range within the OLAP chart.

In the zooming mode, a zooming toolkit is displayed at the top-left corner of the OLAP chart. Using the buttons in the zooming toolkit, ChartSeries can be zoomed in, out, reset, or closed.

![Zooming-and-scrolling_img1](Zooming-and-scrolling_images/Zooming-and-scrolling_img1.png)

The visibility of the zooming toolkit or individual buttons in the toolkit can be controlled by using the following properties:

_Property_

* **ZoomInButtonVisibility**: Gets or sets the zoom in button visibility.
* **ZoomOutButtonVisibility**: Gets or sets the zoom out button visibility.
* **ZoomCloseButtonVisibility**: Gets or sets the zoom close button visibility.
* **ZoomResetButtonVisibility**: Gets or sets the zoom reset button visibility.

The following code sample illustrates the above settings.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" 
    syncfusion:ChartZoomingToolkit.ZoomInButtonVisibility="{Binding IsChecked, 
          ElementName=cbxZoomIn, Converter={StaticResource boolToVisibilityConverter}}"
    syncfusion:ChartZoomingToolkit.ZoomOutButtonVisibility="{Binding IsChecked, 
          ElementName=cbxZoomOut, Converter={StaticResource boolToVisibilityConverter }}"
    syncfusion:ChartZoomingToolkit.ZoomCloseButtonVisibility="{Binding IsChecked, 
          ElementName=cbxZoomClose, Converter={StaticResource boolToVisibilityConverter }}"
    syncfusion:ChartZoomingToolkit.ZoomResetButtonVisibility="{Binding IsChecked, 
          ElementName=cbxZoomReset, Converter={StaticResource boolToVisibilityConverter }}">
</syncfusion:OlapChart>

{% endhighlight %}

{% highlight c# %}
 
ChartZoomingToolkit.SetZoomInButtonVisibility(olapChart, Visibility.Collapsed);
ChartZoomingToolkit.SetZoomOutButtonVisibility(olapChart, Visibility.Hidden);
ChartZoomingToolkit.SetZoomResetButtonVisibility(olapChart, Visibility.Collapsed);
ChartZoomingToolkit.SetZoomingToolkitVisibility(olapChart, Visibility.Visible);

{% endhighlight %}

{% highlight vbnet %}
  
ChartZoomingToolkit.SetZoomInButtonVisibility(olapChart, Visibility.Collapsed)
ChartZoomingToolkit.SetZoomOutButtonVisibility(olapChart, Visibility.Hidden)
ChartZoomingToolkit.SetZoomResetButtonVisibility(olapChart, Visibility.Collapsed)
ChartZoomingToolkit.SetZoomingToolkitVisibility(olapChart, Visibility.Visible)

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Zooming and Scrolling\Zooming and Scrolling Demo
