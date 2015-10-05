---
layout: post
title: Chart Palette| OLAP Chart | Wpf | Syncfusion
description: Chart Palette
platform: wpf
control: OLAP Chart
documentation: ug
---

# Chart Palette

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
* Palette1
* Palette2
* Palette3
* Palette4
* Palette5
* Palette6
* Palette7
* Palette8 
* Custom

## How to apply a built-in chart palette to an OlapChart?


The palettes are pre-defined styles, which can be applied to the Series of an OlapChart.

The following code snippet shows how to apply a palette to an OlapChart:


 {% highlight c# %}
 
    



this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "EarthTone");

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "EarthTone"), Syncfusion.Windows.Chart.ChartColorPalette)

 {% endhighlight %}


The following image shows before and after applying the EarthTone palette:

![](Core-Features_images/Core-Features_img33.png)


## How to create and apply a custom palette to an OlapChart?

Custom palettes can be applied to an OlapChart by setting the _“Interior”_ property with the custom brush to each series in the OlapChart.

A sample, which demonstrates all the series customization, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Customization\Series Customization Demo



## How to apply excel like chart palette for an OlapChart control?

Excel like palettes are very useful in displaying the OlapChart in business applications. 

The following type of excel like palettes are available:

![](Core-Features_images/Core-Features_img34.png)


![](Core-Features_images/Core-Features_img35.png)


The following code snippets show how you can apply excel like palettes. It is similar to the topic “How to apply a built-in chart palette to an OlapChart”.

## Palette1


 {% highlight c# %}
 
   



this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "Palette1");

 {% endhighlight %}




 {% highlight vbnet %}
  
    



Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "Palette1"), Syncfusion.Windows.Chart.ChartColorPalette)

 {% endhighlight %}


## Palette2


 {% highlight c# %}
 
  



this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "Palette2");

 {% endhighlight %}




 {% highlight vbnet %}
  
  



Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "Palette2"), Syncfusion.Windows.Chart.ChartColorPalette)

 {% endhighlight %}


## Palette3


 {% highlight c# %}
 
    



this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "Palette3");

 {% endhighlight %}




 {% highlight vbnet %}
  
   




Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "Palette3"), Syncfusion.Windows.Chart.ChartColorPalette)

 {% endhighlight %}


## Palette4


 {% highlight c# %}
 
    



this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "Palette4");

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "Palette4"), Syncfusion.Windows.Chart.ChartColorPalette)

 {% endhighlight %}


## Palette5


 {% highlight c# %}
 
  



this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "Palette5");

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "Palette5"), Syncfusion.Windows.Chart.ChartColorPalette)

 {% endhighlight %}











## Palette6


 {% highlight c# %}
 
 



this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "Palette6");

 {% endhighlight %}




 {% highlight vbnet %}
  
   




Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "Palette6"), Syncfusion.Windows.Chart.ChartColorPalette)

 {% endhighlight %}



### Palette7


 {% highlight c# %}
 
  




this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "Palette7");

 {% endhighlight %}

 {% highlight vbnet %}
  
   

Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "Palette7"), Syncfusion.Windows.Chart.ChartColorPalette)

 {% endhighlight %}

### Palette8


 {% highlight c# %}
 
   



this.olapchart1.ColorModel.Palette = (Syncfusion.Windows.Chart.ChartColorPalette)Enum.Parse(typeof(Syncfusion.Windows.Chart.ChartColorPalette), "Palette8");

 {% endhighlight %}




 {% highlight vbnet %}
  
  



Me.olapchart1.ColorModel.Palette = CType(System.Enum.Parse(GetType(Syncfusion.Windows.Chart.ChartColorPalette), "Palette8"), Syncfusion.Windows.Chart.ChartColorPalette)

 {% endhighlight %}