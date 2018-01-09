---
layout: post
title: Appearance | OlapGauge | wpf | Syncfusion
description: appearance
platform: wpf
control: OlapGauge
documentation: ug
---

# Appearance

## Gauge Radius

OlapGauge provides support to adjust its radius and it can be achieved by assigning a proper value to the `Radius` property of OlapGauge. The following code snippet illustrates about modifying the radius of OlapGauge.

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

![](Appearance_images/Appearance_img1.png)

A demo sample is available at the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Appearance\Customization\

## Built-In Frame Types

OlapGauge supports 4 kinds of built-in frames to provide effective rim styles. The `FrameType` property is used to set the frame type for OlapGauge. The following are the frame types supported by OlapGauge:

* CircularCenterGradient

![](Appearance_images/Appearance_img2.png)

* CircularWithDarkOuterFrames

![](Appearance_images/Appearance_img3.png)

* FullCircle

![](Appearance_images/Appearance_img4.png)

* HalfCircle

![](Appearance_images/Appearance_img5.png)

The following code snippet illustrates about how to set frame type for OlapGauge.

{% tabs %}

{% highlight c# %}

this.OlapGauge1.FrameType = GaugeFrameType.CircularWithInnerLeftGradient;

{% endhighlight %}

{% highlight vb %}

Me.OlapGauge1.FrameType = GaugeFrameType.CircularWithInnerLeftGradient

{% endhighlight %}

{% endtabs %}

A demo sample is available at the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Appearance\Customization\

## Skins

Built-in-skins allow you to theme and style the look and feel of the OlapGauge control in various rich color schemes. You can use Skin Manager framework to apply a wide range of skins to the OlapGauge control. These skins have been designed to suit the needs of wide range of audience.

**Types of Skins:**

* Metro- This skin is similar to the Windows 8 Metro style.

![](Appearance_images/Appearance_img6.png)

* Blend- This skin is similar to the Microsoft Blend skin.

![](Appearance_images/Appearance_img7.png)

* Office2010Black- This skin is similar to the Microsoft Office2010Black skin.

![](Appearance_images/Appearance_img8.png)

* Office2010Blue- This skin is similar to the Microsoft Office2010Blue skin.

![](Appearance_images/Appearance_img9.png)

* Office2010Silver- This skin is similar to the Microsoft Office2010Silver skin.

![](Appearance_images/Appearance_img10.png)

* Office2013LightGray- This skin is similar to the Microsoft Office2013LightGray skin.

![](Appearance_images/Appearance_img11.png)

* Office2013DarkGray- This skin is similar to the Microsoft Office2013DarkGray skin.

![](Appearance_images/Appearance_img12.png)

* Office2013White- This skin is similar to the Microsoft Office2013White skin.

![](Appearance_images/Appearance_img13.png)

* VisualStudio2013- This skin is similar to the VisualStudio2013 skin.

![](Appearance_images/Appearance_img14.png)

In order to apply skin to OlapGauge, **SkinStorage.VisualStyle** property is used. The following code snippet shows how to set visual style for the control.

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

A demo sample is available at the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Appearance\Visual Styles\