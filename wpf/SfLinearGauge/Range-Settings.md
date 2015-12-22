---
layout: post
title: Range Settings | SfLinearGauge | wpf | Syncfusion
description: range settings
platform: wpf
control: SfLinearGauge 
documentation: ug
---

# Range Settings

Ranges of the linear scale are a collection of the linear range. A linear range is a visual element that starts at a specified StartValue and ends at a specified EndValue within the linear scale. These start and end values are mentioned with the help of the LinearRange class. 

## Customizing Range

The stroke of the range is personalized by changing the RangeStroke of the linear range. The appearance of linear range is customized by setting the StartWidth and EndWidth properties. With the help of the RangeOffset property, the linear range can be positioned with respect to the linear scale. By setting the RangeOpacity of the LinearRange, the opacity of the range can be modified.


{%tabs%}
{% highlight xml %}
 



        <Gauges:SfLinearGauge Orientation="Horizontal">

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale>

                    <Gauges:LinearScale.Ranges>

                        <Gauges:LinearRange StartValue="0" EndValue="35" 

                                            StartWidth="25" EndWidth="10" 

                                            RangeOffset="5" RangeOpacity="1"

                                            RangeStroke="Green"/>

                        <Gauges:LinearRange StartValue="65" EndValue="100" 

                                            StartWidth="10" EndWidth="25" 

                                            RangeOffset="5" RangeOpacity="1"

                                            RangeStroke="Red"/>

                    </Gauges:LinearScale.Ranges>

                </Gauges:LinearScale>

            </Gauges:SfLinearGauge.MainScale>

        </Gauges:SfLinearGauge>
{% endhighlight %}

{% highlight c# %}


            SfLinearGauge lineargauge = new SfLinearGauge();

            lineargauge.Orientation = Orientation.Horizontal;

            LinearScale _mainScale = new LinearScale();

            _mainScale.Ranges.Add(new LinearRange() { StartValue = 0, EndValue = 35, StartWidth = 25, EndWidth = 10,RangeOffset=5,RangeOpacity=1, RangeStroke = new SolidColorBrush(Colors.Green) });

            _mainScale.Ranges.Add(new LinearRange() { StartValue = 65, EndValue = 100, StartWidth = 10, EndWidth = 25, RangeOffset = 5, RangeOpacity = 1, RangeStroke = new SolidColorBrush(Colors.Red) });

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge);

{% endhighlight %}

{%endtabs%}


![](Concepts-and-Feature_images/Concepts-and-Feature_img6.png)



## Binding RangeStroke to Ticks and Labels

By setting the BindWithRangeStrokeToLabels, the stroke of the labels can be set related to the stroke of the specified ranges. Similarly, by setting the BindWithRangeStrokeToTicks, the stroke of the ticks can be set related to the stroke of the specified ranges.


{%tabs%}
{% highlight xml %}




       <Gauges:SfLinearGauge Orientation="Horizontal">

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale BindRangeStrokeToLabels="True"

                                    BindRangeStrokeToTicks="True">

                    <Gauges:LinearScale.Ranges>

                        <Gauges:LinearRange StartValue="0" EndValue="35" 

                                            StartWidth="15" EndWidth="15" 

                                            RangeOffset="5" RangeStroke="Green"/>

                        <Gauges:LinearRange StartValue="35" EndValue="65" 

                                            StartWidth="15" EndWidth="15" 

                                            RangeOffset="5" RangeStroke="Yellow"/>

                        <Gauges:LinearRange StartValue="65" EndValue="100" 

                                            StartWidth="15" EndWidth="15" 

                                            RangeOffset="5" RangeStroke="Red"/>

                    </Gauges:LinearScale.Ranges>

                </Gauges:LinearScale>

            </Gauges:SfLinearGauge.MainScale>

        </Gauges:SfLinearGauge>
{% endhighlight %}

{% highlight c# %}




            SfLinearGauge lineargauge = new SfLinearGauge();

            lineargauge.Orientation = Orientation.Horizontal;

            LinearScale _mainScale = new LinearScale();

            _mainScale.BindRangeStrokeToLabels = true;

            _mainScale.BindRangeStrokeToTicks = true;

            _mainScale.Ranges.Add(new LinearRange() { StartValue = 0, EndValue = 35, StartWidth = 15, EndWidth = 15, RangeOffset = 5,RangeStroke = new SolidColorBrush(Colors.Green) });

            _mainScale.Ranges.Add(new LinearRange() { StartValue = 35, EndValue = 65, StartWidth = 15, EndWidth = 15, RangeOffset = 5, RangeStroke = new SolidColorBrush(Colors.Yellow) });

            _mainScale.Ranges.Add(new LinearRange() { StartValue = 65, EndValue = 100, StartWidth = 25, EndWidth = 10, RangeOffset = 5, RangeStroke = new SolidColorBrush(Colors.Red) });

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge);

{% endhighlight %}

{%endtabs%}
![](Concepts-and-Feature_images/Concepts-and-Feature_img7.png)



## Range Position

The range can be placed above or below the scale by choosing the options available in the RangePosition property. They are:

1. Above (Default).
2. Below.

{%tabs%}
{% highlight xml %}




       <Gauges:SfLinearGauge>

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale BindRangeStrokeToLabels="True" 

                                    BindRangeStrokeToTicks="True"  

                                    RangePosition="Above"

                                    ScaleBarLength="300">

                    <Gauges:LinearScale.Ranges>

                        <Gauges:LinearRange StartValue="65" EndValue="100" 

                                            StartWidth="10" EndWidth="25" 

                                            RangeOffset="5" RangeOpacity="1"

                                            RangeStroke="Red"/>

                    </Gauges:LinearScale.Ranges>

                </Gauges:LinearScale>

            </Gauges:SfLinearGauge.MainScale>

        </Gauges:SfLinearGauge>

{% endhighlight %}


{% highlight c# %}


            SfLinearGauge lineargauge = new SfLinearGauge();

            LinearScale _mainScale = new LinearScale();

            _mainScale.BindRangeStrokeToLabels = true;

            _mainScale.BindRangeStrokeToTicks = true;

            _mainScale.ScaleBarLength = 300;

            _mainScale.RangePosition = LinearRangesPosition.Above;

            _mainScale.Ranges.Add(new LinearRange() { StartValue = 65, EndValue = 100, StartWidth = 10, EndWidth = 25, RangeOffset = 5, RangeOpacity = 1, RangeStroke = new SolidColorBrush(Colors.Red) });

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge);

{% endhighlight %}

{%endtabs%}

The following screenshot displays the Linear Gauge with the Range positioned above:

![](Concepts-and-Feature_images/Concepts-and-Feature_img8.png)



