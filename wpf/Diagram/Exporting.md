---
layout: post
title: Exporting in WPF Diagram | Syncfusion®
description: Export diagrams from Syncfusion® WPF Diagram to image and XPS formats with customizable settings, regions, sizes, and backgrounds.
platform: wpf
control: SfDiagram
documentation: ug
---

# Exporting in WPF Diagram

[WPF Diagram](https://www.syncfusion.com/diagram-sdk/wpf-diagram) supports exporting its content as image or XPS files using the [Export](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Export) method. The `Export` method is provided in two overloads:

* `void Export()` — exports to the location specified by `ExportSettings.FileName` or `ExportSettings.ExportStream`.
* `void Export(Stream stream)` — exports directly to the supplied `Stream`.

Diagram can be exported in the following file formats:

* PNG (`ExportType.PNG`)
* JPEG (`ExportType.JPEG`)
* TIFF (`ExportType.TIFF`)
* GIF (`ExportType.GIF`)
* BMP (`ExportType.BMP`)
* WDP (`ExportType.WDP` — Windows Media Photo)
* XPS (set `ExportSettings.IsSaveToXps` to `true`)

The following code explains how to export the diagram as an image:

{% tabs %}
{% highlight c# %}

//Initialize the diagram

SfDiagram diagram = new SfDiagram();

//Method to export the SfDiagram

diagram.Export();

{% endhighlight %}
{% endtabs %}

## Export Settings

Diagram provides various options to customize the exported diagram using the [`SfDiagram.ExportSettings`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_ExportSettings) property of type [ExportSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html). By default, `ExportSettings` is already instantiated on the diagram, so you can set its properties directly or assign a new instance.

| Property | Description | Default |
|---|---|---|
| `ExportType` | Image format used for the export (PNG, JPEG, BMP, TIFF, GIF, WDP). | `PNG` |
| `ExportBitmapEncoder` | Custom `BitmapEncoder` instance; takes precedence over `ExportType` when set. | `null` |
| `FileName` | Output file path; relative paths resolve against the current working directory. | `null` |
| `ExportStream` | Output `Stream`; ignored if `FileName` is set. | `null` |
| `ExportMode` | Region to export — `PageSettings` or `Content`. | `PageSettings` |
| `Clip` | `Rect` that defines the exported region (x, y, width, height). | `Empty` |
| `ImageSize` | Target `Size` for the exported image. | `(0, 0)` (natural size) |
| `ImageShrunk` | How the image fits the `ImageSize` — `None`, `Expand`, `Shrink`, `BestFit`. | `None` |
| `ExportBackground` | `Brush` painted behind the diagram in the export. | `null` (transparent) |
| `IsSaveToXps` | When `true`, the export is written as an XPS document using `FileName`/`ExportStream`. | `false` |

### Image Format

You can use the [`ExportBitmapEncoder`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ExportBitmapEncoder) or [`ExportType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ExportType) properties to specify the type/format of the exported image file. The `ExportType` enum is:

| Value | Description |
|---|---|
| `ExportType.PNG` | Portable Network Graphics image. |
| `ExportType.JPEG` | JPEG image. |
| `ExportType.BMP` | Windows bitmap. |
| `ExportType.TIFF` | Tagged Image File Format. |
| `ExportType.GIF` | Graphics Interchange Format. |
| `ExportType.WDP` | Windows Media Photo. |

{% tabs %}
{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Specify the file format of the image
diagram.ExportSettings.ExportType = ExportType.PNG;
       
//Method to export the Diagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Image File Name

You can save the exported image to a stream or to the file system using the [`ExportStream`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ExportStream) or [`FileName`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_FileName) properties of the `ExportSettings` class, respectively. `FileName` takes precedence when both are set; relative paths resolve against the current working directory.

{% tabs %}
{% highlight c# %}

//Initialize the export settings
ExportSettings settings = new ExportSettings()
{  
  FileName = "export.png",
}; 

diagram.ExportSettings = settings;         
//Method to export the Diagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Export Mode

[ExportMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ExportMode) specifies whether the complete page region of the diagram is to be exported or the content region alone. The exporting options are as follows:

| ExportMode| Description | Output |
|---|---|---|
| PageSettings| Region that fits all pages (single or multiple, based on page settings) |![WPF Diagram displays Export Page Setting Mode](Exporting_images/wpf-diagram-page-setting-mode.png) |
| Content| Region that fits all nodes and connectors that are added to model | ![WPF Diagram displays Export Content Mode](Exporting_images/wpf-diagram-content-mode.png)|

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the export settings-->
  <syncfusion:SfDiagram.ExportSettings>
    <syncfusion:ExportSettings ExportMode="PageSettings"/>
  </syncfusion:SfDiagram.ExportSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}

//Initialize the export settings
ExportSettings settings = new ExportSettings()
{  
    ExportMode = ExportMode.PageSettings,
}; 
   
diagram.ExportSettings = settings;         
//Method to export the Diagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Export to XPS

Diagram has built-in support for exporting the diagram as an XPS file instead of an image file. To export the diagram as an XPS file, set the [`IsSaveToXps`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_IsSaveToXps) property of `ExportSettings` class to `true` (default `false`) and specify the file name with the ".xps" extension.

{% tabs %}
{% highlight c# %}

//Initialize the export settings
ExportSettings settings = new ExportSettings()
{  
  IsSaveToXps = true,
  FileName = "export.xps",
}; 

diagram.ExportSettings = settings;         
//Method to export the Diagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Export to PDF

Diagram does not have built-in support for converting the diagram to a PDF file, but you can achieve this by exporting the diagram as an XPS file and then converting the exported XPS file to a PDF using [Syncfusion.XPS.XPSToPdfConverter](https://help.syncfusion.com/cr/file-formats/Syncfusion.XPS.XPSToPdfConverter.html).

### Export Specific Region of the Diagram

Diagram provides support for exporting any specific region of the diagram by using the [`Clip`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_Clip) property of `ExportSettings` class.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the export settings with clipping area-->
  <syncfusion:SfDiagram.ExportSettings>
    <syncfusion:ExportSettings Clip="200, 200, 200, 300"/>
  </syncfusion:SfDiagram.ExportSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}

//Initialize the export settings with a clipping region.
ExportSettings settings = new ExportSettings()
{  
    Clip = new Rect(200, 0, 200, 500),
}; 
   
diagram.ExportSettings = settings;         
//Method to export the Diagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

![Export Specific Region in WPF Diagram](Exporting_images/wpf-diagram-export-specific-region.png)

### Set the Image Size

Diagram provides support for changing the size of the exported image using the [`ImageSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ImageSize) property of `ExportSettings` class. The default value is `(0, 0)`, which exports the diagram at its natural size.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the export settings with image size-->
  <syncfusion:SfDiagram.ExportSettings>
    <syncfusion:ExportSettings ImageSize="400,400"/>
  </syncfusion:SfDiagram.ExportSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}

//Initialize the export settings with image size
ExportSettings settings = new ExportSettings()
{  
    ImageSize = new Size(400, 400),
}; 
   
diagram.ExportSettings = settings;         
//Method to export the Diagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Set the Image Stretch Options

Diagram provides support for stretching the exported image within the given `ImageSize` using the [`ImageShrunk`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ImageShrunk) property of `ExportSettings` class. The stretching options are as follows:

| ImageShrunk | Description |
|---|---|
| None | Exported image will not be stretched. |
| Expand | Exported image will be expanded to the given image size. |
| Shrink | Exported image will be shrunk to the given image size. |
| BestFit | Exported image will be expanded or shrunk depending on the given image size. |

> The `ImageShrunk` property name is historical and refers to image scaling behavior; the `Expand`/`Shrink` enum values stretch the image to the target `ImageSize`.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the export settings with image shrunk option as expand-->
  <syncfusion:SfDiagram.ExportSettings>
    <syncfusion:ExportSettings ImageShrunk="Expand"/>
  </syncfusion:SfDiagram.ExportSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}

