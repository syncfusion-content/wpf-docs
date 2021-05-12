---
layout: post
title: Scale in WPF Linear Gauge control | Syncfusion
description: Learn here all about Scale support in Syncfusion WPF Linear Gauge (SfLinearGauge) control, its elements and more.
platform: wpf
control: SfLinearGauge
documentation: ug
---

# Scale in WPF Linear Gauge (SfLinearGauge)

The [`MainScale`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfLinearGauge.html#Syncfusion_UI_Xaml_Gauges_SfLinearGauge_MainScale) is a linear scale integrates ticks, labels, ranges, and pointers to customize the basic look and feel of the linear gauge.

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

    <gauge:SfLinearGauge.MainScale>
                                               
    <gauge:LinearScale  ScaleBarStroke="#E0E0E0" MajorTickStroke="Gray" MinorTickStroke="Gray" LabelStroke="#424242"   

    ScaleBarSize="10" MinorTicksPerInterval="3"/>

    </gauge:SfLinearGauge.MainScale>

    </gauge:SfLinearGauge>


{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();
           
            LinearScale linearScale = new LinearScale();

            linearScale.ScaleBarStroke = new SolidColorBrush(Color.FromRgb(224, 224, 224));

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromRgb(66, 66, 66));

            linearScale.ScaleBarSize = 10;

            linearScale.MinorTicksPerInterval = 3;

            sfLinearGauge.MainScale = linearScale;


{% endhighlight %}

{% endtabs %}

![Linear Gauge Scale](Scale_images/Scale_img1.png)

## Setting minimum and maximum values for a scale

To change the minimum and maximum values of a linear scale, use the [`Minimum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_Maximum) properties as shown in the following code snippet.

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

        <gauge:SfLinearGauge.MainScale>

            <gauge:LinearScale Minimum="0" Maximum="200" ScaleBarStroke="#E0E0E0"/>

        </gauge:SfLinearGauge.MainScale>

    </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

           SfLinearGauge sfLinearGauge = new SfLinearGauge();
           
            LinearScale linearScale = new LinearScale();

            linearScale.ScaleBarStroke = new SolidColorBrush(Color.FromRgb(224, 224, 224));

            linearScale.Minimum = 0;

            linearScale.Maximum = 200;

            sfLinearGauge.MainScale = linearScale;


{% endhighlight %}

{% endtabs %}

![Linear Gauge Scale Value](Scale_images/Scale_img2.png)

## Setting interval for a scale

The [`Interval`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_Interval) property allows to set intervals for scale. The default value of the `Interval` property is auto interval. Auto interval defines the count of the scale labels as 3 for 100 pixels.

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

    <gauge:SfLinearGauge.MainScale>

    <gauge:LinearScale Minimum="0" Maximum="500" Interval="100" ScaleBarStroke="#E0E0E0" MajorTickStroke="Gray"

    MinorTickStroke="Gray" LabelStroke="#424242" ScaleBarSize="10"/>

    </gauge:SfLinearGauge.MainScale>

    </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();
           
            LinearScale linearScale = new LinearScale();

            linearScale.Minimum = 0;

            linearScale.Maximum = 500;

            linearScale.Interval = 100;

            linearScale.ScaleBarStroke = new SolidColorBrush(Color.FromRgb(224, 224, 224));

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromRgb(66, 66, 66));

            linearScale.ScaleBarSize = 10;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![Linear Gauge Interval](Scale_images/Scale_img3.png)

## Scale customization

You can customize the color, length, size, and position of the `LinearScale` using the [`ScaleBarStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_ScaleBarStroke), [`ScaleBarBorderThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_ScaleBarBorderThickness), and [`ScaleBarBorderBrush`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_ScaleBarBorderBrush) properties, respectively.

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

    <gauge:SfLinearGauge.MainScale>

    <gauge:LinearScale ScaleBarBorderBrush="Red"  ScaleBarStroke="Blue" MajorTickStroke="Gray"

    MinorTickStroke="Gray" LabelStroke="#424242" ScaleBarBorderThickness="3"

    ScaleBarSize="20" MinorTicksPerInterval="3" />

    </gauge:SfLinearGauge.MainScale>

    </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

             SfLinearGauge sfLinearGauge = new SfLinearGauge();
           
            LinearScale linearScale = new LinearScale();

            linearScale.ScaleBarStroke = new SolidColorBrush(Colors.Blue);

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromRgb(66, 66, 66));

            linearScale.ScaleBarSize = 20;

            linearScale.ScaleBarBorderThickness = new Thickness(3);

            linearScale.ScaleBarBorderBrush = new SolidColorBrush(Colors.Red);

            linearScale.MinorTicksPerInterval = 3;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![Linear Gauge Scale Customization](Scale_images/Scale_img4.png)

### Size customization

Size of the scale can be customized using the following two properties.

* [`ScaleBarSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_ScaleBarSize) - Customizes the size of the scale bar (i.e height in case of landscape orientation).
* [`ScaleBarLength`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_ScaleBarLength) - Customizes the length of the scale bar (i.e width in case of landscape orientation).

{% tabs %}

{% highlight xml %}

 <Gauges:SfLinearGauge Background="AliceBlue" BorderBrush="Black" 
                          BorderThickness="1"
                              Height="300" Width="500">

 <Gauges:SfLinearGauge.MainScale>
         <Gauges:LinearScale ScaleBarStroke="Blue" ScaleBarSize="50" 
                  ScaleBarLength="350">
        </Gauges:LinearScale>
 </Gauges:SfLinearGauge.MainScale>
            
 </Gauges:SfLinearGauge>    

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            sfLinearGauge.Background = new SolidColorBrush(Colors.AliceBlue);

            sfLinearGauge.BorderBrush = new SolidColorBrush(Colors.Black);

            sfLinearGauge.BorderThickness = new Thickness(1);

            sfLinearGauge.Height = 300;

            sfLinearGauge.Width=500;

            LinearScale linearScale = new LinearScale();

            linearScale.ScaleBarStroke = new SolidColorBrush(Colors.Blue);
           
            linearScale.ScaleBarSize = 50;

            linearScale.ScaleBarLength = 350;
           
            sfLinearGauge.MainScale = linearScale;

            grid.Children.Add(sfLinearGauge);

{% endhighlight %}

{% endtabs %}

![Linear Gauge Scale Size Customization](Scale_images/Scale_img7.png)

## Setting scale direction

You can set the scale position to its forward and backward using the [`ScaleDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_ScaleDirection) property.

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

    <gauge:SfLinearGauge.MainScale>

    <gauge:LinearScale ScaleDirection="Backward" ScaleBarStroke="#E0E0E0" MajorTickStroke="Gray"
                       MinorTickStroke="Gray" LabelStroke="#424242"  ScaleBarSize="10" 
                       MinorTicksPerInterval="3"/>

    </gauge:SfLinearGauge.MainScale>

    </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.ScaleDirection = LinearScaleDirection.Backward;

            linearScale.ScaleBarStroke = new SolidColorBrush(Color.FromRgb(224, 224, 224));

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromRgb(66, 66, 66));

            linearScale.ScaleBarSize = 10;

            linearScale.MinorTicksPerInterval = 3;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![Linear Gauge Scale Direction](Scale_images/Scale_img5.png)

## Setting position for a scale

You can set the scale position using the [`ScaleBarPositionFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_ScaleBarPositionFactor) property. First, set the [`ElementsPositionMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_ElementsPositionMode) to custom, and then set [`ScaleBarPositionFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_ScaleBarPositionFactor).

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

    <gauge:SfLinearGauge.MainScale>

    <gauge:LinearScale  ElementsPositionMode="Custom"

    ScaleBarPositionFactor="0.5" TickPositionFactor="0.443"

    ScaleBarStroke="#E0E0E0" MajorTickStroke="Gray"

    MinorTickStroke="Gray" LabelStroke="#424242"

    MinorTickSize="9" MajorTickSize="15"

    ScaleBarSize="10" MinorTicksPerInterval="3" />

    </gauge:SfLinearGauge.MainScale>

    </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.ElementsPositionMode = LinearScalePositionModes.Custom;

            linearScale.ScaleBarPositionFactor = 0.5;

            linearScale.TickPositionFactor = 0.443;

            linearScale.MajorTickSize = 9;

            linearScale.MinorTickSize = 15;

            linearScale.ScaleBarStroke = new SolidColorBrush(Color.FromRgb(224, 224, 224));

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromRgb(66, 66, 66));

            linearScale.ScaleBarSize = 10;

            linearScale.MinorTicksPerInterval = 3;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![Linear Gauge scale position](Scale_images/Scale_img6.png)
