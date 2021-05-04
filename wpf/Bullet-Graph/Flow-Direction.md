---
layout: post
title: Flow Direction in WPF Bullet Graph control | Syncfusion
description: Learn here all about Flow Direction support in Syncfusion WPF Bullet Graph (SfBulletGraph) control and more.
platform: wpf
control: SfBulletGraph
documentation: ug
---

### Flow Direction

By default the flow direction of SfBulletGraph is Left to Right. It can be customized by using **FlowDirection** property respectively.

>Note:-When the Orientation of **SfBulletGraph** is **Horizontal** the default Flow direction will be Left to Right like when the Orientation of **SfBulletGraph** is **Vertical** the default Flow Direction will be Top to Bottom.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph  FlowDirection="LeftToRight">
    </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

     SfBulletGraph bulletgraph = new SfBulletGraph();
     bulletgraph.FlowDirection = BulletGraphFlowDirection.LeftToRight;
     this.Grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}

<table>
<tr>
<td>
{{'![](Flow-Direction_images/Flow-Direction_img1.jpeg)'| markdownify }}
</td>
<td>
{{'![](Flow-Direction_images/Flow-Direction_img2.jpeg)'| markdownify }}
{{'____'| markdownify }}
</td></tr>
</table>