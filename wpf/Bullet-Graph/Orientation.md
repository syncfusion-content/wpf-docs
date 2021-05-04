---
layout: post
title: Orientation in WPF Bullet Graph control | Syncfusion
description: Learn here all about Orientation support in Syncfusion WPF Bullet Graph (SfBulletGraph) control and more.
platform: wpf
control: SfBulletGraph
documentation: ug
---

# Orientation in WPF Bullet Graph (SfBulletGraph)

By default orientation of SfBulletGraph is horizontal. It can be customized by using **Orientation** property respectively.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph Orientation="Vertical">
    </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

     SfBulletGraph bulletgraph = new SfBulletGraph();
     bulletgraph.Orientation = Orientation.Vertical;
     this.Grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}

<table>
<tr>
<td>
{{'![Orientation_images1](Orientation_images/Orientation_img1.jpeg)'| markdownify }}
</td><td>
{{'![Orientation_images2](Orientation_images/Orientation_img2.jpeg)'| markdownify }}
</td></tr>
</table>
