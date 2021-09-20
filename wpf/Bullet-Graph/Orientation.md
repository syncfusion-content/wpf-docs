---
layout: post
title: Orientation in WPF Bullet Graph control | Syncfusion
description: Learn here all about Orientation support in Syncfusion WPF Bullet Graph (SfBulletGraph) control and more.
platform: wpf
control: SfBulletGraph
documentation: ug
---

# Orientation in WPF Bullet Graph (SfBulletGraph)

By default, orientation of SfBulletGraph is horizontal. It can be customized by using [`Orientation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_Orientation) property, respectively.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph Orientation="Vertical" Minimum="0" Maximum="10" Interval="2">
            <syncfusion:SfBulletGraph.QualitativeRanges>
            <syncfusion:QualitativeRange RangeEnd="3" RangeStroke="#EBEBEB"></syncfusion:QualitativeRange>
            <syncfusion:QualitativeRange RangeEnd="7" RangeStroke="#7F7F7F"></syncfusion:QualitativeRange>
            <syncfusion:QualitativeRange RangeEnd="10" RangeStroke="#D8D8D8"></syncfusion:QualitativeRange>
            </syncfusion:SfBulletGraph.QualitativeRanges>
        </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

            SfBulletGraph bulletgraph = new SfBulletGraph();
            bulletgraph.Minimum = 0;
            bulletgraph.Maximum = 10;
            bulletgraph.Interval = 2;
            bulletgraph.Orientation = Orientation.Vertical;
            QualitativeRange range1 = new QualitativeRange();
            range1.RangeEnd = 3;
            range1.RangeStroke = (Brush)new BrushConverter().ConvertFrom("#EBEBEB");
            QualitativeRange range2 = new QualitativeRange();
            range2.RangeEnd = 7;
            range2.RangeStroke = (Brush)new BrushConverter().ConvertFrom("#7F7F7F");

            QualitativeRange range3 = new QualitativeRange();
            range3.RangeEnd = 10;
            range3.RangeStroke = (Brush)new BrushConverter().ConvertFrom("#D8D8D8");


            bulletgraph.QualitativeRanges.Add(range1);
            bulletgraph.QualitativeRanges.Add(range2);
            bulletgraph.QualitativeRanges.Add(range3);
            grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}

![Orientation_images1](Orientation_images/Orientation_img1.jpeg)
![Orientation_images2](Orientation_images/Orientation_img2.jpeg)

