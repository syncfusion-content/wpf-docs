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

### Use Case Scenarios

This feature enables users to develop a single application and apply different looks as necessary.

###  Properties



<table>
<tr>
<th>
Property</th><th>
Description}</th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
VisualStyle </td><td>
Gets or sets the VisualStyle of the OLAPChart control. </td><td>
Dependency Property</td><td>
OlapChartVisualStyle</td></tr>
</table>


### Sample Link

A demo is available in the following location:

&lt;InstalledDrive&gt;:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\10.4.0.53\BI\WPF\OlapChart.WPF\Samples\Appearance\Skin Customization Demo

### Adding Theming to an Application 

The following code snippets demonstrate how theming is added to the OLAPChart control.

 {% highlight xml %}

   

      <syncfusion:OlapChart  x:Name="olapChart" VisualStyle="Transparent"/> 

 {% endhighlight %}



 {% highlight c# %}
 
   


       this.olapChart.VisualStyle = OlapChartVisualStyle.Transparent;

 {% endhighlight %}
