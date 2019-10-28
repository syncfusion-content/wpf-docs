---
layout: post
title: Export Diagram content as image files.
description: How to export the Diagram as image?
platform: wpf
control: SfDiagram
documentation: ug
---

# Exporting

SfDiagram provides support to export the desired region of the Diagram to desired formats.Contents of the SfDiagram can be exported as raster image files by using Export method. 

The exporting can be customized by using [ExportSettings](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ExportSettings_members.html) property of the SfDiagram.

SfDiagram can be exported in the following File formats.

* PNG
* JPEG
* TIFF
* GIF
* BMP

{% tabs %}
{% highlight C# %}

//Basic and customization properties for exporting
ExportSettings settings = new ExportSettings()
  {  
   ImageStretch = Stretch.Fill,
   ExportMode = ExportMode.Content
  }; 
   
Diagram.ExportSettings = settings;         
//Method to Export the SfDiagram
Diagram.Export();

{% endhighlight %}
{% endtabs %}

## Export To PDF

SfDiagram provides support to export the Diagram as XPS format by using the `IsSaveToXps` property of `ExportSettings`.

We can convert the XPS document into PDF file through `Syncfusion.XPS.XPSToPdfConverter`.Please refer to the KB link to [Export the SfDiagram as PDF](https://www.syncfusion.com/kb/8494/how-to-export-the-diagram-as-pdf).