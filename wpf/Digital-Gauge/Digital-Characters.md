---
layout: post
title: Digital Characters in WPF Digital Gauge control | Syncfusion
description: Learn here all about Digital Characters support in Syncfusion WPF Digital Gauge (SfDigitalGauge) control and more.
platform: wpf
control: SfDigitalGauge
documentation: ug
---

# Digital Characters in WPF Digital Gauge (SfDigitalGauge)

The digital characters in the digital gauge can be viewed in different types of segments. These digital characters are set to the digital gauge through the [`Value`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_Value) property of type string. The type of segment used to display the characters is determined by the [`CharacterType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) property.

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

By default, the digital characters set as the [`Value`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_Value) property are displayed using 7-segments. These are mainly used to display numbers rather than letters. The type of segments can be set by the [`CharacterType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) property.

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

The digital characters set as the [`Value`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_Value) property can be displayed using 14 segments. This type of character is used to display both alphabets and numbers. Set the [`CharacterType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) property to `SegmentFourteen` to display characters in this format.

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

The digital characters set as the [`Value`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_Value) property can be displayed using 16 segments. Like 14-segment characters, this type is also used to display both alphabets and numbers, with finer segment detail. Set the [`CharacterType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) property to `SegmentSixteen` to display characters in this format.

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

## 8×8 Dot Matrix Segments

The digital characters set as the [`Value`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_Value) property can be displayed using 8×8 dot matrix segments. This type of character is used to display special characters along with alphabets and numbers. Set the [`CharacterType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfDigitalGauge.html#Syncfusion_UI_Xaml_Gauges_SfDigitalGauge_CharacterType) property to `EightCrossEightDotMatrix` to display characters in this format.

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
{% endtabs %}

![Digital Gauge with EightCrossEightDotMatrix CharacterType](Digital-Characters_images/Digital-Characters_img5.png)

