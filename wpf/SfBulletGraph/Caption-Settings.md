---
layout: post
title: Caption-Settings
description: Caption Settings
platform: wpf
control: Bullet Graph 
documentation: ug
---

# Caption Settings

The Caption for a Bullet Graph is used to specify a unique label describing the value represented. 
{% highlight html %}


         <syncfusion:SfBulletGraph Orientation="Horizontal"  Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"

                                  QualitativeRangesSize="30"

                                  QuantitativeScaleLength="400">

            <syncfusion:SfBulletGraph.Caption>

                <StackPanel Margin="0,0,10,0">

                    <TextBlock Text="Revenue YTD" Foreground="Black"

                               FontSize="13" HorizontalAlignment="Center"/>

                    <TextBlock Text="$ in Thousands" Foreground="Black"

                               FontSize="13" HorizontalAlignment="Center"/>

                </StackPanel>

            </syncfusion:SfBulletGraph.Caption>

</syncfusion:SfBulletGraph>


{% endhighlight %}

{% highlight c# %}




            SfBulletGraph bulletgraph = new SfBulletGraph();

            bulletgraph.FlowDirection = BulletGraphFlowDirection.Forward;

            bulletgraph.Orientation   = Orientation.Horizontal;

            bulletgraph.Minimum = 0;

            bulletgraph.Maximum = 10;

            bulletgraph.Interval = 2;

            bulletgraph.QualitativeRangesSize   = 30;

            bulletgraph.QuantitativeScaleLength = 400;

            TextBlock _textBlock   = new TextBlock() { Text = "Revenue YTD" };

            TextBlock _textBlock1  = new TextBlock() { Text = "$ in Thousands" };

            StackPanel _stackPanel = new StackPanel();

            _stackPanel.Children.Add(_textBlock);

            _stackPanel.Children.Add(_textBlock1);

            bulletgraph.Caption    = _stackPanel;

            this.Grid.Children.Add(bulletgraph);




{% endhighlight %}






![C:/Users/Giftline/Desktop/blessy3.jpg](Concept-and-Features_images/Concept-and-Features_img3.jpeg)

## Caption Position

The caption in the Bullet Graph can be placed in the start or end of the quantitative scale by choosing from one of the two options available in the CaptionPosition property. They are:

1. Near (Default)
2. Far

## Code Example

{% highlight html %}


    <syncfusion:SfBulletGraph Orientation="Horizontal" FlowDirection="Forward" Minimum="0" Maximum="10" Interval="2"  

                              QualitativeRangesSize="30" 

                              QuantitativeScaleLength="400"                              

                              FeaturedMeasure="5" 

                              FeaturedMeasureBarStroke="Red" 

                              FeaturedMeasureBarStrokeThickness="10"

                              ComparativeMeasureSymbolStroke="Black"

                              LabelOffset="5" LabelStroke="Black"

                              CaptionPosition="Far">

    </syncfusion:SfBulletGraph>

{% endhighlight  %}
{% highlight c# %}



SfBulletGraph bulletgraph = new SfBulletGraph();

      bulletgraph.FlowDirection = BulletGraphFlowDirection.Forward;

      bulletgraph.Orientation = Orientation.Horizontal;

      bulletgraph.QualitativeRangesSize = 30;

      bulletgraph.QuantitativeScaleLength = 400;

      bulletgraph.FeaturedMeasure = 5;

      bulletgraph.FeaturedMeasureBarStroke = new SolidColorBrush(Colors.Black);

      bulletgraph.FeaturedMeasureBarStrokeThickness = 10;

      bulletgraph.ComparativeMeasureSymbolStroke = new SolidColorBrush(Colors.Black);

      bulletgraph.LabelOffset = 5;

      bulletgraph.LabelStroke = new SolidColorBrush(Colors.Black);

      bulletgraph.CaptionPosition = BulletGraphCaptionPosition.Far;

      this.Grid.Children.Add(bulletgraph);



{% endhighlight  %}



![C:/Users/Giftline/Desktop/New folder/1.jpg](Concept-and-Features_images/Concept-and-Features_img4.png)

