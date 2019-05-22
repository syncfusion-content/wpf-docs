---
layout: post
title: Pointers | Circular Gauge | WPF | Syncfusion
description: Pointers in WPF Circular Gauge are used to indicate values on the scale. The pointer values can be modified using the value property.
platform: wpf
control: SfCircularGauge
documentation: ug
---

# Pointers

Pointers are used to indicate values on the scale. Value of the pointer can be modified using the `Value` property.

## Pointer Type

There are three types of pointers. You can choose a pointer using the `PointerType` property. 

## Needle pointer

A needle pointer contains two parts, a needle and a pointer cap, that can be placed on a gauge to mark values. 

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="NeedlePointer"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

CircularPointer circularPointer = new CircularPointer();

circularPointer.PointerType = PointerType.NeedlePointer;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img1.png)

### NeedlePointerType

The appearance of the needle pointer can be customized using the `NeedlePointerType` property. The default value of this property is Rectangle.
The `NeedlePointerType` is an `enum` property that includes the following options:

1.	Rectangle

2.	Triangle

3.	Tapered

4.	Arrow

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="NeedlePointer" NeedlePointerType="Triangle"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

CircularPointer circularPointer = new CircularPointer();

circularPointer.PointerType = PointerType.NeedlePointer;

circularPointer.NeedlePointerType = NeedlePointerType.Triangle;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img2.png)

### Needle pointer customization

The length of a needle is controlled using the `NeedleLengthFactor` property. The minimum and maximum bounds of the `NeedleLengthFactor` property are 0 and 1. The needle’s UI is customized using the `NeedlePointerStroke` and `NeedlePointerStrokeThickness` properties. The size of the pointer cap can be modified by changing the `PointerCapDiameter` property, and color can be modified using the `PointerCapStroke` property.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="NeedlePointer" NeedlePointerType="Triangle" NeedlePointerStroke="DeepSkyBlue"     PointerCapDiameter="20" PointerCapStroke="DeepSkyBlue"
    NeedleLengthFactor="0.5" NeedlePointerStrokeThickness="10"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

CircularPointer circularPointer = new CircularPointer();

circularPointer.PointerType = PointerType.NeedlePointer;

circularPointer.NeedlePointerType = NeedlePointerType.Triangle;

circularPointer.NeedlePointerStroke = new SolidColorBrush(Colors.DeepSkyBlue);

circularPointer.NeedlePointerStrokeThickness =10;

circularPointer.NeedleLengthFactor = 0.5;

circularPointer.PointerCapDiameter = 20;

circularPointer.PointerCapStroke = new SolidColorBrush(Colors.DeepSkyBlue);

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img3.png)

### Setting visibility of needle pointer

The visibility of the needle pointer can be set using the `NeedlePointerVisibility` property.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

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

CircularPointer circularPointer = new CircularPointer();

circularPointer.NeedlePointerVisibility = Visibility.Hidden;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img4.png)

## Range pointer

The range pointer is an accenting line or shaded background range that can be placed on a gauge to mark values. 

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="RangePointer" Value="50" />

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

CircularPointer circularPointer = new CircularPointer();

circularPointer.PointerType = PointerType.RangePointer;

circularPointer.Value = 50;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img5.png)

### Range pointer customization

The range pointer’s UI is customized using the `RangePointerStroke` and `RangePointerStrokeThickness` properties.  

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="RangePointer" Value="50" RangePointerStroke="DarkCyan" RangePointerStrokeThickness="20"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

CircularPointer circularPointer = new CircularPointer();

circularPointer.PointerType = PointerType.RangePointer;

circularPointer.Value = 50;

circularPointer.RangePointerStroke = new SolidColorBrush(Colors.DarkCyan);

circularPointer.RangePointerStrokeThickness = 20;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img6.png)

### Setting visibility for range pointer

The `RangePointerVisibility` property is used to set the visibility of the range pointer.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer RangePointerVisibility="Hidden"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>
                    
    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

CircularPointer circularPointer = new CircularPointer();

circularPointer.RangePointerVisibility = Visibility.Hidden;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img7.png)

### Setting position for range pointer

The `RangePointer` can be placed inside or outside the scale by the following two ways:
1.	Using the `RangePointerPosition` property.

You can place the range pointer by selecting one of the options available in the `RangePointerPosition` property. They are:
1.	Inside (Default)

2.	Outside

3.	Cross

4.	Custom

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale RangePointerPosition="Outside">

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="RangePointer" RangePointerStroke="HotPink" Value="60"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

mainscale.RangePointerPosition = RangePointerPosition.Outside;

CircularPointer circularPointer = new CircularPointer();

circularPointer.PointerType = PointerType.RangePointer;

circularPointer.RangePointerStroke = new SolidColorBrush(Colors.HotPink);

circularPointer.Value = 60;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img8.png)

2.	Using the `RangePointerOffset` property. First, set the `RangePointerPosition` to custom, and then set the `RangePointerOffset` property.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale RangePointerPosition="Custom" RangePointerOffset="0.5">

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="RangePointer" RangePointerStroke="HotPink" Value="60"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

mainscale.RangePointerOffset = 0.5;

mainscale.RangePointerPosition = RangePointerPosition.Custom;

