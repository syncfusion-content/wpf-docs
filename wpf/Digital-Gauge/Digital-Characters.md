---
layout: post
title: Digital Characters | SfDigitalGauge | Wpf | Syncfusion
description:  This section describes Digital Characters support in WPF SfDigitalGauge control with CharacterType property.
platform: wpf
control: SfDigitalGauge
documentation: ug
---

# Digital Characters in Digital Gauge (SfDigitalGauge)

The digital characters in the digital gauge can be viewed in different types of segments. These digital characters are set to the digital gauge through the [`Value`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_Value) property of type string.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="GAUGE" />    

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digitalgauge = new SfDigitalGauge();
    digitalgauge.Value = "GAUGE";
    this.Grid.Children.Add(digitalgauge);

{% endhighlight %}
{% endtabs %}

![Digital Gauge with Value](Digital-Characters_images/Digital-Characters_img1.png)


## 7-Segments

The digital characters which are set as the value property of the digital gauge are displayed by default 7-segments. Rather than using the alphabets, these are mainly used to display numbers. The type of segments can be set by the [`CharacterType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) property.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="12345"  CharacterType="SegmentSeven" />

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digitalgauge = new SfDigitalGauge();
    digitalgauge.Value = "12345";
    digitalgauge.CharacterType = CharacterType.SegmentSeven;
    this.Grid.Children.Add(digitalgauge);

{% endhighlight %}
{% endtabs %}

![Digital Gauge with SegmentSeven CharacterType](Digital-Characters_images/Digital-Characters_img2.png)

## 14-Segments

The digital characters which are set as the value property of the digital gauge are displayed by 14 segments. These type of characters are used to display both alphabets and numbers. 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="SYNCFUSION" CharacterType="SegmentFourteen" />

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digitalgauge = new SfDigitalGauge();
    digitalgauge.Value = "SYNCFUSION";
    digitalgauge.CharacterType = CharacterType.SegmentFourteen;
    this.Grid.Children.Add(digitalgauge);

{% endhighlight %}
{% endtabs %}

![Digital Gauge with SegmentFourteen CharacterType](Digital-Characters_images/Digital-Characters_img3.png)

## 16-Segments

The digital characters which are set as the value property of the digital gauge are displayed by 16 segments. These type of characters are also used to display both alphabets and numbers. 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="SYNCFUSION" CharacterType="SegmentSixteen" />

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digitalgauge = new SfDigitalGauge();
    digitalgauge.Value = "SYNCFUSION";
    digitalgauge.CharacterType = CharacterType.SegmentSixteen;
    this.Grid.Children.Add(digitalgauge);

{% endhighlight %}
{% endtabs %}

![Digital Gauge with SegmentSixteen CharacterType](Digital-Characters_images/Digital-Characters_img4.png)

## 8*8 Dot Matrix Segments

The digital characters which are set as the value property of the digital gauge are displayed by eight cross eight dot matrix segments. These type of characters are used to display special characters along with the alphabets and numbers. 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfDigitalGauge Value="SYNCFUSION" CharacterType="EightCrossEightDotMatrix" />

{% endhighlight %}

{% highlight c# %}

    SfDigitalGauge digitalgauge = new SfDigitalGauge();
    digitalgauge.Value = "SYNCFUSION";
    digitalgauge.CharacterType = CharacterType.EightCrossEightDotMatrix;
    this.Grid.Children.Add(digitalgauge);

{% endhighlight %}
{% endtabs%}

![Digital Gauge with EightCrossEightDotMatrix CharacterType](Digital-Characters_images/Digital-Characters_img5.png)

