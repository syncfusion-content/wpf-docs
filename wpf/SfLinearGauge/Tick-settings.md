---
layout: post
title: Tick settings | SfLinearGauge | wpf | Syncfusion
description: tick settings
platform: wpf
control: SfLinearGauge
documentation: ug
---

# Tick settings

Ticks are of two types: major and minor. These ticks are arranged with respect to the specified frequency that is, interval of the linear scale. The minor ticks are displayed by using the MinorTicksPerInterval property.

## Customizing Ticks

By setting the MajorTickStroke and MinorTickStroke, the stroke of the major ticks and minor ticks are personalized. With the help of the MajorTickStrokeThickness and MinorTickStrokeThickness, the stroke thickness of the major and minor ticks is customized. The size of the major ticks and minor ticks can be modified by using the MajorTickSize and MinorTickSize properties.


{%tabs%}
{% highlight xml %}




        <Gauges:SfLinearGauge Name="linearGauge" Orientation="Horizontal">

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale Minimum="0" Maximum="10"

                                    Interval="100" MinorTicksPerInterval="3"

                                    MajorTickSize="15" MinorTickSize="10"

                                    MajorTickStroke="Red" MinorTickStroke="Yellow"

                                    MajorTickStrokeThickness="2" 

                                    MinorTickStrokeThickness="1">

                </Gauges:LinearScale>

            </Gauges:SfLinearGauge.MainScale>

        </Gauges:SfLinearGauge> 
{% endhighlight %}

{% highlight c# %}




            SfLinearGauge lineargauge = new SfLinearGauge();

            lineargauge.Orientation = Orientation.Horizontal;

            LinearScale _mainScale = new LinearScale();

            _mainScale.Minimum = 0;

            _mainScale.Maximum = 10;

            _mainScale.Interval = 100;

            _mainScale.MinorTicksPerInterval = 3;

            _mainScale.MajorTickSize = 15;

            _mainScale.MinorTickSize = 10;

            _mainScale.MajorTickStroke = new SolidColorBrush(Colors.Red);

            _mainScale.MinorTickStroke = new SolidColorBrush(Colors.Yellow);

            _mainScale.MajorTickStrokeThickness = 2;

            _mainScale.MinorTickStrokeThickness = 1;

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge);

{% endhighlight %}

{%endtabs%}

The following screenshot illustrates customizingthe Ticks of the Linear Gauge:

![](Concepts-and-Feature_images/Concepts-and-Feature_img10.png)



## Tick Position

The ticks in the scale can be placed above, below, or in between the scale by choosing the following options that are available in the TickPosition property. 

1. Above.
2. Below (Default).
3. Cross.


{%tabs%}

{% highlight xml %}




        <Gauges:SfLinearGauge>

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale TickPosition="Cross"

                                    ScaleBarLength="300" 

                                    Minimum="0" Maximum="100"

                                    MajorTickStroke="Black" MinorTicksPerInterval="2"

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

            _mainScale.Minimum = 0;

            _mainScale.Maximum = 100;

          _mainScale.MinorTicksPerInterval = 3;

           _mainScale.Interval = 2;

           _mainScale.MajorTickStroke = new SolidColorBrush(Colors. Black));

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge);

{% endhighlight %}

{%endtabs%}

The following screenshot displays Ticks Positioned across the Scale: 

![](Concepts-and-Feature_images/Concepts-and-Feature_img11.png)



