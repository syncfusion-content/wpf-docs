---
layout: post
title: Orientation | SfLinearGauge | Wpf | Syncfusion
description: Orientation 
platform: wpf
control: SfLinearGauge
documentation: ug
---

# Orientation

The orientation of the linear gauge can be changed by setting the **Orientation** property of the SfLineraGauge. By default orientation of SfLinearGauge is Horizontal.

{% tabs %}
{% highlight xaml %}

    <Gauges:SfLinearGauge Name="linearGauge" Orientation="Horizontal"/>
    
{% endhighlight %}

{% highlight c# %}

    SfLinearGauge lineargauge = new SfLinearGauge();
    lineargauge.Orientation = Orientation.Horizontal;
    this.Grid.Children.Add(lineargauge);

{% endhighlight %}
{% endtabs %}

<table>
<tr>
<td>
{{'![](Orientation_images/Orientation_img2.png)'| markdownify }}
</td><td>
{{'![](Orientation_images/Orientation_img1.jpeg)'| markdownify }}
</td></tr>
</table>
