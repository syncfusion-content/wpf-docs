---
layout: post
title: Appearance | AutoComplete | wpf | Syncfusion
description: appearance
platform: wpf
control: AutoComplete
documentation: ug
---

# Appearance

The Appearance of the AutoComplete control can be changed using the VisualStyle property. The following styles are supported by AutoComplete control.

* Blend
* Office2003
* Office2007Blue
* Office2007Black
* Office2007Silver
* ShinyBlue
* ShinyRed
* SyncOrange
* VS2010
* Metro
* Transparent 

The following code example illustrates how different visual styles can be applied to the control.

Refer how to apply visual styles using SkingManger in below link.[SkinManger](https://help.syncfusion.com/wpf/skinmanager/overview)

{% tabs %}
{% highlight xaml %}

<syncfusion:AutoComplete Height="25" Width="200" syncfusion:SkinStorage.VisualStyle="Office2007Blue"/>

{% endhighlight %}

{% highlight c# %}

SkinStorage.SetVisualStyle(autoComplete, "Office2007Blue");

{% endhighlight %}
{% endtabs %}

![](Appearance_images/Appearance_img1.png)

Windows7
{:.caption}

![](Appearance_images/Appearance_img2.png)

Blend
{:.caption}

![](Appearance_images/Appearance_img3.png)

Office2007Blue
{:.caption}

![](Appearance_images/Appearance_img4.png)

Office2007Black
{:.caption}

![](Appearance_images/Appearance_img5.png)

Office2007Silver
{:.caption}

![](Appearance_images/Appearance_img6.png)

Office2003
{:.caption}

![](Appearance_images/Appearance_img7.png)

ShinyRed
{:.caption}

![](Appearance_images/Appearance_img8.png)

ShinyBlue
{:.caption}

![](Appearance_images/Appearance_img9.png)

SyncOrange
{:.caption}

![](Appearance_images/Appearance_img10.png)

Metro
{:.caption}

![](Appearance_images/Appearance_img11.png)

Transparent
{:.caption}
