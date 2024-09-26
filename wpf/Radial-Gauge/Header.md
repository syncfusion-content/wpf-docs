---
layout: post
title: Header in WPF Radial Gauge control | Syncfusion
description: Learn here all about Header support in Syncfusion WPF Radial Gauge (SfCircularGauge) control and more.
platform: wpf
control: SfCircularGauge
documentation: ug
---

# Header in WPF Radial Gauge (SfCircularGauge)

Header allows you to show text or any UI content inside the gauge control using [`GaugeHeader`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfCircularGauge.html#Syncfusion_UI_Xaml_Gauges_SfCircularGauge_GaugeHeader) option. This provides information about the data that is being plotted in the circular gauge.

## Setting Header for Circular Gauge

The [`GaugeHeader`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfCircularGauge.html#Syncfusion_UI_Xaml_Gauges_SfCircularGauge_GaugeHeader) is an object that can be used to set a unique header for the circular gauge. You can add text and images as header in the circular gauge. Only one header can be added in a circular gauge.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge  HeaderAlignment="Center">

    <gauge:SfCircularGauge.GaugeHeader>

    <TextBlock Text="Temperature (K)"

     Height="40" Width="100"

     FontSize="13" Foreground="Black"/>

    </gauge:SfCircularGauge.GaugeHeader>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale>

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Hidden"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

TextBlock textBlock = new TextBlock();

textBlock.Text = "Temperature (K)";

textBlock.Height = 40;

textBlock.Width = 100;

textBlock.FontSize = 13;

textBlock.Foreground = new SolidColorBrush(Colors.Black);

sfCircularGauge.GaugeHeader = textBlock;

sfCircularGauge.HeaderAlignment = HeaderAlignment.Center;

CircularPointer circularPointer = new CircularPointer();

circularPointer.NeedlePointerVisibility = Visibility.Hidden;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

this.Content = sfCircularGauge;

{% endhighlight %}

{% endtabs %}

![CircularGauge Header in WPF Radial Gauge](header_images/wpf-radial-gauge-header.png)

## Setting alignment for header

The gauge header can be positioned by using the [`HeaderAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfCircularGauge.html#Syncfusion_UI_Xaml_Gauges_SfCircularGauge_HeaderAlignment) property. The default value of this property is `Left`.

It includes the following options:

* Left

* Right

* Top

* Bottom

* Center

* TopLeft

* TopRight

* BottomLeft

* BottomRight

* Custom

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge  HeaderAlignment="Top">

    <gauge:SfCircularGauge.GaugeHeader>

    <TextBlock Text="Temperature (K)"

     Height="40" Width="100"

     FontSize="13" Foreground="Black"/>

    </gauge:SfCircularGauge.GaugeHeader>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale>

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Hidden"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

TextBlock textBlock = new TextBlock();

textBlock.Text = "Temperature (K)";

textBlock.Height = 40;

textBlock.Width = 100;

textBlock.FontSize = 13;

textBlock.Foreground = new SolidColorBrush(Colors.Black);

sfCircularGauge.GaugeHeader = textBlock;

sfCircularGauge.HeaderAlignment = HeaderAlignment.Top;

CircularPointer circularPointer = new CircularPointer();

circularPointer.NeedlePointerVisibility = Visibility.Hidden;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

this.Content = sfCircularGauge;

{% endhighlight %}

{% endtabs %}

![CircularGauge Header with customization in WPF Radial Gauge](header_images/wpf-radial-gauge-header-alignment.png)

## Setting position for header

The [`GaugeHeaderPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfCircularGauge.html#Syncfusion_UI_Xaml_Gauges_SfCircularGauge_GaugeHeaderPosition) property is used to place header in the circular gauge. The value for `GaugeHeaderPosition` should be specified in offset value. In the point value, which has been given for the `GaugeHeaderPosition`, the first value represent x-coordinate and the second value represents y-coordinate. First, set the `HeaderAlignment` to custom, then set the position of header.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge  HeaderAlignment="Custom" GaugeHeaderPosition="0.5,0.8">

    <gauge:SfCircularGauge.GaugeHeader>

    <TextBlock Text="Temperature (K)"

     Height="40" Width="100"

     FontSize="13" Foreground="Black"/>

    </gauge:SfCircularGauge.GaugeHeader>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale>

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Hidden"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

  SfCircularGauge sfCircularGauge = new SfCircularGauge();

            CircularScale mainscale = new CircularScale();

            TextBlock textBlock = new TextBlock();

            textBlock.Text = "Temperature (K)";

            textBlock.Height = 40;

            textBlock.Width = 100;

            textBlock.FontSize = 13;

            textBlock.Foreground = new SolidColorBrush(Colors.Black);

            sfCircularGauge.GaugeHeader = textBlock;

            sfCircularGauge.HeaderAlignment = HeaderAlignment.Custom;

            sfCircularGauge.GaugeHeaderPosition = new Point(0.5, 0.8);

            CircularPointer circularPointer = new CircularPointer();

            circularPointer.NeedlePointerVisibility = Visibility.Hidden;

            mainscale.Pointers.Add(circularPointer);

            sfCircularGauge.Scales.Add(mainscale);

            this.Content = sfCircularGauge;

{% endhighlight %}

{% endtabs %}

![CircularGauge header with custom position in WPF Radial Gauge](header_images/wpf-radial-gauge-header-custon-position.png)

## Customization of header font

You can customize the header’s text by using the `FontFamily`, `FontStyle`, `FontSize`, and `Foreground` properties.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge  HeaderAlignment="Custom" GaugeHeaderPosition="0.5,0.8"

     FontFamily="Monotype Corsiva" FontSize="15"

     FontStyle="Italic"  Foreground="Blue">

    <gauge:SfCircularGauge.GaugeHeader>

    <TextBlock Text="Temperature (K)"

     Height="40" Width="100" />

    </gauge:SfCircularGauge.GaugeHeader>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Hidden"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

 SfCircularGauge sfCircularGauge = new SfCircularGauge();

            CircularScale mainscale = new CircularScale();

            TextBlock textBlock = new TextBlock();

            textBlock.Text = "Temperature (K)";

            textBlock.Height = 40;

            textBlock.Width = 100;

            sfCircularGauge.GaugeHeader = textBlock;

            sfCircularGauge.HeaderAlignment = HeaderAlignment.Custom;

            sfCircularGauge.GaugeHeaderPosition = new Point(0.5, 0.8);

            sfCircularGauge.FontSize = 15;

            sfCircularGauge.FontFamily = new FontFamily("Monotype Corsiva");

            sfCircularGauge.FontStyle = FontStyles.Italic;

            sfCircularGauge.Foreground = new SolidColorBrush(Colors.Blue);

            CircularPointer circularPointer = new CircularPointer();

            circularPointer.NeedlePointerVisibility = Visibility.Hidden;

            mainscale.Pointers.Add(circularPointer);

            sfCircularGauge.Scales.Add(mainscale);

            this.Content = sfCircularGauge;
  
{% endhighlight %}

{% endtabs %}

![CircularGauge Header with customization in WPF Radial Gauge](header_images/wpf-radial-gauge-header-customization.png)





