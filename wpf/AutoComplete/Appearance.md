---
layout: post
title: Appearance
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


{% highlight xml %}


<syncfusion:AutoComplete Height="25" Width="200" syncfusion:SkinStorage.VisualStyle="Office2007Blue"/>
{% endhighlight %}

{% highlight c# %}


SkinStorage.SetVisualStyle(autoComplete, "Office2007Blue");

{% endhighlight %}

![](Appearance_images/Appearance_img1.png)

_Windows7_

![](Appearance_images/Appearance_img2.png)

_Blend_


![](Appearance_images/Appearance_img3.png)

_Office2007Blue_

![](Appearance_images/Appearance_img4.png)

_Office2007Black_

![](Appearance_images/Appearance_img5.png)

_Office2007Silver_

![](Appearance_images/Appearance_img6.png)

_Office2003_

![](Appearance_images/Appearance_img7.png)

_ShinyRed_

![](Appearance_images/Appearance_img8.png)

_ShinyBlue_



![](Appearance_images/Appearance_img9.png)

_SyncOrange_



![](Appearance_images/Appearance_img10.png)

_Metro_



![](Appearance_images/Appearance_img11.png)

_Transparent_

