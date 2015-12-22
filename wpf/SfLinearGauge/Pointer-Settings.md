---
layout: post
title: Pointer Settings | SfLinearGauge | wpf | Syncfusion
description: pointer settings
platform: wpf
control: SfLinearGauge 
documentation: ug
---

# Pointer Settings

Multiple pointers are added to the Linear Gauge to point multiple values on the same linear scale. This is useful for showing a low and a high value at the same time. Value of the pointer is set by the Value property. There are two types of pointers to choose from by using the PointerType property. Movement of the pointer can be animated by enabling the EnableAnimation property.

## Bar Pointer

Bar pointer is an accenting line or colored bar that is placed on the Linear Gauge to mark the values. Bar pointer’s UI is customized by using the BarPointerStroke and BarPointerStrokeThickness properties.


{%tabs%}
{% highlight xaml %}




        <Gauges:SfLinearGauge>

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale BindRangeStrokeToLabels="True"

                                    BindRangeStrokeToTicks="True"

                                    ScaleBarLength="300">

                    <Gauges:LinearScale.Pointers>

                        <Gauges:LinearPointer PointerType="BarPointer" Value="40" />

                    </Gauges:LinearScale.Pointers>

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

            _mainScale.ScaleBarLength = 300;

            _mainScale.Pointers.Add(new LinearPointer() { PointerType = LinearPointerType.BarPointer,Value=40 });

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge);

{% endhighlight %}

{%endtabs%}

The following screenshot illustrates the Linear Gauge with Bar Pointer:

![](Concepts-and-Feature_images/Concepts-and-Feature_img3.png)



## Symbol Pointer

In the symbol pointer type, the value is pointed by a symbol on the scale. You can modify the symbol pointer’s size by changing the SymbolPointerHeight and SymbolPointerWidth properties. The stroke of the symbol pointer is changed by using the SymbolPointerStroke property. The SymbolPointerStyle property is used to select the symbol pointer style.


{%tabs%}
{% highlight xaml %}




       <Gauges:SfLinearGauge>

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale BindRangeStrokeToLabels="True"

                                    BindRangeStrokeToTicks="True"

                                    ScaleBarLength="300">

                    <Gauges:LinearScale.Pointers>

                        <Gauges:LinearPointer PointerType="SymbolPointer" Value="40"  SymbolPointerStyle = "Triangle"/>

                    </Gauges:LinearScale.Pointers>

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

            _mainScale.ScaleBarLength = 300;

            _mainScale.Pointers.Add(new LinearPointer() { PointerType = LinearPointerType.SymbolPointer,Value=40, SymbolPointerStyle = LinearSymbolPointerStyle.Triangle });

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge);
{% endhighlight %}


{%endtabs%}

The following screenshot illustrates the Linear Gauge with Symbol Pointer:

![](Concepts-and-Feature_images/Concepts-and-Feature_img4.png)



## Pointer Position

The SymbolPointer in the scale can be placed above, below, or in between the scale by choosing the following options that are available in the SymbolPointerPosition property. 

1. Above.
2. Below (Default).
3. Cross.

{%tabs%}
{% highlight xaml %}




   <Gauges:SfLinearGauge Name="linearGauge" Orientation="Horizontal">

            <Gauges:SfLinearGauge.MainScale>

                <Gauges:LinearScale ScaleDirection="Forward"

                                    ScaleBarStroke="Black" 

                                    ScaleBarSize="20" 

                                    ScaleBarLength="350"

                                    ScaleBarBorderThickness="1"

                                         Interval="10" MinorTicksPerInterval="3"

                                    Minimum="0" Maximum="100">

                    <Gauges:LinearScale.Pointers>

                        <Gauges:LinearPointer Value="40" PointerType="BarPointer" />

                        <Gauges:LinearPointer Value="40" PointerType="SymbolPointer" SymbolPointerPosition="Above"/>



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

            _mainScale.Interval = 10;

            _mainScale.Minimum = 0;

            _mainScale.Maximum = 100;

            _mainScale.Pointers.Add(new LinearPointer() { Value = 40, PointerType = LinearPointerType.BarPointer });

            _mainScale.Pointers.Add(new LinearPointer() { Value = 40, PointerType = LinearPointerType.SymbolPointer , SymbolPointerPosition=LinearSymbolPointersPosition.Above});

            lineargauge.MainScale = _mainScale;

            this.Grid.Children.Add(lineargauge);

{% endhighlight %}

{%endtabs%}



The following screenshot illustrates the SymbolPointer:

![](Concepts-and-Feature_images/Concepts-and-Feature_img5.png)


