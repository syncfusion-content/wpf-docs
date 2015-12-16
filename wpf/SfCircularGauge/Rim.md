---
layout: post
title: Rim | SfCircularGauge | Wpf | Syncfusion
description: Rim
platform: wpf
control: SfCircularGauge
documentation: ug
---

# Rim

Scale determines the structure of the circular gauge using the circular rim. By setting the StartAngle, SweepDirection and SweepAngle properties, you can shape the circular gauge into a full circular gauge, half circular gauge, or quarter circular gauge.

The StartValue and EndValue properties will determine the overall range of the circular rim. The rim’s stroke and stroke thickness can be set using the RimStroke and RimStrokeThickness properties.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfCircularGauge x:Name="gauge">
            <syncfusion:SfCircularGauge.Scales >
                <syncfusion:CircularScale 
                                            StartAngle="180" 
                                            SweepAngle="180"
                                            SweepDirection="Clockwise"
                                            StartValue="0" 
                                            EndValue="100"
                                            RimStroke="Red" 
                                            RimStrokeThickness="3"
                                            >
                </syncfusion:CircularScale>
            </syncfusion:SfCircularGauge.Scales >
        </syncfusion:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge();
            CircularScale _mainscale = new CircularScale();
            _mainscale.StartAngle = 180;
            _mainscale.SweepAngle = 180;
            _mainscale.SweepDirection = SweepDirection.Clockwise;
            _mainscale.StartValue = 0;
            _mainscale.EndValue = 100;
            _mainscale.RimStroke = new SolidColorBrush(Colors.Red);
            _mainscale.RimStrokeThickness = 3;
            circularGauge.Scales.Add(_mainscale);
            this.Grid.Children.Add(circularGauge);

{% endhighlight %}
{% endtabs %}

![](Rim_images/Rim_img1.jpeg)
