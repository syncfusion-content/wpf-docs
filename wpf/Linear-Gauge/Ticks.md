---
layout: post
title: Ticks | SfCLinearGauge | Wpf | Syncfusion
description: Ticks in WPF Linear Gauge are used to indicate the interval value. And able to customize the tick UI with its properties. 
platform: wpf
control: SfCLinearGauge
 documentation: ug
---

# Ticks support in WPF Linear Gauge (SfLinearGauge) with customization

Ticks are used to identify the gauge’s data value by marking the gauge scale in regular increments.

## Tick customization

By setting the [`MajorTickStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_MajorTickStroke) and [`MinorTickStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_MinorTickStroke) properties, the stroke of the major ticks and minor ticks can be customized. Using the [`MajorTickStrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_MajorTickStrokeThickness) and [`MinorTickStrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_MinorTickStrokeThickness), the stroke thickness of the major ticks and minor ticks can be customized. The size of the major ticks and minor ticks can be modified using the [`MajorTickSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_MajorTickSize) and [`MinorTickSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_MinorTickSize) properties.

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

    <gauge:SfLinearGauge.MainScale>

    <gauge:LinearScale MajorTickSize="20" MinorTickSize="9"

    ScaleBarStroke="#E0E0E0" MajorTickStroke="SkyBlue"

    MinorTickStroke="Brown" LabelStroke="#424242"

    MinorTickStrokeThickness="1" MajorTickStrokeThickness="2"

    ScaleBarSize="10" MinorTicksPerInterval="3" />

    </gauge:SfLinearGauge.MainScale>

    </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.ScaleBarStroke = new SolidColorBrush(Color.FromRgb(224, 224, 224));

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.SkyBlue);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Brown);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromRgb(66, 66, 66));

            linearScale.MinorTickStrokeThickness = 1;

            linearScale.MajorTickStrokeThickness = 2;

            linearScale.MajorTickSize = 20;

            linearScale.MinorTickSize = 9;

            linearScale.ScaleBarSize = 10;

            linearScale.MinorTicksPerInterval = 3;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![Linear Gauge Ticks appearance customization](Ticks_images/Ticks_img1.png)

## Setting position for tick

The ticks in the scale can be placed above, below, or in between the scale by choosing one of the following options available in the [`TickPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_TickPosition) property:

1.	Above

2.	Below (Default)

3.	Cross

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

    <gauge:SfLinearGauge.MainScale>

    <gauge:LinearScale TickPosition="Cross" MajorTickSize="20" MinorTickSize="9"

    ScaleBarStroke="#E0E0E0" MajorTickStroke="Black" MinorTickStroke="Black" LabelStroke="#424242"

    ScaleBarSize="40" MinorTicksPerInterval="3" />

    </gauge:SfLinearGauge.MainScale>

    </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.ScaleBarStroke = new SolidColorBrush(Color.FromRgb(224, 224, 224));

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Black);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Black);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromRgb(66, 66, 66));

            linearScale.MajorTickSize = 20;

            linearScale.MinorTickSize = 9;

            linearScale.TickPosition = LinearTicksPosition.Cross;

            linearScale.ScaleBarSize = 40;

            linearScale.MinorTicksPerInterval = 3;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![Linear Gauge with Ticks position customization](Ticks_images/Ticks_img2.png)

## Setting minor ticks per interval

The [`Interval`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_Interval) property is used to calculate the tick counts for a scale. Like ticks, minor ticks can also be calculated by using the [`MinorTicksPerInterval`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_MinorTicksPerInterval) property.

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

    <gauge:SfLinearGauge.MainScale>

    <gauge:LinearScale ScaleBarStroke="#E0E0E0" MajorTickStroke="Gray"

    MinorTickStroke="Gray" LabelStroke="#424242"

    ScaleBarSize="10" MinorTicksPerInterval="4" />

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

            linearScale.ScaleBarLength = 300;

            linearScale.MinorTicksPerInterval = 4;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![Linear Gauge Ticks interval customization](Ticks_images/Ticks_img3.png)