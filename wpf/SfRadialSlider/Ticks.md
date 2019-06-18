---
layout: post
title: Ticks | SfRadialSlider  | wpf | Syncfusion
description: ticks 
platform: wpf
control: SfRadialSlider
documentation: ug
---

# Ticks 

Ticks are placed along the round track in a uniform manner. The position of tick marks can be customized.

### Tick Frequency

The [TickFrequency](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~TickFrequency.html) property is used to define the number of ticks along the track, based on Minimum and Maximum values.


{% highlight XAML %}

<syncfusion:SfRadialSlider Minimum="0" Maximum="100"  

TickFrequency="5" />


{% endhighlight %}


![Ticks frequency](Concepts_images/Concepts_img2.png) 

## Sweep direction

You can use `SweepDirection` property in `SfRadialSlider` for the changing the direction of slider value arrangement. `SweepDirection` property contains the following values.

* Clockwise
* Counterclockwise

{% tabs %}

{% highlight C# %}

            // For clockwise direction
            this.radialSlider1.SweepDirection = SweepDirection.Clockwise;
            // For anti-clockwise direction
            this.radialSlider1.SweepDirection = SweepDirection.Counterclockwise;

{% endhighlight %}


{% highlight VB %}

             Me.radialSlider1.SweepDirection = SweepDirection.Clockwise
             Me.radialSlider1.SweepDirection = SweepDirection.Counterclockwise

{% endhighlight %}

{% endtabs %}

![SweepDirection](Slider-value_images/Slider-Sweep-Direction.png)


