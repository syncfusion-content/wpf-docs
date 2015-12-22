---
layout: post
title: Exporting | SfDiagram | wpf | Syncfusion
description: exporting
platform: wpf
control: SfDiagram
documentation: ug
---

## Exporting

Diagram provides support to extent its content as image/svg files



![D:\Diagram\Diagram2015Vol4\2015 November 1st Sprint\UG\Diagram Images\Diagram\Exporting_images\Exporting_img1.png](Exporting_images\Exporting_img1.png)

Exporting Options

Diagram provides support to export the desired region of the Diagram to desired formats.

Format

SfDiagram can be exported to be following File formats.

* PNG

* JPEG

* TIFF

* GIF

* BMP

Contents of the Diagram can be exported as raster image files by using Export function. This exporting can be customized by using ExportSettings.

The following code illustrates how to use ExportSettings property of the SfDiagram:

{% highlight C# %}

ExportSettings settings = new ExportSettings()

{

  ImageStretch = Stretch.Fill,

  ExportMode = ExportMode.PageSettings

};

diagram.ExportSettings = settings;
{% endhighlight %}




The following code shows how to export the SfDiagram



_//Method to Export the SfDiagram_

diagram.Export();





Mode

<table>
<tr>
<td>
ExportMode</td><td>
Description</td></tr>
<tr>
<td>
PageSettings</td><td>
The area to be exported is based on PageSettings and how Children are arranged.</td></tr>
<tr>
<td>
Content</td><td>
Areas occupied by children are exported exactly.</td></tr>
</table>


