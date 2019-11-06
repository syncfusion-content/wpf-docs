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
* Office2010Black
* Office2010Blue
* Office2010Silver
* Office2013
* Office2003
* VS2010
* Transparent

In the below code example, Metro theme is applied to the ColorPickerPalette control. 

{% tabs %}

{% highlight xaml %}

<syncfusion:ColorPickerPalette x:Name="colorPickerPalette" Color="Orange" syncfusion:SkinStorage.VisualStyle="Metro"  ThemePanelVisibility="Visible" Width="200" Height="50”/> 

{% endhighlight %}

{% highlight C# %}

SkinStorage.SetVisualStyle(colorPickerPalette, "Metro"); 

{% endhighlight %}

{% highlight VB %}

SkinStorage.SetVisualStyle(colorPickerPalette, "Metro")

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

Office2010Blue

![](Appearance_images/Appearance_img8.png)

Office2010Black

![](Appearance_images/Appearance_img9.png)

Office2010Silver

![](Appearance_images/Appearance_img10.png)

Office2013

![](Appearance_images/Appearance_img11.png)

## MouseOverBackGround Color of ColorPickerPalette

You can change the background color of the ColorPickerPalette at mouse over, based on the brush color set in the MouseOverBackground property.

{% tabs %}

{% highlight xaml %}

<syncfusion:ColorPickerPalette  x:Name="ColorPickerPalette1" MouseOverBackground="Green">       
</syncfusion:ColorPickerPalette>

{% endhighlight %}

{% highlight C# %}

ColorPickerPalette ColorPickerPalette1 = new ColorPickerPalette();
ColorPickerPalette1.MouseOverBackground = Brushes.Green;

{% endhighlight %}

{% highlight VB %}

ColorPickerPalette ColorPickerPalette1 = new ColorPickerPalette()
ColorPickerPalette1.MouseOverBackground = Brushes.Green

{% endhighlight %}

{% endtabs %}

### Properties


<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
MouseOverBackgroundBrush </td><td>
Gets or sets the MouseOver BackgroundBrush value of the ColorPickerPalette.</td><td>
Brush </td><td>
N/A </td></tr>
</table>

