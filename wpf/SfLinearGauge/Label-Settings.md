---
layout: post
title: Label Settings | SfLinearGauge | wpf | Syncfusion
description: label settings
platform: wpf
control: SfLinearGauge 
documentation: ug
---


# Label Settings

Labels of the linear scale provide a numeric value to the major ticks that are specified according to the range of the scale.

## Customizing Labels

The foreground of the label is customized by setting the LabelStroke of the linear scale. By making use of the LabelSize property, the font size of the labels is personalized. The labels can be positioned away from the ticks by using the LabelOffset property.


{%tabs%}
{% highlight xaml %}




        <Gauges:SfLinearGauge Name="linearGauge" Orientation="Horizontal">

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale LabelStroke="Red" Minimum="0" Maximum="10" Interval="1"  MinorTicksPerInterval="3"

                                    LabelSize="13" 

                                    LabelOffset="5">

                </Gauges:LinearScale>

            </Gauges:SfLinearGauge.MainScale>

        </Gauges:SfLinearGauge>
{% endhighlight %}

{% highlight c# %}


            SfLinearGauge lineargauge = new SfLinearGauge();

            LinearScale _mainScale = new LinearScale();

            _mainScale.Minimum = 0;

            _mainScale.Maximum = 10;

            _mainScale.MinorTicksPerInterval = 3;

            _mainScale.LabelStroke = new SolidColorBrush(Colors.Red);

            _mainScale.LabelSize = 13;

            _mainScale.LabelOffset = 5;

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge);

{% endhighlight %}
{%endtabs%}


The following screenshot illustrates customizing Labels of the Linear Gauge:

![](Concepts-and-Feature_images/Concepts-and-Feature_img1.png)



## Label Position

The labels in the scale can be placed above or below the linear scale by choosing the following options that are available in the LabelPosition property. 

1. Above.
2. Below (Default).

{%tabs%}
{% highlight xaml %}




        <Gauges:SfLinearGauge>

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale TickPosition="Cross"

                                    ScaleBarLength="300" 

                                    LabelPosition="Above"

                                    Minimum="0" Maximum="100"

                                    LabelStroke="Black"

                                    LabelSize="14"	

                                    Interval="10">

                </Gauges:LinearScale>

            </Gauges:SfLinearGauge.MainScale>

        </Gauges:SfLinearGauge>
{% endhighlight %}

{% highlight c# %}




            SfLinearGauge lineargauge = new SfLinearGauge();

            LinearScale _mainScale = new LinearScale();

            _mainScale.ScaleBarLength = 300;

            _mainScale.TickPosition = LinearTicksPosition.Cross;

            _mainScale.LabelPosition = LinearLabelsPosition.Above;

            _mainScale.Minimum = 0;

            _mainScale.Maximum = 100;

            _mainScale.LabelStroke = new SolidColorBrush(Colors.White);

            _mainScale.LabelSize = 14;

            _mainScale.Interval = 10;

            _mainScale.MajorTickStroke = new SolidColorBrush(Colors.Black);

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge); 

{% endhighlight %}
{%endtabs%}


The following screenshot illustrates the labels positioned above the Scale:

![](Concepts-and-Feature_images/Concepts-and-Feature_img2.png)



