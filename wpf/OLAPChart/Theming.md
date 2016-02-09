---
layout: post
title: Theming| OLAP Chart | Wpf | Syncfusion
description: Theming
platform: wpf
control: OLAP Chart
documentation: ug
---

# Theming

Theming is the process of applying particular settings to the visual elements of a product. This feature provides the following theming options:

* Office 2010 Blue
* Office 2010 Black
* Office 2010 Silver
* Transparent
* Office 2007 Blue
* Office 2007 Black
* Office 2007 Silver
* Blend
* Metro
* Office 2003
* Default

###  Properties

* **VisualStyle** - Gets or sets the VisualStyle of the OLAPChart control. 

### Sample Link

A demo is available in the following location:

&lt;InstalledDrive&gt;:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\10.4.0.53\BI\WPF\OlapChart.WPF\Samples\Appearance\Skin Customization Demo

### Adding Theming to an Application 

The following code snippets demonstrate how theming is added to the OLAPChart control.

 {% highlight xaml %}

   

      <syncfusion:OlapChart  x:Name="olapChart" VisualStyle="Transparent"/> 

 {% endhighlight %}



 {% highlight c# %}
 
   


       this.olapChart.VisualStyle = OlapChartVisualStyle.Transparent;

 {% endhighlight %}
