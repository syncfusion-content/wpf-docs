---
layout: post
title: Digital Characters | SfDigitalGauge  | wpf | Syncfusion
description: digital characters
platform: wpf
control: SfDigitalGauge
documentation: ug
---

# Digital Characters

The Digital Characters in the Digital Gauge can be viewed in different types of segments. The digital characters are set to the Digital Gauge by using the Value property of type string.

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

### Screenshot:

![](Digital-Characters_images/Digital-Characters_img1.png)

## 7-Segments

The digital characters set with the value property of the Digital Gauge are displayed by default 7-segments. Rather than using the alphabets, these are mainly used to display numbers. The type of segments can be set by using the CharacterType property.

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

### Screenshot:

![](Digital-Characters_images/Digital-Characters_img2.png)

## 14-Segments

The digital characters set with the value property of the Digital Gauge are displayed by 14 segments. It is used to display both alphabets and numbers. 

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


### Screenshot:

![](Digital-Characters_images/Digital-Characters_img3.png)

## 16-Segments

The digital characters set with the value property of the digital gauge are displayed by 16 segments. It is used to display both alphabets and numbers. 

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


### Screenshot:

![](Digital-Characters_images/Digital-Characters_img4.png)

## 8*8 Dot Matrix Segments

The digital characters set with the value property of the Digital Gauge are displayed by eight cross eight dot matrix segments. It is used to display special characters along with the alphabets and numbers. 

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

### Screenshot:

![](Digital-Characters_images/Digital-Characters_img5.png)
