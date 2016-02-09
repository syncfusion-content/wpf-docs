---
layout: post
title: Theming| OLAP Client  | Wpf | Syncfusion
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


### Properties

* **VisualStyle** - Gets or Sets the VisualStyle of OlapClient control.



### Sample Link

A demo available in the following location: <InstalledDrive>:\AppData\Local\Syncfusion\EssentialStudio\10.4.0.53\BI\WPF\OlapClient.WPF\Samples\Appearance\SkinCustomizationDemo


## Adding Theming to an Application. 


  The following code samples demonstrate how theming is added to the OlapClient control.

{% tabs %}
{% highlight xaml %} 





      <syncfusion:OlapClient  x:Name="olapClient" VisualStyle="Transparent"/>



{% endhighlight %}

{% highlight C# %}  





       this.olapClient.VisualStyle = OlapClientVisualStyle.Transparent;

{% endhighlight %} 
{% endtabs %}



