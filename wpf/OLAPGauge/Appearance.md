---
layout: post
title: Customize the appearance of OLAP Gauge
description: Customize the radius, frame type, and skin of OLAP Gauge
platform: wpf
control: OLAP Gauge
documentation: ug
---

# Customize the appearance of OLAP Gauge

## Gauge radius

The OLAP gauge supports adjusting its radius and this can be achieved by assigning a proper value to the `Radius` property of OLAP gauge. The following code snippet illustrates about modifying the radius of OLAP gauge.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge Name="olapGauge1" Radius="120"/>

{% endhighlight %}

{% highlight c# %}

this.OlapGauge1.Radius = 100;

{% endhighlight %}

{% highlight vb %}

Me.OlapGauge1.Radius = 100

{% endhighlight %}

{% endtabs %}

![WPF OLAPGauge displays radius value](Appearance_images/Appearance_img1.png)

A demo sample is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Appearance\Customization\

## Built-in frame types

The OLAP gauge supports four types of built-in frames to provide effective rim styles. The `FrameType` property is used to set the frame type for the OLAP gauge. The following are the frame types supported by the OLAP gauge:

* CircularCenterGradient

![WPF OLAPGauge displays circular center gradient frame type](Appearance_images/Appearance_img2.png)

* CircularWithDarkOuterFrames

![WPF OLAPGauge displays circular with dark outer frame type](Appearance_images/Appearance_img3.png)

* FullCircle

![WPF OLAPGauge displays full circle of gauge](Appearance_images/Appearance_img4.png)

* HalfCircle

![WPF OLAPGauge displays half circle of gauge](Appearance_images/Appearance_img5.png)

The following code snippet illustrates about how to set frame type for the OLAP gauge.

{% tabs %}

{% highlight c# %}

this.OlapGauge1.FrameType = GaugeFrameType.CircularWithInnerLeftGradient;

{% endhighlight %}

{% highlight vb %}

Me.OlapGauge1.FrameType = GaugeFrameType.CircularWithInnerLeftGradient

{% endhighlight %}

{% endtabs %}

A demo sample is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Appearance\Customization\

## Skins

Built-in-skins allow you to customize the theme and style to improve the look and feel of the OLAP gauge control in various rich color schemes. You can use the skin manager framework to apply a wide range of skins to the OLAP gauge control. These skins have been designed to suit the needs of wide range of audience.

**Types of skins:**

* Metro: This skin is similar to the Windows 8 Metro style.

![WPF OLAPGauge displays applied Metro theme to the contol](Appearance_images/Appearance_img6.png)

* Blend: This skin is similar to the Microsoft Blend skin.

![WPF OLAPGauge displays applied Blend theme to the control](Appearance_images/Appearance_img7.png)

* Office2010Black: This skin is similar to the Microsoft Office2010Black skin.

![WPF OLAPGauge displays applied Office2010Black theme to the control](Appearance_images/Appearance_img8.png)

* Office2010Blue: This skin is similar to the Microsoft Office2010Blue skin.

![WPF OLAPGauge displays applied Office2010Blue theme to the control](Appearance_images/Appearance_img9.png)

* Office2010Silver: This skin is similar to the Microsoft Office2010Silver skin.

![WPF OLAPGauge displays applied Office2010Silver theme to the control](Appearance_images/Appearance_img10.png)

* Office2013LightGray: This skin is similar to the Microsoft Office2013LightGray skin.

![WPF OLAPGauge displays applied Office2013LightGray theme to the control](Appearance_images/Appearance_img11.png)

* Office2013DarkGray: This skin is similar to the Microsoft Office2013DarkGray skin.

![WPF OLAPGauge displays applied Office2013DarkGray theme to the control](Appearance_images/Appearance_img12.png)

* Office2013White: This skin is similar to the Microsoft Office2013White skin.

![WPF OLAPGauge displays applied Office2013White theme to the control](Appearance_images/Appearance_img13.png)

* VisualStudio2013: This skin is similar to the VisualStudio2013 skin.

![WPF OLAPGauge displays applied VisualStudio2013 theme to the control](Appearance_images/Appearance_img14.png)

To apply a skin to the OLAP gauge, use the `SkinStorage.VisualStyle` property. The following code snippet shows how to set the visual style for the control.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge Name="olapGauge1" sfshared:SkinStorage.VisualStyle="Metro"/>

{% endhighlight %}

{% highlight c# %}

SfSkinManager.SetVisualStyle(olapGauge1, Syncfusion.SfSkinManager.VisualStyles.Metro);

{% endhighlight %}

{% highlight vb %}

SfSkinManager.SetVisualStyle(olapGauge1, Syncfusion.SfSkinManager.VisualStyles.Metro);

{% endhighlight %}

{% endtabs %}

A demo sample is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Appearance\Visual Styles\