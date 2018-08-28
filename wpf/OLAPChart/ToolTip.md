---
layout: post
title: Tooltip
description: Tooltip
platform: wpf
control: OLAP Chart
documentation: ug
---

# Tooltip

The OLAP chart provides the series information such as measure, primary x-axis and y-axis values, and series name through the series tooltip, when the mouse pointer is moved over chart points.

The following code sample shows how to disable the series tooltip using the `ShowToolTip` property.

{% tabs %}

{% highlight c# %}
 
this.olapChart.Series[0].ShowToolTip = false;

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.Series(0).ShowToolTip = False

{% endhighlight %}

{% endtabs %}
  
![](Tooltip_images/Tooltip_img1.png)
  
The following code sample shows how to enable the series tooltip using the `ShowToolTip` property.

{% tabs %}

{% highlight c# %}
 
this.olapChart.Series[0].ShowToolTip = true;

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.Series(0).ShowToolTip = True

{% endhighlight %}

{% endtabs %}
  
![](Tooltip_images/Tooltip_img2.png)