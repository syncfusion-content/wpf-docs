---
layout: post
title: UI-Settings
description: ui settings
platform: wpf
control: Digital Gauge 
documentation: ug
---

# UI Settings

There are some other UI modifications that can be achieved in the Digital Gauge. They are:

* Character Spacing
* Segment Thickness
* RTL (Right to Left) support
* Character Stroke
* Dimmed Brush stroke
* Dimmed Brush opacity

## Character Spacing

The distance between the characters can be set by using the CharacterSpacing property.


{% highlight xml %}

[XAML]

           <syncfusion:SfDigitalGauge  Value="SYNCFUSION" CharacterSpacing="50"/>
{% endhighlight %}

{% highlight C# %}

[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = " SYNCFUSION";

            digitalgauge.CharacterSpacing = 50;

            this.Grid.Children.Add(digitalgauge);      
{% endhighlight %}


### Screenshot:



![](UI-Settings_images/UI-Settings_img1.png)




## Character Stroke

The Stroke of the character can be changed by using CharacterStroke property.



{% highlight xml %}

[XAML]

       <syncfusion:SfDigitalGauge  Value="SYNCFUSION"   CharacterType="SegmentFourteen" CharacterStroke="Yellow" />
{% endhighlight %}

{% highlight C# %}

[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = " SYNCFUSION";

            digitalgauge.CharacterStroke = new SolidColorBrush(Colors.Yellow);

            digitalgauge.CharacterType = CharacterType.SegmentFourteen;

            this.Grid.Children.Add(digitalgauge);

{% endhighlight %}

### Screenshot:



![](UI-Settings_images/UI-Settings_img2.png)





## Segment Thickness

By using SegmentThickness property, you can adjust the thickness of the segment.


{% highlight xml %}

[XAML]

      <syncfusion:SfDigitalGauge  Value="SYNCFUSION"  CharacterType="SegmentFourteen  SegmentThickness="5"/>
{% endhighlight %}

{% highlight C# %}


[C#]





            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = " SYNCFUSION";

            digitalgauge.SegmentThickness = 5;

            digitalgauge.CharacterType = CharacterType.SegmentFourteen;



            this.Grid.Children.Add(digitalgauge);

{% endhighlight %}



### Screenshot:



![](UI-Settings_images/UI-Settings_img3.png)





## RTL (Right to Left) support

The Characters are aligned by using EnableRTLFormat property. The default value of EnableRTLFormat is False.


{% highlight xml %}

[XAML]

      <syncfusion:SfDigitalGauge  Value="SYNCFUSION"  CharacterType="SegmentFourteen"   EnableRTLFormat="True" />
{% endhighlight %}

{% highlight C# %}

[C#]



            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = " SYNCFUSION";

            digitalgauge.EnableRTLFormat= true;

            digitalgauge.CharacterType = CharacterType.SegmentFourteen;

            this.Grid.Children.Add(digitalgauge);
{% endhighlight %}




### Screenshot:



![](UI-Settings_images/UI-Settings_img4.png)





## Dimmed Brush stroke

DimmedBrush property is used to apply brushes to the dimmed segment. This property is used to suit the background of the Digital gauge.



{% highlight xml %}
[XAML]

      <syncfusion:SfDigitalGauge  Value="SYNCFUSION" CharacterType="SegmentFourteen"  DimmedBrush="White" />

{% endhighlight %}

{% highlight C# %}

[C#]



            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = " SYNCFUSION";

            digitalgauge.DimmedBrush = new SolidColorBrush(Colors.White);

            digitalgauge.CharacterType = CharacterType.SegmentFourteen;

            this.Grid.Children.Add(digitalgauge);

{% endhighlight %}



### Screenshot:



![](UI-Settings_images/UI-Settings_img5.png)





## Dimmed Brush opacity

DimmedBrushOpacity property is used to set the opacity of the brushes to the dimmed segment.



{% highlight xml %}

[XAML]

      <syncfusion:SfDigitalGauge  Value="SYNCFUSION" DimmedBrush="White"  DimmedBrushOpacity="20" CharacterType="SegmentFourteen" />
{% endhighlight %}

{% highlight C# %}
[C#]

            SfDigitalGauge digitalgauge = new SfDigitalGauge();

            digitalgauge.Value = " SYNCFUSION";

            digitalgauge.DimmedBrush = new SolidColorBrush(Colors.White);

            digitalgauge.CharacterType = CharacterType.SegmentFourteen;

            digitalgauge.DimmedBrushOpacity = 20;

            this.Grid.Children.Add(digitalgauge);

{% endhighlight %}




### Screenshot:



![](UI-Settings_images/UI-Settings_img6.png)









