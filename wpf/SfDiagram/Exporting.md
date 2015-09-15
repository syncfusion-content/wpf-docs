---
layout: post
title: Exporting
description: exporting
platform: wpf
control: Control Name undefined
documentation: ug
---

### Exporting

SfDiagram can be exported to the following File formats:

Image File Format

1.   Png
2. Jpeg
3. Tiff
4. Gif
5. Bitmap



Contents of the Diagram can be exported as raster image files by using Export function. This exporting can be customized by using ExportSettings.



The following code illustrates how to use ExportSettings Property of the SfDiagram:

[C#]

  ExportSettings settings= new ExportSettings() 

     {
          //Stretch Option for Exporting the Image

          ImageStretch = Stretch.Uniform,

          //Specifies the Modes for Exporting

          ExportMode = ExportMode.Content

     };   



  //Assigns the ExportSettings

  sfdiagram.ExportSettings = settings;





The following code shows how to export the SfDiagram:

[C#]

 //Method to Export the SfDiagram

 sfdiagram.Export();





1. Export Mode

<table>
<tr>
<th>
ExportMode</th><th>
Description</th></tr>
<tr>
<td>
PageSettings</td><td>
The area to be exported is based on PageSettings and how Children are arranged.</td></tr>
<tr>
<td>
Content</td><td>
Areas occupied by children are exported exactly.</td></tr>
</table>


