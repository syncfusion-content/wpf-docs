---
layout: post
title: Measure-Settings-Performance--feature-Measure
description: measure settings (performance/feature measure)
platform: wpf
control: Bullet Graph 
documentation: ug
---

# Measure Settings (Performance/feature measure)

### Featured Measure:

Featured measure is used to display the primary data, or the current value of the data that you are measuring. It should usually be encoded as a bar, like the bar on a bar graph, and be prominent.

### Customizing Featured Measure:

The value of the featured measure of the Bullet Graph is set by the FeaturedMeasure property. By setting the FeaturedMeasureBarStroke property, the stroke of the feature measure bar can be customized. The thickness of the featured measure bar is modified by using FeaturedMeasureBarStrokeThickness.

### Code Example:
{% highlight html %}
[XAML]

    <syncfusion:SfBulletGraph Orientation="Horizontal"  Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward" 

                              QualitativeRangesSize="30" 

                              QuantitativeScaleLength="400"                              

                              FeaturedMeasure="5" 

                              FeaturedMeasureBarStroke="Red" 

                              FeaturedMeasureBarStrokeThickness="10"

                              ComparativeMeasureSymbolStroke="Black"

                              LabelOffset="5" LabelStroke="Black"

                              CaptionPosition="Near">

    </syncfusion:SfBulletGraph>

{% endhighlight  %}
{% highlight c# %}
[C#]



SfBulletGraph bulletgraph = new SfBulletGraph();

      bulletgraph.FlowDirection = BulletGraphFlowDirection.Forward;

      bulletgraph.Orientation = Orientation.Horizontal;

      bulletgraph.Minimum = 0;

      bulletgraph.Maximum = 10;

      bulletgraph.Interval = 2;

      bulletgraph.QualitativeRangesSize   = 30;

      bulletgraph.QuantitativeScaleLength = 400;

      bulletgraph.FeaturedMeasure = 5;

      bulletgraph.FeaturedMeasureBarStroke = new SolidColorBrush(Colors.Red);

      bulletgraph.FeaturedMeasureBarStrokeThickness = 10;

      bulletgraph.ComparativeMeasureSymbolStroke    = new SolidColorBrush(Colors.Black);

      bulletgraph.LabelOffset = 5;

      bulletgraph.LabelStroke  = new SolidColorBrush(Colors.Black);

      bulletgraph.CaptionPosition = BulletGraphCaptionPosition.Near;

      this.Grid.Children.Add(bulletgraph);


{% endhighlight  %}


![C:/Users/Giftline/Desktop/New folder/3.jpg](Concept-and-Features_images/Concept-and-Features_img5.png)



### Comparative Measure:

Comparative measure is less visually dominant than the featured measure. It is always encoded as a short line that runs perpendicular to the orientation of the graph. A good example would be a target for YTD revenue. Whenever the featured measure intersects a comparative measure, the comparative measure should appear behind the featured measure.

### Customizing Comparative Measure:

The value of the comparative measure is set by using the ComparativeMeasure property. By setting the ComparativeMeasureSymbolStroke property, the stroke of the comparative measure symbol is customized. The thickness of the comparative measure symbol is modified by using ComparativeMeasureSymbolStrokeThickness.

### Code Example:
{% highlight html %}
[XAML]

        <syncfusion:SfBulletGraph Orientation="Horizontal"  FlowDirection="Forward"

                                  QualitativeRangesSize="30" 

                                  QuantitativeScaleLength="400"

                                  Minimum="0" Maximum="10" Interval="2" 

                                  ComparativeMeasure="7"

                                  ComparativeMeasureSymbolStroke="Red"

                                  ComparativeMeasureSymbolStrokeThickness="6">

        </syncfusion:SfBulletGraph>

{% endhighlight  %}
{% highlight c# %}
[C#]



SfBulletGraph bulletgraph = new SfBulletGraph();

       bulletgraph.FlowDirection = BulletGraphFlowDirection.Forward;

       bulletgraph.Orientation = Orientation.Horizontal;

       bulletgraph.QualitativeRangesSize = 30;

       bulletgraph.QuantitativeScaleLength = 400;

       bulletgraph.Minimum = 0;

       bulletgraph.Maximum = 10;

       bulletgraph.Interval = 2;

       bulletgraph.ComparativeMeasure = 7;

       bulletgraph.ComparativeMeasureSymbolStroke = new SolidColorBrush(Colors.Red);

       bulletgraph.ComparativeMeasureSymbolStrokeThickness = 6;

       this.Grid.Children.Add(bulletgraph);


{% endhighlight  %}


![C:/Users/Giftline/Desktop/New folder/4.jpg](Concept-and-Features_images/Concept-and-Features_img6.png)



