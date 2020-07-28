---
layout: post
title: Rim | SfCircularGauge | Wpf | Syncfusion
description: This section describes SfCircularGauge Rim customization and position the rim based on the RadiusFactor value and Radius value.
platform: wpf
control: SfCircularGauge
documentation: ug
---

# SfCircularGauge Rim customization

Scale determines the structure of a circular gauge by using a circular rim. By setting the `StartAngle` and `SweepAngle` properties, you can change the shape of the circular gauge to a full-circular gauge, half-circular gauge, or quarter-circular gauge.

The `StartValue` and `EndValue` properties, determine the overall range of the circular rim.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge  HeaderAlignment="Bottom">

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale StartAngle="270" SweepAngle="360" StartValue="0" EndValue="360"
                                     Interval="20" MinorTicksPerInterval="0" >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Hidden"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale circularScale = new CircularScale();

circularScale.StartAngle = 270;

circularScale.SweepAngle = 360;

circularScale.StartValue = 0;

circularScale.EndValue = 360;

circularScale.Interval = 20;

circularScale.MinorTicksPerInterval = 0;

CircularPointer circularPointer = new CircularPointer();

circularPointer.NeedlePointerVisibility = Visibility.Hidden;

circularScale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Rim startValue enadValue image](Rim_images/Rim_StartValue_EnadValue.png)

## Rim customization

The color and thickness of the rim can be set by using the [`RimStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGauge.WPF~Syncfusion.UI.Xaml.Gauges.CircularScale~RimStroke.html) and [`RimStrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGauge.WPF~Syncfusion.UI.Xaml.Gauges.CircularScale~RimStrokeThickness.html) properties.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale RadiusFactor="1" RimStrokeThickness="40" RimStroke="SkyBlue" >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Hidden"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

 SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale circularScale = new CircularScale();

circularScale.RadiusFactor = 1;

circularScale.RimStrokeThickness = 40;

circularScale.RimStroke = new SolidColorBrush(Colors.SkyBlue);

CircularPointer circularPointer = new CircularPointer();

circularPointer.NeedlePointerVisibility = Visibility.Hidden;

circularScale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Rim customization image](Rim_images/Rim_customization.png)

## Setting a position for rim

You can customize the position of [`Scales`](https://help.syncfusion.com/cr/cref_files/wpf/gauge/Syncfusion.Gauge.WPF~Syncfusion.Windows.Gauge.CircularGauge~Scales.html) in the following two ways:
1.	 [`RadiusFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGauge.WPF~Syncfusion.UI.Xaml.Gauges.CircularScale~RadiusFactor.html) property.
2.	 [`Radius`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGauge.WPF~Syncfusion.UI.Xaml.Gauges.CircularScale~Radius.html) property.

### Setting a radius factor for rim

The value for `RadiusFactor` should be specified in offset value. `RadiusFactor` sets the scale responsive with the window. 

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale RadiusFactor="0.6" RimStrokeThickness="30" >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Hidden"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>
                
    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale circularScale = new CircularScale();

circularScale.RadiusFactor = 0.6;

circularScale.RimStrokeThickness = 30;

CircularPointer circularPointer = new CircularPointer();

circularPointer.NeedlePointerVisibility = Visibility.Hidden;

circularScale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Rim with RadiusFactor image](Rim_images/Rim_with_RadiusFactor.png)

### Setting a radius for rim

You can set the `Radius` of rim in pixel value. `Radius` sets the scale fixed with the given pixel value. 

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge  HeaderAlignment="Bottom">

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale Radius ="100" >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Hidden"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale circularScale = new CircularScale();

circularScale.Radius = 100;

CircularPointer circularPointer = new CircularPointer();

circularPointer.NeedlePointerVisibility = Visibility.Hidden;

circularScale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Rim with Radius image](Rim_images/Rim_with_Radius.png)

### Setting rim visibility

The [`ShowRim`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGauge.WPF~Syncfusion.UI.Xaml.Gauges.CircularScale~ShowRim.html) property is a Boolean property, which is used to enable or disable the rim in circular gauge.

N> Default value of the ShowRim property is true.

{% tabs %}

{% highlight xaml %}

       <gauge:SfCircularGauge  HeaderAlignment="Bottom">
           <gauge:SfCircularGauge.Scales >
                 <gauge:CircularScale ShowRim="False" x:Name="scale" >
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
            mainscale.ShowRim = false;
            CircularPointer circularPointer = new CircularPointer();
            circularPointer.NeedlePointerVisibility = Visibility.Hidden;
            mainscale.Pointers.Add(circularPointer);
            sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![Show rim support in WPF Circular Gauge](Rim_images/show-rim.png)

### Set offset value for a responsive window in rim

* [`RimStartOffset`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGauge.WPF~Syncfusion.UI.Xaml.Gauges.CircularScale~RimStartOffset.html) - Sets the rim start offset position. Its range is from 0 to 1.
* [`RimEndOffset`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGauge.WPF~Syncfusion.UI.Xaml.Gauges.CircularScale~RimEndOffset.html) - Sets the rim end offset position. Its range is from 0 to 1.

{% tabs %}

{% highlight xaml %}

        <gauge:SfCircularGauge x:Name="gauge">
             <gauge:SfCircularGauge.Scales >
                  <gauge:CircularScale  x:Name="scale" RimStartOffset="0.6" RimEndOffset="0.7" RimStroke="LightGray"  >
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
            mainscale.RimStroke = new SolidColorBrush(Colors.LightGray);
            mainscale.RimStartOffset = 0.6;
            mainscale.RimEndOffset = 0.7;
            CircularPointer circularPointer = new CircularPointer();
            circularPointer.NeedlePointerVisibility = Visibility.Hidden;
            mainscale.Pointers.Add(circularPointer);
            sfCircularGauge.Scales.Add(mainscale);
			
{% endhighlight %}

{% endtabs %}

![Start and End offset support in WPF Circular Gauge rim](Rim_images/rim-offset.png)