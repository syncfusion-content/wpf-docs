---

layout: post
title: Animation in WPF Sunburst Chart | Syncfusion®
description: Animation in the WPF Sunburst Chart provides smooth visual transitions for rendering hierarchical data and interactive updates.
platform: wpf 
control: SfSunburstChart 
documentation: ug

---

# Animation in WPF Sunburst Chart

The Sunburst Chart allows you to animate the chart segments. You can enable animation using the [`EnableAnimation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SfSunburstChart.html#Syncfusion_UI_Xaml_SunburstChart_SfSunburstChart_EnableAnimation) property. You can also set the duration for animation by using the [`AnimationDuration`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SfSunburstChart.html#Syncfusion_UI_Xaml_SunburstChart_SfSunburstChart_AnimationDuration) property.

{% tabs %}

{% highlight xaml %}

<sunburst:SfSunburstChart 
    EnableAnimation="True" 
    AnimationDuration="5000">
</sunburst:SfSunburstChart>

{% endhighlight %}

{% highlight c# %}

sunburstChart.EnableAnimation = true;
sunburstChart.AnimationDuration = 5000;

{% endhighlight %}

{% endtabs %}

## Animation Types

The Sunburst Chart provides options to animate the chart segments in different ways using the [`AnimationType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SfSunburstChart.html#Syncfusion_UI_Xaml_SunburstChart_SfSunburstChart_AnimationType) property.

FadeIn – It gradually changes the opacity of the chart segment.

Rotation – During an animation, the control rotates from 0 to 360 degrees.

### FadeIn

The following example shows how to enable the FadeIn animation:

{% tabs %}

{% highlight xaml %}

<sunburst:SfSunburstChart 
    EnableAnimation="True"
    AnimationType="FadeIn">
</sunburst:SfSunburstChart>

{% endhighlight %}

{% highlight c# %}

sunburstChart.EnableAnimation = true;
sunburstChart.AnimationType = AnimationType.FadeIn;

{% endhighlight %}

{% endtabs %}

![Animation_img1](Animation_images/Animation_img1.gif)

### Rotation

The following example shows how to enable the Rotation animation:

{% tabs %}

{% highlight xaml %}

<sunburst:SfSunburstChart 
    EnableAnimation="True"
    AnimationType="Rotation">
</sunburst:SfSunburstChart>

{% endhighlight %}

{% highlight c# %}

sunburstChart.EnableAnimation = true;
sunburstChart.AnimationType = AnimationType.Rotation;

{% endhighlight %}

{% endtabs %}

![Animation_img2](Animation_images/Animation_img2.gif)