CircularPointer circularPointer = new CircularPointer();

circularPointer.PointerType = PointerType.RangePointer;

circularPointer.Value = 90;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img9.png)

## Symbol pointer

In symbol pointer, the value is pointed out using a symbol on the scale. The symbol is an enum property that provides symbol options for the symbol pointer, which contains several shapes such as rectangle, ellipse, and triangle.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale>

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="SymbolPointer"  Value="60"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

CircularPointer circularPointer = new CircularPointer();

circularPointer.PointerType = PointerType.SymbolPointer;

circularPointer.Value = 60;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img10.png)

### Symbol pointer customization

You can modify the stroke of the symbol by changing the `SymbolPointerStroke` property. The `SymbolPointerHeight` property is used to set the height of the symbol pointer. The value should be given as a double value. The `SymbolPointerWidth` property is used to set the width of the symbol pointer.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale>

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="SymbolPointer"  Value="60" SymbolPointerStroke="Red"
     SymbolPointerHeight="20" SymbolPointerWidth="20"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>
            
    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

CircularPointer circularPointer = new CircularPointer();

circularPointer.PointerType = PointerType.SymbolPointer;

circularPointer.Value = 60;

circularPointer.SymbolPointerStroke = new SolidColorBrush(Colors.Red);

circularPointer.SymbolPointerHeight = 20;

circularPointer.SymbolPointerWidth = 20;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img11.png)

### Setting visibility of symbol pointer

The visibility of the symbol pointer can be set using the `SymbolPointerVisibility` Property.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge >

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale>

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer SymbolPointerVisibility="Hidden"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

CircularPointer circularPointer = new CircularPointer();

circularPointer.SymbolPointerVisibility = Visibility.Hidden;

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img12.png)

### Setting multiple pointers

In addition to the default pointer, you can add n number of pointers to a scale using the `Pointer` property.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="NeedlePointer" NeedleLengthFactor="0.4" Value="60"
     NeedlePointerType="Tapered" PointerCapStroke="#39B2C6" />

    <gauge:CircularPointer PointerType="RangePointer"  Value="100"/>

    <gauge:CircularPointer PointerType="SymbolPointer"  Value="50" Symbol="Pentagon"
     SymbolPointerHeight="20" SymbolPointerWidth="20" SymbolPointerStroke="#39B2C6"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale mainscale = new CircularScale();

CircularPointer circularPointer = new CircularPointer();

circularPointer.PointerType = PointerType.NeedlePointer;

circularPointer.NeedleLengthFactor = 0.4;

circularPointer.Value = 60;

circularPointer.NeedlePointerType = NeedlePointerType.Tapered;

circularPointer.PointerCapStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x39, 0xb2, 0xc6));

mainscale.Pointers.Add(circularPointer);

CircularPointer circularPointer1 = new CircularPointer();

circularPointer1.PointerType = PointerType.RangePointer;

circularPointer1.Value = 100;

mainscale.Pointers.Add(circularPointer1);

CircularPointer circularPointer2 = new CircularPointer();

circularPointer2.PointerType = PointerType.SymbolPointer;

circularPointer2.Value = 50;

circularPointer2.Symbol = Symbol.Pentagon;

circularPointer2.SymbolPointerHeight = 20;

circularPointer2.SymbolPointerWidth = 20;

circularPointer2.SymbolPointerStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x39, 0xb2, 0xc6));

mainscale.Pointers.Add(circularPointer2);

mainscale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img13.png)

## Setting animation for pointer

The `EnableAnimation` property is a Boolean property that enables or disables the animation of the pointers in circular gauge.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale Radius="150" >

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer PointerType="NeedlePointer" NeedleLengthFactor="0.4" Value="60"
    NeedlePointerType="Triangle" PointerCapStroke="#39B2C6" PointerCapDiameter="20"/>

    <gauge:CircularPointer PointerType="RangePointer"  Value="100" RangePointerStroke="#39B2C6"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

            SfCircularGauge sfCircularGauge = new SfCircularGauge();

            CircularScale mainscale = new CircularScale();

            mainscale.Radius = 150;

            CircularPointer circularPointer = new CircularPointer();

            circularPointer.PointerType = PointerType.NeedlePointer;

            circularPointer.EnableAnimation = true;

            circularPointer.NeedleLengthFactor = 0.4;

            circularPointer.Value = 60;

            circularPointer.NeedlePointerType = NeedlePointerType.Triangle;

            circularPointer.PointerCapDiameter = 20;

            circularPointer.PointerCapStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x39, 0xb2, 0xc6));

            mainscale.Pointers.Add(circularPointer);

            CircularPointer circularPointer1 = new CircularPointer();

            circularPointer1.PointerType = PointerType.RangePointer;

            circularPointer1.RangePointerStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x39, 0xb2, 0xc6));

            circularPointer1.EnableAnimation = true;

            circularPointer1.Value = 100;

            mainscale.Pointers.Add(circularPointer1);

            mainscale.Pointers.Add(circularPointer);

            sfCircularGauge.Scales.Add(mainscale);

{% endhighlight %}

{% endtabs %}

![](Pointers_images/Pointers_img14.gif)