---
layout: post
title: Theming| OLAP Grid | Wpf | Syncfusion
description: theming
platform: wpf
control: OLAP Grid
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

## Use Case Scenarios

This feature enables users to develop a single application and apply different looks as necessary. 

###  Properties



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th></tr>
<tr>
<td>
VisualStyle </td><td>
Gets or sets the VisualStyle of the OlapGrid control.</td><td>
Dependency Property</td><td>
OlapGridVisualStyle</td></tr>
</table>


## Sample Link

A sample demo available in the following link,

<InstalledDrive>:\Users\sabapathyk\AppData\Local\Syncfusion\EssentialStudio\10.4.0.53\BI\WPF\OlapGrid.WPF\Samples\Appearance\Skin Customization Demo

## Adding Theming to an Application 

The following code sample demonstrates how to add theming to the OlapGrid control.

{% tabs %}
  {% highlight xml %}

   



      <syncfusion:OlapGrid  x:Name="olapGrid" VisualStyle="Transparent"/>

    {% endhighlight %}





  {% highlight c# %}

   



       this.olapGrid.VisualStyle = OlapGridVisualStyle.Transparent;

    {% endhighlight %}


{% endtabs %}






