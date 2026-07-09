---
layout: post
title: Ticks in WPF Bullet Graph control | Syncfusion
description: Learn all about the Ticks support in Syncfusion WPF Bullet Graph (SfBulletGraph) control, its elements, and more details.
platform: wpf
control: SfBulletGraph
documentation: ug
---

# Ticks in WPF Bullet Graph (SfBulletGraph)

The quantitative scale is displayed with two types of ticks:

* Major ticks: the primary scale indicators.
* Minor ticks: the secondary scale indicators that fall in between the major ticks.

## Customizing Ticks

The [`Interval`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_Interval) property is used to calculate the major tick count of a SfBulletGraph. Like ticks, small ticks are calculated using the [`MinorTicksPerInterval`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_MinorTicksPerInterval) property.

The stroke of the major and minor ticks is customized by setting the [`MajorTickStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_MajorTickStroke) and [`MinorTickStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_MinorTickStroke) properties. The size can be modified by using the [`MajorTickSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_MajorTickSize) and [`MinorTickSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_MinorTickSize) properties. By setting the [`MajorTickStrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_MajorTickStrokeThickness) and [`MinorTickStrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_MinorTickStrokeThickness) properties, the stroke's thickness can be customized.

{% tabs %}
{% highlight xaml %}

     <syncfusion:SfBulletGraph  Interval="2" Minimum="0" Maximum="10"
                                MinorTicksPerInterval="3"
                                MajorTickSize="15"
                                MinorTickSize="10"
                                MajorTickStroke="Red"      
                                MinorTickStroke="Green">
    </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bulletgraph = new SfBulletGraph();
    bulletgraph.Interval = 2;
    bulletgraph.Minimum = 0;
    bulletgraph.Maximum = 10;
    bulletgraph.MinorTicksPerInterval = 3;
    bulletgraph.MajorTickSize = 15;
    bulletgraph.MinorTickSize = 10;
    bulletgraph.MajorTickStroke = new SolidColorBrush(Colors.Red);
    bulletgraph.MinorTickStroke = new SolidColorBrush(Colors.Green);
    grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}

![Ticks_img](Ticks_images/Ticks_img.png)

## TickPosition, below, or across the ranges of the quantitative scale using the [`TickPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_TickPosition) property, which supports the following options:

1. Below (Default)
2. Above
3. Cross

{% capture codesnippet1 %}
{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph TickPosition="Cross">
    </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

            SfBulletGraph bulletgraph = new SfBulletGraph();
            bulletgraph.TickPosition = BulletGraphTicksPosition.Cross;
            grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

![Ticks_img1](Ticks_images/Ticks_img1.png)
