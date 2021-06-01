---
layout: post
title: Palette in WPF Olap Chart control | Syncfusion
description: Learn about Palette support in Syncfusion Essential Studio WPF Olap Chart control, its elements and more details.
platform: wpf
control: OLAP Chart
 documentation: ug
---

# Palette in WPF Olap Chart

The chart palette is a pre-defined collection of a set of colors that can be applied to a chart series. The OLAP chart supports 23 chart palettes, which is used to provide rich look for your business applications.

The following are the available palettes in the OLAP chart control:

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

The following code sample shows how to apply a palette to the OLAP chart.

{% tabs %}

{% highlight c# %}
 
this.olapChart.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "EarthTone");

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "EarthTone"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

The following image shows before and after applying the *EarthTone* palette.

![Palette_img1](Palette_images/Palette_img1.png)

## Custom palette

Custom palettes can be applied to the OLAP chart by setting the _“Interior”_ property with custom brush to each series in the OLAP chart.

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Customization\Series Customization Demo

## Excel-like palette

Excel-like palettes are used to display the OLAP chart in business applications.

The following are the available types of Excel-like palettes:

**GrayScale, BlueScale**

![Palette_img2](Palette_images/Palette_img2.png)

**MaroonRed, GreenScale**

![Palette_img3](Palette_images/Palette_img3.png)

**MixedViolet, CoolBlueScale**

![Palette_img4](Palette_images/Palette_img4.png)

**ChocolateOrange, MixedFantasy**

![Palette_img5](Palette_images/Palette_img5.png)

The following code sample shows how to apply Excel-like palettes.

### Grayscale

{% tabs %}

{% highlight c# %}
 
this.olapChart.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "Grayscale");

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "Grayscale"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

### BlueScale

{% tabs %}

{% highlight c# %}
 
this.olapChart.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "BlueScale");

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "BlueScale"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}
 
{% endtabs %}

### MaroonRed

{% tabs %}

{% highlight c# %}
 
this.olapChart.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "MaroonRed");

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "MaroonRed"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

### GreenScale

{% tabs %}

{% highlight c# %}
 
this.olapChart.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "GreenScale");

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "GreenScale"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

### MixedViolet

{% tabs %}

{% highlight c# %}
 
this.olapChart.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "MixedViolet");

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "MixedViolet"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

### CoolBlueScale

{% tabs %}

{% highlight c# %}
 
this.olapChart.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "CoolBlueScale");

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "CoolBlueScale"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}
 
### ChocolateOrange

{% tabs %}

{% highlight c# %}
 
this.olapChart.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "ChocolateOrange");

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "ChocolateOrange"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}

### MixedFantasy

{% tabs %}

{% highlight c# %}
 
this.olapChart.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "MixedFantasy");

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "MixedFantasy"), Syncfusion.Windows.Chart.ChartColorPalette)

{% endhighlight %}

{% endtabs %}
