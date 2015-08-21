---
layout: post
title: Theming
description: theming
platform: wpf
control: OLAP Client 
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

## Properties

_Property Table_

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
VisualStyle </td><td>
Gets or Sets the VisualStyle of OlapClient control.</td><td>
Dependency Property</td><td>
OlapClientVisualStyle    </td></tr>
</table>


## Sample Link

A demo available in the following location: <InstalledDrive>:\AppData\Local\Syncfusion\EssentialStudio\10.4.0.53\BI\WPF\OlapClient.WPF\Samples\Appearance\SkinCustomizationDemo


## Adding Theming to an Application. 


  The following code samples demonstrate how theming is added to the OlapClient control.

{% highlight xml %} 





      <syncfusion:OlapClient  x:Name="olapClient" VisualStyle="Transparent"/>



{% endhighlight %}

{% highlight C# %}  





       this.olapClient.VisualStyle = OlapClientVisualStyle.Transparent;

{% endhighlight %} 




