---
layout: post
title: Scale-Tick-Mark-Settings
description: Scale Tick Mark Settings
platform: wpf
control: Bullet Graph 
documentation: ug
---



# Scale Tick Mark Settings

## Quantitative scale is displayed with two types of ticks: 

* Major ticks, the primary scale indicators.
* Minor ticks, the secondary scale indicators that fall in between the major ticks.



## Customizing Ticks:

The stroke of the major and minor ticks is customized by setting the MajorTickStroke and MinorTickStroke properties. The size can be modified by using the MajorTickSize and MinorTickSize properties. By setting MajorTickStrokeThickness and MinorTickStrokeThickness, the stroke’s thickness is customized.



### Code Example:
{% highlight html %}




    <syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"

                                  QualitativeRangesSize="30" 

                                  QuantitativeScaleLength="400"    

                                  MinorTicksPerInterval="3"

                                  MajorTickSize="15" MinorTickSize="10"

                                  MajorTickStroke="Red" MinorTickStroke="Green">

        </syncfusion:SfBulletGraph>



{% endhighlight  %}
{% highlight c# %}



  SfBulletGraph bulletgraph = new SfBulletGraph();

      bulletgraph.FlowDirection = BulletGraphFlowDirection.Forward;

      bulletgraph.Orientation = Orientation.Horizontal;

      bulletgraph.QualitativeRangesSize = 30;

      bulletgraph.QuantitativeScaleLength = 400;

      bulletgraph.Minimum = 0;

      bulletgraph.Maximum = 10;

      bulletgraph.Interval = 2;

      bulletgraph.MinorTicksPerInterval = 3;

      bulletgraph.MajorTickSize = 15;

      bulletgraph.MinorTickSize = 10;

      bulletgraph.MajorTickStroke = new SolidColorBrush(Colors.Red);

      bulletgraph.MinorTickStroke = new SolidColorBrush(Colors.Green);

      this.Grid.Children.Add(bulletgraph);



{% endhighlight  %}

![C:/Users/Giftline/Desktop/New folder/7.jpg](Concept-and-Features_images/Concept-and-Features_img9.png)





## TickPosition:

The ticks in the scale can be placed above or below the ranges of the quantitative scale by choosing the options available in the TickPosition property. 

They are:

1. Below (Default)
1. Above
2. Cross

## Code Example:

{% highlight html %}


        <syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2"  FlowDirection="Forward"

                                  QualitativeRangesSize="30" 

                                  QuantitativeScaleLength="400"

                                  Minimum="0" Maximum="10" Interval="2" 

                                  MinorTicksPerInterval="2"

                                  MinorTickStrokeThickness="1"

                                  MajorTickSize="30" MinorTickSize="30"

                                  MajorTickStroke="Black" MinorTickStroke="Black"                                  

                                  TickPosition="Cross">

        </syncfusion:SfBulletGraph>
{% endhighlight %}

{% highlight c# %}




        SfBulletGraph bulletgraph = new SfBulletGraph();

            bulletgraph.FlowDirection = BulletGraphFlowDirection.Forward;

            bulletgraph.Orientation = Orientation.Horizontal;

            bulletgraph.QualitativeRangesSize = 30;

            bulletgraph.QuantitativeScaleLength = 400;

            bulletgraph.Minimum = 0;

            bulletgraph.Maximum = 10;

            bulletgraph.Interval = 2;

            bulletgraph.MinorTicksPerInterval = 2;

            bulletgraph.MinorTickStrokeThickness = 1;

            bulletgraph.MajorTickSize = 30;

            bulletgraph.MinorTickSize = 30;

            bulletgraph.MajorTickStroke = new SolidColorBrush(Colors.Black);

            bulletgraph.MinorTickStroke = new SolidColorBrush(Colors.Black);

            bulletgraph.TickPosition = BulletGraphTicksPosition.Cross; 

            this.Grid.Children.Add(bulletgraph);



{% endhighlight %}



![](Concept-and-Features_images/Concept-and-Features_img10.png)



## Scale Label settings

### Labels:

A quantitative scale label specifies the numeric value according to the major ticks in the range of the scale.

### Customizing Labels:

The label’s offset is changed by using the LabelOffset property. The foreground of the label is customized by setting LabelStroke. By setting LabelSize, the font size of the labels is modified. 

### Code Example:

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



### Label Position

The labels in the scale can be placed above or below the qualitative ranges by choosing the following options available in the LabelPosition property. 

1. Below (Default)
2. Above

### Code Example:

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





