---
layout: post
title: Scale-Label-settings
description: Scale Label settings
platform: wpf
control: Bullet Graph 
documentation: ug
---

# Scale Label settings

## Labels:

A quantitative scale label specifies the numeric value according to the major ticks in the range of the scale.

## Customizing Labels:

The label’s offset is changed by using the LabelOffset property. The foreground of the label is customized by setting LabelStroke. By setting LabelSize, the font size of the labels is modified. 

## Code Example:

{% highlight html %}


        <syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"

                                  QualitativeRangesSize="30" 

                                  QuantitativeScaleLength="400"

                                  LabelOffset="5" 

                                  LabelStroke="Red">

        </syncfusion:SfBulletGraph>

{% endhighlight %}
{% highlight c# %}



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



## Label Position

The labels in the scale can be placed above or below the qualitative ranges by choosing the following options available in the LabelPosition property. 

1. Below (Default)
2. Above

## Code Example:

{% highlight html %}


        <syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"

                                  QualitativeRangesSize="30" 

                                  QuantitativeScaleLength="400"                                  

                                  LabelOffset="5" LabelStroke="Black"

                                  TickPosition="Cross"

                                  LabelPosition="Above">

        </syncfusion:SfBulletGraph>

{% endhighlight  %}

{% highlight html %}


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



## Tooltip Setting

Tooltip in SfBulletGraph is used to view the values of FeaturedMeasure, ComparativeMeasure and QualitativeRange in the required design.

This tooltip is displayed when the mouse is over the FeaturedMeasure, ComparativeMeasure or QualitativeRange. Whereas, in touch device it is displayed on holding over the FeaturedMeasure, ComparativeMeasure and QualitativeRange of SfBulletGraph.

The SfBulletGraph tooltip is displayed only when the ShowToolTip property is set to true.



### FeaturedMeasureToolTipTemplate

You can display the value of FeaturedMeasure of SfBulletGraph in ToolTip that is used to view the FeaturedMeasure value .The FeaturedMeasureToolTipTemplate is DataTemplate type.

### Code Example:

{% highlight html %}

                           <syncfusion:SfBulletGraph Orientation="Horizontal"  Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"

                              QualitativeRangesSize="30"

                              QuantitativeScaleLength="400"                             

                              FeaturedMeasure="5"

                              FeaturedMeasureBarStroke="Black"

                              ComparativeMeasureSymbolStroke="Black"

                              LabelOffset="5" LabelStroke="Black"

                              MajorTickStroke="Black" MinorTickStroke="Black"

                              ShowToolTip="True"

                              CaptionPosition="Near">



            <syncfusion:SfBulletGraph.FeaturedMeasureToolTipTemplate>

                <DataTemplate>

                    <Border BorderBrush="#D3D3D3" BorderThickness="1.5" Background="#232323" CornerRadius="5">

                        <TextBlock Text="{Binding}" FontSize="14" Foreground="#D3D3D3" Margin="12 8"/>

                    </Border>

                </DataTemplate>

            </syncfusion:SfBulletGraph.FeaturedMeasureToolTipTemplate>

            <syncfusion:SfBulletGraph.QualitativeRanges>

                <syncfusion:QualitativeRange RangeEnd="4.5"

                                             RangeStroke="Red"

                                             RangeOpacity="1">

                </syncfusion:QualitativeRange>

                <syncfusion:QualitativeRange RangeEnd="7.5"

                                             RangeStroke="Yellow"

                                             RangeOpacity="1">

                </syncfusion:QualitativeRange>

                <syncfusion:QualitativeRange RangeEnd="10"

                                             RangeStroke="Green"

                                             RangeOpacity="1">

                </syncfusion:QualitativeRange>

            </syncfusion:SfBulletGraph.QualitativeRanges>



        </syncfusion:SfBulletGraph>


{% endhighlight  %}


![http://help.syncfusion.com/ug/wpf/ImagesExt/image279_20.jpg](Concept-and-Features_images/Concept-and-Features_img13.jpeg)



### ComparativeMeasureToolTipTemplate

You can display the value of ComparativeMeasure of SfBulletGraph in ToolTip that is used to view the ComparativeMeasure value. The ComparativeMeasureToolTipTemplate is DataTemplate type.

### Code Example:

{% highlight html %}


                           <syncfusion:SfBulletGraph Orientation="Horizontal"  Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"

                              QualitativeRangesSize="30"

                              QuantitativeScaleLength="400"                             

                              FeaturedMeasure="5"

                              ComparativeMeasure="4"

                              FeaturedMeasureBarStroke="Black"

                              ComparativeMeasureSymbolStroke="Black"

                              LabelOffset="5" LabelStroke="Black"

                              MajorTickStroke="Black" MinorTickStroke="Black"

                              ShowToolTip="True"

                              CaptionPosition="Near">



            <syncfusion:SfBulletGraph.ComparativeMeasureToolTipTemplate>

                <DataTemplate>

                    <Border BorderBrush="#D3D3D3" BorderThickness="1.5" Background="#232323" CornerRadius="5">

                        <TextBlock Text="{Binding}" FontSize="14" Foreground="#D3D3D3" Margin="12 8"/>

                    </Border>

                </DataTemplate>

            </syncfusion:SfBulletGraph.ComparativeMeasureToolTipTemplate>

            <syncfusion:SfBulletGraph.QualitativeRanges>

                <syncfusion:QualitativeRange RangeEnd="4.5"

                                             RangeStroke="Red"

                                             RangeOpacity="1">

                </syncfusion:QualitativeRange>

                <syncfusion:QualitativeRange RangeEnd="7.5"

                                             RangeStroke="Yellow"

                                             RangeOpacity="1">

                </syncfusion:QualitativeRange>

                <syncfusion:QualitativeRange RangeEnd="10"

                                             RangeStroke="Green"

                                             RangeOpacity="1">

                </syncfusion:QualitativeRange>

            </syncfusion:SfBulletGraph.QualitativeRanges>



        </syncfusion:SfBulletGraph>


{% endhighlight  %}


![undefined](Concept-and-Features_images/Concept-and-Features_img14.jpeg)





### QualitativeRangeToolTipTemplate

You can display the value of QualitativeRange of SfBulletGraph in ToolTip that is used to view the Start and End value of QualitativeRange. The QualitativeRangeToolTipTemplate is DataTemplate type.

### Code Example:

{% highlight html %}


                           <syncfusion:SfBulletGraph Orientation="Horizontal"  Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"

                              QualitativeRangesSize="30"

                              QuantitativeScaleLength="400"                             

                              FeaturedMeasure="5"

                              ComparativeMeasure="4"

                              FeaturedMeasureBarStroke="Black"

                              ComparativeMeasureSymbolStroke="Black"

                              LabelOffset="5" LabelStroke="Black"

                              MajorTickStroke="Black" MinorTickStroke="Black"

                              ShowToolTip="True"

                              CaptionPosition="Near">



            <syncfusion:SfBulletGraph.QualitativeRangeToolTipTemplate>

                <DataTemplate>

                    <Border BorderBrush="#D3D3D3" BorderThickness="1.5" CornerRadius="5">

                        <Border Background="{Binding RangeStroke}" Opacity="0.7" CornerRadius="5">

                            <StackPanel Orientation="Horizontal" Margin="12 8" >

                                <TextBlock Text="{Binding RangeStart}" FontSize="14" Foreground="Black"/>

                                <TextBlock Text="-" FontSize="14" Foreground="Black" Width="10" TextAlignment="Center"/>

                                <TextBlock Text="{Binding RangeEnd}" FontSize="14" Foreground="Black"/>

                            </StackPanel>

                        </Border>

                    </Border>

                </DataTemplate>

            </syncfusion:SfBulletGraph.QualitativeRangeToolTipTemplate>

            <syncfusion:SfBulletGraph.QualitativeRanges>

                <syncfusion:QualitativeRange RangeEnd="4.5"

                                             RangeStroke="Red"

                                             RangeOpacity="1">

                </syncfusion:QualitativeRange>

                <syncfusion:QualitativeRange RangeEnd="7.5"

                                             RangeStroke="Yellow"

                                             RangeOpacity="1">

                </syncfusion:QualitativeRange>

                <syncfusion:QualitativeRange RangeEnd="10"

                                             RangeStroke="Green"

                                             RangeOpacity="1">

                </syncfusion:QualitativeRange>

            </syncfusion:SfBulletGraph.QualitativeRanges>



        </syncfusion:SfBulletGraph>


{% endhighlight %}


![http://help.syncfusion.com/ug/wpf/ImagesExt/image279_22.jpg](Concept-and-Features_images/Concept-and-Features_img15.jpeg)





