---
layout: post
title: Scale-Label-Settings
description: scale label settings
platform: wpf
control: Bullet Graph 
documentation: ug
---

# Scale Label settings

### Labels:

A quantitative scale label specifies the numeric value according to the major ticks in the range of the scale.

### Customizing Labels:

The label’s offset is changed by using the LabelOffset property. The foreground of the label is customized by setting LabelStroke. By setting LabelSize, the font size of the labels is modified. 

### Code Example:

{% highlight html %}
[XAML]

        <syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"

                                  QualitativeRangesSize="30" 

                                  QuantitativeScaleLength="400"

                                  LabelOffset="5" 

                                  LabelStroke="Red">

        </syncfusion:SfBulletGraph>

{% endhighlight %}
{% highlight c# %}
[C#]



   SfBulletGraph bulletgraph = new SfBulletGraph();

      bulletgraph.FlowDirection = BulletGraphFlowDirection.Forward;

      bulletgraph.Orientation = Orientation.Horizontal;

      bulletgraph.Minimum = 0;

      bulletgraph.Maximum = 10;

      bulletgraph.Interval = 2;

      bulletgraph.QualitativeRangesSize = 30;

      bulletgraph.QuantitativeScaleLength = 400;

      bulletgraph.LabelOffset = 5;

      bulletgraph.LabelSize = 10;

      bulletgraph.LabelFormat = "";

      bulletgraph.LabelStroke = new SolidColorBrush(Colors.Red);

      this.Grid.Children.Add(bulletgraph);


{% endhighlight  %}




![C:/Users/Giftline/Desktop/New folder/8.jpg](Concept-and-Features_images/Concept-and-Features_img11.png)



### Label Position

The labels in the scale can be placed above or below the qualitative ranges by choosing the following options available in the LabelPosition property. 

1. Below (Default)
2. Above

### Code Example:

{% highlight html %}
[XAML]

        <syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"

                                  QualitativeRangesSize="30" 

                                  QuantitativeScaleLength="400"                                  

                                  LabelOffset="5" LabelStroke="Black"

                                  TickPosition="Cross"

                                  LabelPosition="Above">

        </syncfusion:SfBulletGraph>

{% endhighlight  %}
{% highlight html %}

[C#]

SfBulletGraph bulletgraph = new SfBulletGraph();

      bulletgraph.FlowDirection = BulletGraphFlowDirection.Forward;

      bulletgraph.Orientation = Orientation.Horizontal;

      bulletgraph.Minimum = 0;

      bulletgraph.Maximum = 10;

      bulletgraph.Interval = 2;

      bulletgraph.QualitativeRangesSize = 30;

      bulletgraph.QuantitativeScaleLength = 400;

      bulletgraph.LabelOffset = 5;

      bulletgraph.LabelStroke = new SolidColorBrush(Colors.Black);

      bulletgraph.TickPosition = BulletGraphTicksPosition.Cross;

      bulletgraph.LabelPosition = BulletGraphLabelsPosition.Above;

      this.Grid.Children.Add(bulletgraph);

{% endhighlight  %}

![C:/Users/Giftline/Desktop/New folder/9.jpg](Concept-and-Features_images/Concept-and-Features_img12.png)