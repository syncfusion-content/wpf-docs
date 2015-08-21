---
layout: post
title: Run-Time-Feature
description: run time feature
platform: wpf
control: OLAP Gauge
documentation: ug
---

# Run Time Feature

# Define the types of tooltips available in Gauge control

The OLAP Gauge control can display the tooltip information when the mouse pointer is moved over the gauge pointer or marker.

## Pointer ToolTip

The OLAP Gauge control for WPF provides value information when the mouse pointer is moved over the pointer. This is achieved by enabling the ShowPointersTooltip property of the gauge control. The following code example illustrates the setting of this property.

 {% highlight c# %}
 
    



this.olapGauge1.ShowPointersTooltip = true;

 {% endhighlight %}




 {% highlight vbnet %}
  
    



Me.olapGauge1.ShowPointersTooltip = True

 {% endhighlight %}









The following screen shot illustrates a pointer tooltip displayed for the OLAP Gauge.

![C:/Users/Hari/Pictures/OlapGauge/Pointer Tooltip.png](Run-Time-Feature_images/Run-Time-Feature_img1.png)


## Marker ToolTip

The OLAP Gauge control for WPF provides goal information when the mouse pointer is moved over the marker. This is achieved by enabling the ShowMarkersTooltip property of the Gauge control. The following code example illustrates the setting of this property.

 {% highlight c# %}
 
    



this.olapGauge1.ShowMarkersTooltip = true;

 {% endhighlight %}




 {% highlight vbnet %}
  
    



Me.olapGauge1.ShowMarkersTooltip = True

 {% endhighlight %}









The following screen shot illustrates a marker tooltip displayed for the OLAP Gauge.

![C:/Users/Hari/Pictures/OlapGauge/Marker Tooltip.png](Run-Time-Feature_images/Run-Time-Feature_img2.png)


## Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Version Number>\BI\WPF\OLAPGauge.WPF\Samples\Product ShowCase\Product Showcase Demo\

