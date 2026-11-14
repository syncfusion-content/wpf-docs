---
layout: post
title: Tooltip in WPF Olap Chart | Syncfusion®
description: Tooltip in the WPF OLAP Chart displays detailed information about data points on hover, helping users analyze chart data effectively.
platform: wpf
control: OLAP Chart
documentation: ug
---

# Tooltip in WPF Olap Chart

The WPF OLAP Chart provides series information, such as measure values, primary x-axis and y-axis values, and the series name, through series tooltips when the mouse pointer is moved over chart points.

The following code sample shows how to disable the series tooltip using the `ShowToolTip` property.

{% tabs %}

{% highlight c# %}
 
this.olapChart.Series[0].ShowToolTip = false;

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.Series(0).ShowToolTip = False

{% endhighlight %}

{% endtabs %}
  
![Tooltip_img1](Tooltip_images/Tooltip_img1.png)
  
The following code sample shows how to enable the series tooltip using the `ShowToolTip` property.

{% tabs %}

{% highlight c# %}
 
this.olapChart.Series[0].ShowToolTip = true;

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.Series(0).ShowToolTip = True

{% endhighlight %}

{% endtabs %}
  
![Tooltip_img2](Tooltip_images/Tooltip_img2.png)
