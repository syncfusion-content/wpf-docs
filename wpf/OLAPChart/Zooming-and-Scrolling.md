---
layout: post
title: Zooming and Scrolling| OLAP Chart | Wpf | Syncfusion
description: Zooming and Scrolling
platform: wpf
control: OLAP Chart
documentation: ug
---

# Zooming and Scrolling

OLAP Chart for WPF allows you to zoom into a narrower range within the OLAP Chart. 

## Zoom by using the Zooming Toolkit

In the Zooming mode, a Zooming toolkit is displayed at the top-left corner of the OLAP Chart. Using the buttons in the Zooming toolkit, ChartSeries can be zoomed in, out, reset, or closed.

![](Core-Features_images/Core-Features_img43.png)


## Display/Hide Buttons in the Zooming Toolkit

The visibility of the Zooming Toolkit or the individual buttons in the toolkit can be controlled by using the following properties:

_Property Table_

<table>
<tr>
<th>
{{ '**Properties**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th></tr>
<tr>
<td>
ZoomInButtonVisibility</td><td>
Gets or sets the zoom in button visibility.</td></tr>
<tr>
<td>
ZoomOutButtonVisibility</td><td>
Gets or sets the zoom out button visibility.</td></tr>
<tr>
<td>
ZoomCloseButtonVisibility</td><td>
Gets or sets the zoom close button visibility.</td></tr>
<tr>
<td>
ZoomResetButtonVisibility</td><td>
Gets or sets the zoom reset button visibility.</td></tr>
</table>


The following code snippet illustrates the above settings:

 {% highlight xaml %}

    



    <syncfusion:OlapChart Name="olapChart" 



 syncfusion:ChartZoomingToolkit.ZoomInButtonVisibility="{Binding IsChecked, 

 ElementName=cbxZoomIn, 

 Converter={StaticResource boolToVisibilityConverter}}"


 syncfusion:ChartZoomingToolkit.ZoomOutButtonVisibility="{Binding IsChecked, 

 ElementName=cbxZoomOut, 

 Converter={StaticResource boolToVisibilityConverter }}"


 syncfusion:ChartZoomingToolkit.ZoomCloseButtonVisibility="{Binding IsChecked, 

 ElementName=cbxZoomClose, 

 Converter={StaticResource boolToVisibilityConverter }}"


 syncfusion:ChartZoomingToolkit.ZoomResetButtonVisibility="{Binding IsChecked, 

 ElementName=cbxZoomReset, 

 Converter={StaticResource boolToVisibilityConverter }}">



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


A sample, which demonstrates the zooming feature, is available in the following sample installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Zooming and Scrolling\Zooming and Scrolling Demo
