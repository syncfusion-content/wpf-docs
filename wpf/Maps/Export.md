---
layout: post
title: Export in WPF Maps control | Syncfusion
description: Learn here all about Map Export support in Syncfusion WPF Maps (SfMap) control, its elements and more details.
platform: wpf
control: SfMap
documentation: ug
---

# Export in WPF Maps (SfMap)

The SfMap control provides built-in support to export the rendered map view into PNG, JPEG, and SVG formats. The export captures the fully rendered visual state of the map exactly as displayed on the screen.

## Overview

The export functionality enables you to generate image or scalable outputs of the map, including all layers, visual elements, and styling. The export operation works on the rendered visual tree of the SfMap control rather than raw data, ensuring:

* Accurate visual representation
* Theme consistency
* Complete rendering fidelity

## Supported Export Formats

<table>
  <tr>
    <th>Format</th>
    <th>Type</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>PNG</td>
    <td>Raster</td>
    <td>Lossless image export suitable for high-quality output</td>
  </tr>
  <tr>
    <td>JPEG</td>
    <td>Raster</td>
    <td>Compressed image export suitable for sharing</td>
  </tr>
  <tr>
    <td>SVG</td>
    <td>Vector (Hybrid)</td>
    <td>Scalable output with embedded raster content</td>
  </tr>
</table>

## Supported Export Formats

The map can be exported as an image in the following formats.

* JPEG
* PNG
* SVG

## Exporting the Map

You can export the current map view using the ExportMaps method available in the SfMap control.

{% tabs %}

{% highlight C# %} 

map.ExportMaps(ExportFormat format, string fileName, string filePath = null);

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C#  hl_lines="2,5,8" %} 

### Parameters

<table>
  <tr>
    <th>Parameter</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>format</td>
    <td>Specifies the export format (PNG, JPEG, SVG)</td>
  </tr>
  <tr>
    <td>fileName</td>
    <td>Name of the exported file (extension added automatically)</td>
  </tr>
  <tr>
    <td>filePath</td>
    <td>Optional export directory. Defaults to system Downloads folder</td>
  </tr>
</table>

// Export map as PNG
map.ExportMaps(ExportFormat.PNG, "WorldMapExport");

// Export map as JPEG
map.ExportMaps(ExportFormat.JPEG, "WorldMapExport");

// Export map as SVG
map.ExportMaps(ExportFormat.SVG, "WorldMapExport", filePath: @"C:\Users\Public\Documents");

{% endhighlight %}

{% endtabs %}

### Parameters

format: Specifies the export format (PNG, JPEG, or SVG).
fileName: Name of the exported file without extension.
filePath (optional): Directory path to save the exported file. If not specified, the file will be saved in the Downloads folder.

N>
* The export occurs only after the map is fully rendered, including data binding, color mappings, bubble sizing, labels, legends, markers, tile loading, and zoom/pan stabilization. The export process captures the final visual state and does not reprocess data. Tooltips are not included in the exported output.

* The export includes all visible layers such as ShapeFileLayer, ImageryLayer (Bing, OpenStreetMap, Azure, etc.), sublayers, and overlays. Proper Z-ordering, visibility, and opacity settings are preserved in the exported result.





