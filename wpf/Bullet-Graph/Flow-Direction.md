---
layout: post
title: Flow Direction in WPF Bullet Graph | Syncfusion®
description: Flow direction in the WPF Bullet Graph controls the layout orientation, enabling content to be displayed from left to right or right to left.
platform: wpf
control: SfBulletGraph
documentation: ug
---

# Flow Direction in WPF Bullet Graph

By default, the flow direction of WPF Bullet Graph is Left to Right. It can be customized by using the **FlowDirection** property.

>**Note:** When the orientation of [`SfBulletGraph`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html) is **Horizontal**, the default flow direction is left to right, and when the orientation is **Vertical**, the default flow direction is top to bottom.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2" FlowDirection="LeftToRight">
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
    bulletgraph.FlowDirection = FlowDirection.LeftToRight;
    bulletgraph.Orientation = Orientation.Horizontal;
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

Refer to the following screenshot for flow direction `LeftToRight`.

![Flow-Direction_images1](Flow-Direction_images/Flow-Direction_img1.jpeg)
![Flow-Direction_images2](Flow-Direction_images/Flow-Direction_img2.jpeg)


{% tabs %}

{% highlight xaml %}

     <syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2" FlowDirection="RightToLeft">
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
    bulletgraph.FlowDirection = FlowDirection.RightToLeft;
    bulletgraph.Orientation = Orientation.Horizontal;
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


Refer to the following screenshot for flow direction `RightToLeft`.

![Flow-Direction_images2](Flow-Direction_images/RTL_Vertical.png)
![Flow-Direction_images1](Flow-Direction_images/RTL_Horizontal.png)

