---
layout: post
title: Quantitative Scale in WPF Bullet Graph control | Syncfusion
description: Learn here all about Quantitative Scale support in Syncfusion WPF Bullet Graph (SfBulletGraph) control and more.
platform: wpf
control: SfBulletGraph
documentation: ug
---

# Quantitative Scale in WPF Bullet Graph (SfBulletGraph)

Quantitative scale contains two major components such as ticks and labels which gives the looks of bar graph. It defines the frequency of labels and tick marks with overall [`Minimum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_Maximum) values for declared [`Interval`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_Interval). The length of the quantitative scale can be customized by using the [`QuantitativeScaleLength`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_QuantitativeScaleLength) property.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph QuantitativeScaleLength="300" Minimum="0" Maximum="10"  Interval="2"/>

{% endhighlight %}

{% highlight c# %}

            SfBulletGraph bulletgraph = new SfBulletGraph();
            bulletgraph.QuantitativeScaleLength = 300;
            bulletgraph.Minimum = 0;
            bulletgraph.Maximum = 10;
            bulletgraph.Interval = 2;
            grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}

![Quantitative-scale_img1](Quantitative-scale_images/Quantitative-scale.png)