//Initialize the export settings with image shrunk options as expand
ExportSettings settings = new ExportSettings()
{  
    ImageShrunk = ImageShrunk.Expand,
}; 
   
diagram.ExportSettings = settings;         
//Method to export the Diagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Change the Background of the Exported Files

Diagram provides support for changing the background color of the exported image using the [`ExportBackground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ExportBackground) property of `ExportSettings` class. The default value is `null` (transparent). The XAML form uses a `Brush` value (the `BrushConverter` accepts a named color such as `"Blue"`), while the C# form uses a `SolidColorBrush`.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the export settings with background color-->
  <syncfusion:SfDiagram.ExportSettings>
    <syncfusion:ExportSettings ExportBackground="Blue"/>
  </syncfusion:SfDiagram.ExportSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}

//Initialize the export settings with background color
ExportSettings settings = new ExportSettings()
{  
    ExportBackground = new SolidColorBrush(Colors.Blue),
}; 
   
diagram.ExportSettings = settings;         
//Method to export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

![Changing Export Files Background in WPF Diagram](Exporting_images/wpf-diagram-export-background.png)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Exporting)

## See Also
 
[How to export the Diagram as PDF?](https://support.syncfusion.com/kb/article/7520/how-to-export-the-diagram-as-a-pdf-in-the-wpf-diagram-sfdiagram)

[How to Export the Visible Area Within the ViewPort in WPF Diagram?](https://support.syncfusion.com/kb/article/18001/how-to-export-the-visible-area-within-the-viewport-in-wpf-diagram)

[How to avoid the node clipping while export in the WPF Diagram?](https://support.syncfusion.com/kb/article/15536/how-to-avoid-the-node-clipping-while-export-in-the-wpf-diagram)