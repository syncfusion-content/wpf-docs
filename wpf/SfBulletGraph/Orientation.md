---
layout: post
title: Orientation| Bullet Graph  | Wpf | Syncfusion
description: orientation
platform: wpf
control: Bullet Graph 
documentation: ug
---

# Orientation

The view of the Bullet Graph is changed by setting the Orientation property. Quantitative scale contains two major components: ticks and labels. The length of the quantitative scale is customized by using the QuantitativeScaleLength property. The direction of the quantitative scale is personalized by making use of the FlowDirection property it’s either Forward or Backward.

{% tabs %}
{% highlight html %}


<syncfusion:SfBulletGraph Orientation="Vertical"   FlowDirection="Forward"

QualitativeRangesSize="30" 

QuantitativeScaleLength="400"

Minimum="0" Maximum="10" Interval="2" >

<syncfusion:SfBulletGraph.QualitativeRanges>

<syncfusion:QualitativeRange RangeEnd="3" 

RangeStroke="LightGray"

RangeOpacity="1">

</syncfusion:QualitativeRange>

<syncfusion:QualitativeRange RangeEnd="7" 

RangeStroke="Gray"

RangeOpacity="1">

</syncfusion:QualitativeRange>

<syncfusion:QualitativeRange RangeEnd="10" 

RangeStroke="DarkGray"

RangeOpacity="1">

</syncfusion:QualitativeRange>

</syncfusion:SfBulletGraph.QualitativeRanges>



</syncfusion:SfBulletGraph>

{% endhighlight  %}
{% highlight c# %}




SfBulletGraph bulletgraph = new SfBulletGraph();

bulletgraph.FlowDirection = BulletGraphFlowDirection.Forward;

bulletgraph.Orientation = Orientation.Vertical;

bulletgraph.QualitativeRangesSize = 30;

bulletgraph.QuantitativeScaleLength = 400;

bulletgraph.Minimum = 0;

bulletgraph.Maximum = 10;

bulletgraph.Interval = 2;

bulletgraph.QualitativeRanges.Add(new QualitativeRange() { RangeEnd = 3, RangeOpacity = 1, RangeStroke = new SolidColorBrush(Colors.LightGray) });

bulletgraph.QualitativeRanges.Add(new QualitativeRange() { RangeEnd = 7, RangeOpacity = 1, RangeStroke = new SolidColorBrush(Colors.Gray) });

bulletgraph.QualitativeRanges.Add(new QualitativeRange() { RangeEnd = 10, RangeOpacity = 1, RangeStroke = new SolidColorBrush(Colors.DarkGray) });

this.Grid.Children.Add(bulletgraph);

{% endhighlight  %}
{% endtabs %}

![](Concept-and-Features_images/Concept-and-Features_img1.png)

SfBulletGraph with Vertical Orientation
{:.caption}


![](Concept-and-Features_images/Concept-and-Features_img2.png)

SfBulletGraph with Horizontal Orientation
{:.caption}



