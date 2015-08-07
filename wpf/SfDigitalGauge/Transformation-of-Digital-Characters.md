---
layout: post
title: Transformation-of-Digital-Characters
description: transformation of digital characters
platform: wpf
control: Digital Gauge 
documentation: ug
---

# Transformation of Digital Characters

The digital characters in the Digital Gauge can be transformed by setting certain properties. Two kinds of transformations are done by using this property. They are:

* Scaling
* Skewing

## Scaling

The value of the digital characters is scaled by changing its height and width. It is achieved by setting the CharacterHeight and CharacterWidth property of Digital Gauge.

### CharacterHeight


{% highlight xml %}

[XAML]



<syncfusion:SfDigitalGauge Value="SYNCFUSION"  CharacterHeight="70"

                                   CharacterType="SegmentFourteen" />
{% endhighlight %}

{% highlight C# %}

[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = "SYNCFUSION";

            digitalgauge.CharacterHeight = 70;

            digitalgauge.CharacterType = CharacterType.SegmentFourteen;

            this.Grid.Children.Add(digitalgauge);
{% endhighlight %}




#### Screenshot:



![](Transformation-of-Digital-Characters_images/Transformation-of-Digital-Characters_img1.png)



### CharacterWidth



{% highlight xml %}

[XAML]

<syncfusion:SfDigitalGauge  Value="SYNCFUSION"  CharacterWidth="60"

                                   CharacterType="SegmentFourteen" />
{% endhighlight %}

{% highlight C# %}


[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = "SYNCFUSION";

            digitalgauge.CharacterWidth = 60;

            digitalgauge.CharacterType = CharacterType.SegmentFourteen;

            this.Grid.Children.Add(digitalgauge);
{% endhighlight %}


#### Screenshot:



{{ '![](Transformation-of-Digital-Characters_images/Transformation-of-Digital-Characters_img2.png)' | markdownify }}





## Skewing

The Digital Gauge also performs skew transformation for the digital characters. It can be done on both x-axis and y-axis by using SkewAngleX and SkewAngleY properties respectively.

### SkewAngleX


{% highlight xml %}

[XAML]

      <syncfusion:SfDigitalGauge  Value="SYNCFUSION"  SkewAngleX="35"

                                   CharacterType="SegmentFourteen" />
{% endhighlight %}


{% highlight C# %}

[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = "SYNCFUSION";

            digitalgauge.SkewAngleX = 35;

            digitalgauge.CharacterType = CharacterType.SegmentFourteen;

            this.Grid.Children.Add(digitalgauge);
			
{% endhighlight %}



#### Screenshot:



![](Transformation-of-Digital-Characters_images/Transformation-of-Digital-Characters_img3.png)





### SkewAngleY



{% highlight xml %}

[XAML]

   <syncfusion:SfDigitalGauge  Value="SYNCFUSION"  SkewAngleY="30"

                                   CharacterType="SegmentFourteen" />   

{% endhighlight %}


{% highlight C# %}

[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = "SYNCFUSION";

            digitalgauge.SkewAngleY = 30;

            digitalgauge.CharacterType = CharacterType.SegmentFourteen;

            this.Grid.Children.Add(digitalgauge);
{% endhighlight %}


#### Screenshot:



![](Transformation-of-Digital-Characters_images/Transformation-of-Digital-Characters_img4.png)



