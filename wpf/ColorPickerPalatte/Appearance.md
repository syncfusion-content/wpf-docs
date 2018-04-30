---
layout: post
title: Appearance| ColorPickerPalette | Wpf | Syncfusion
description: appearance
platform: wpf
control: ColorPickerPalette
documentation: ug
---

# Appearance

The appearance of the ColorPickerPalette control can be customized by using the VisualStyle property. The following are the various built-in visual styles for ColorPickerPalette control.

* Metro
* Blend
* Office2007Blue
* Office2007Black
* Office2007Silver
* Office2003
* VS2010
* Transparent

In the below code example, Metro theme is applied to the ColorPickerPalette control. 

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette x:Name="colorPickerPalette" Color="Orange" syncfusion:SkinStorage.VisualStyle="Metro"  ThemePanelVisibility="Visible" Width="200" Height="50"/> 

{% endhighlight %}

{% highlight C# %}

SkinStorage.SetVisualStyle(colorPickerPalette, "Metro"); 

{% endhighlight %}
{% endtabs %}

Metro

![](Appearance_images/Appearance_img6.png)

Blend

![](Appearance_images/Appearance_img2.png)

Office2007Blue

![](Appearance_images/Appearance_img1.png)

Office2007Black

![](Appearance_images/Appearance_img4.png)

Office2007Silver

![](Appearance_images/Appearance_img5.png)

Office2003

![](Appearance_images/Appearance_img3.png)

Transparent

![](Appearance_images/Appearance_img7.png)
