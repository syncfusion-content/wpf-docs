---
layout: post
title: Scale Settings | SfLinearGauge | wpf | Syncfusion
description: scale settings
platform: wpf
control: SfLinearGauge 
documentation: ug
---

# Scale Settings

The MainScale is a linear scale that integrates ticks, labels, and scale bar to specify the basic look and feel of the Linear Gauge. It defines the overall minimum and maximum values as well as the frequency of labels and ticks through the interval of the scale. It can contain multiple ranges within a scale. It also contains one or more pointers to the measures of the linear scale. 

## Customizing the MainScale

The range of the main scale can be mentioned by Minimum and Maximum of the linear scale. The width and height of the linear scale is customized by using the ScaleBarLength and ScaleBarSize properties respectively. The border thickness of the linear scale is changed by using the ScaleBarBorderThickness property. The direction of the linear scale is personalized by setting the ScaleDirection property of the linear scale.


{%tabs%}
{% highlight xaml %}




        <Gauges:SfLinearGauge Name="linearGauge" Orientation="Horizontal">

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale ScaleDirection="Forward"

                                    ScaleBarStroke="Black" 

                                    ScaleBarSize="20" 

                                    ScaleBarLength="350"

                                    ScaleBarBorderThickness="1"

                                         Interval="1"

                                    Minimum="0" Maximum="10">

                    <Gauges:LinearScale.Ranges>

                        <Gauges:LinearRange StartValue="0" EndValue="5" 

                                            StartWidth="10" EndWidth="10" 

                                            RangeStroke="Green"/>

                        <Gauges:LinearRange StartValue="5" EndValue="10" 

                                            StartWidth="10" EndWidth="10" 

                                            RangeStroke="Red"/>

                    </Gauges:LinearScale.Ranges>

                    <Gauges:LinearScale.Pointers>

                        <Gauges:LinearPointer Value="3" PointerType="BarPointer" />

                        <Gauges:LinearPointer Value="3" PointerType="SymbolPointer"/>

                    </Gauges:LinearScale.Pointers>

                </Gauges:LinearScale>

            </Gauges:SfLinearGauge.MainScale>

        </Gauges:SfLinearGauge>
{% endhighlight %}

{% highlight c# %}




            SfLinearGauge lineargauge = new SfLinearGauge();

            lineargauge.Orientation = Orientation.Horizontal;

            LinearScale _mainScale = new LinearScale();

            _mainScale.ScaleDirection = LinearScaleDirection.Forward;

            _mainScale.ScaleBarStroke = new SolidColorBrush(Colors.Black);

            _mainScale.ScaleBarSize = 20;

            _mainScale.ScaleBarLength = 350;

            _mainScale.ScaleBarBorderThickness = new Thickness(1);

            _mainScale.Interval = 1;

            _mainScale.Minimum = 0;

            _mainScale.Maximum = 10;

            _mainScale.Ranges.Add(new LinearRange(){ StartValue = 0, EndValue = 5, StartWidth = 10, EndWidth = 10, RangeStroke = new SolidColorBrush(Colors.Green) });

            _mainScale.Ranges.Add(new LinearRange() { StartValue = 5, EndValue = 10, StartWidth = 10, EndWidth = 10, RangeStroke = new SolidColorBrush(Colors.Red) });

            _mainScale.Pointers.Add(new LinearPointer(){Value=3,PointerType=LinearPointerType.BarPointer});

            _mainScale.Pointers.Add(new LinearPointer(){Value=3,PointerType=LinearPointerType.SymbolPointer});

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge);
{% endhighlight %}


{%endtabs%}

The following screenshot displaysthe Linear Gauge:

![](Concepts-and-Feature_images/Concepts-and-Feature_img9.png)



