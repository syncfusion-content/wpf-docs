# Exporting

Diagram provides support to extent its content as image/svg files

![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Exporting_images/Exporting_img1.png](Exporting_images/Exporting_img1.jpeg)


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

<table>
<tr>
<td>
ExportSettings settings = new ExportSettings()<br/><br/>{<br/><br/>ImageStretch = Stretch.Fill,<br/><br/>ExportMode = ExportMode.PageSettings<br/><br/>};<br/><br/>diagram.ExportSettings = settings;<br/><br/><br/><br/></td></tr>
</table>
The following code shows how to export the SfDiagram

<table>
<tr>
<td>
{{'__//__'| markdownify }}{{'__Method__ '| markdownify }}{{'__to__ '| markdownify }}{{'__Export__ '| markdownify }}{{'__the__ '| markdownify }}{{'__SfDiagram__'| markdownify }}{{'____'| markdownify }}<br/><br/>diagram.Export();<br/><br/><br/><br/></td></tr>
</table>
Mode

<table>
<tr>
<td>
ExportMode<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
PageSettings<br/><br/></td><td>
The area to be exported is based on PageSettings and how Children are arranged.<br/><br/></td></tr>
<tr>
<td>
Content<br/><br/></td><td>
Areas occupied by children are exported exactly.<br/><br/></td></tr>
</table>
