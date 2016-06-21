---
layout: post
title: Palette| OlapChart | Wpf | Syncfusion
description: Palette
platform: wpf
control: OlapChart
documentation: ug
---

# Palette

Chart Palette is a pre-defined collection of a set of colors that can be applied to a chart series. OlapChart comes with a support of 23 chart palette, which can be used to provide a rich look for your business applications.

The available palettes in the OlapChart control are as follows:      

* Default
* DefaultAlpha
* EarthTone
* Analog
* Colorful
* Nature
* Pastel
* Triad
* WarmCold
* Grayscale
* Office2007Blue
* Office2007Black 
* Office2007Silver
* Gradient
* Grayscale
* BlueScale
* MaroonRed
* GreenScale
* MixedViolet
* CoolBlueScale
* ChocolateOrange
* MixedFantasy
* Custom

The following code sample shows how to apply a palette to an OlapChart:

{% tabs %}

{% highlight c# %}
 
	this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "EarthTone");

{% endhighlight %}

{% highlight vbnet %}
  
	Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "EarthTone"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

The following image shows before and after applying the *EarthTone* palette:

![](Palette_images/Palette_img1.png)

## Custom Palette

Custom palettes can be applied to an OlapChart by setting the _“Interior”_ property with the custom brush to each series in the OlapChart.

A sample demo is available at the following link:

[system drive]:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Customization\Series Customization Demo

## Excel-like Palette

Excel-like palettes are very useful in displaying the OlapChart in business applications. 

The following type of excel like palettes are available:

**GrayScale, BlueScale**

![](Palette_images/Palette_img2.png)

**MaroonRed, GreenScale**

![](Palette_images/Palette_img3.png)

**MixedViolet, CoolBlueScale**

![](Palette_images/Palette_img4.png)

**ChocolateOrange, MixedFantasy**

![](Palette_images/Palette_img5.png)

The following code sample show how you can apply excel like palettes.

### Grayscale

{% tabs %}

{% highlight c# %}
 
	this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "Grayscale");

{% endhighlight %}

{% highlight vbnet %}
  
	Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "Grayscale"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

### BlueScale

{% tabs %}

{% highlight c# %}
 
	this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "BlueScale");

{% endhighlight %}

{% highlight vbnet %}
  
	Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "BlueScale"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}
 
{% endtabs %}

### MaroonRed

{% tabs %}

{% highlight c# %}
 
	this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "MaroonRed");

{% endhighlight %}

{% highlight vbnet %}
  
	Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "MaroonRed"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

### GreenScale

{% tabs %}

{% highlight c# %}
 
	this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "GreenScale");

{% endhighlight %}

{% highlight vbnet %}
  
	Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "GreenScale"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

### MixedViolet

{% tabs %}

{% highlight c# %}
 
	this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "MixedViolet");

{% endhighlight %}

{% highlight vbnet %}
  
	Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "MixedViolet"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

### CoolBlueScale

{% tabs %}

{% highlight c# %}
 
	this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "CoolBlueScale");

{% endhighlight %}

{% highlight vbnet %}
  
	Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "CoolBlueScale"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}
 
### ChocolateOrange

{% tabs %}

{% highlight c# %}
 
	this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "ChocolateOrange");

{% endhighlight %}

{% highlight vbnet %}
  
	Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "ChocolateOrange"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

### MixedFantasy

{% tabs %}

{% highlight c# %}
 
	this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "MixedFantasy");

{% endhighlight %}

{% highlight vbnet %}
  
	Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "MixedFantasy"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}