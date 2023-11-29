---
layout: post
title: Exporting in WPF Diagram control | Syncfusion
description: Learn here all about Exporting support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Exporting in WPF Diagram (SfDiagram)

SfDiagram provides the support to export its content as image/XPS files using the [Export](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Export) method.
SfDiagram can be exported in the following File formats.

* PNG
* JPEG
* TIFF
* GIF
* BMP
* WDP
* XPS

The following code explains how to export the diagram as image.

{% tabs %}
{% highlight C# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Method to export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

## Export settings

SfDiagram provides various options to customize the exported diagram using the [`SfDiagram.ExportSettings`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_ExportSettings) property of type [ExportSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html).

### Image format

You can use the [`ExportBitmapEncoder`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ExportBitmapEncoder) or [`ExportType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ExportType) properties to specify the type/format of the exported image file.

{% tabs %}
{% highlight C# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Specify the file format of the image
diagram.ExportSettings.ExportType = ExportType.PNG;
       
//Method to export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Image file name

You can save the exported image as stream or file system using the [`ExportStream`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ExportStream) or [`FileName`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_FileName) properties of [`ExportSettings`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html) class respectively.

{% tabs %}
{% highlight C# %}

//Initialize the export settings
ExportSettings settings = new ExportSettings()
{  
  FileName = "export.png",
}; 

diagram.ExportSettings = settings;         
//Method to export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### ExportMode

[ExportMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ExportMode) specifies whether the complete page region of the diagram is to be exported or the content region alone. The exporting options are as follows:

| ExportMode| Description | Output |
|---|---|---|
| PageSettings| Region that fits all pages (single or multiple pages based on page settings) |![WPF Diagram displays Export Page Setting Mode](Exporting_images/wpf-diagram-page-setting-mode.png) |
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
{% highlight C# %}

//Initialize the export settings
ExportSettings settings = new ExportSettings()
{  
    ExportMode = ExportMode.PageSettings,
}; 
   
diagram.ExportSettings = settings;         
//Method to export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Export to XPS

SfDiagram has in-built support to export the diagram as XPS file instead of image file. To export diagram as XPS file, set the [`IsSaveToXps`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_IsSaveToXps) property of [`ExportSettings`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html) class to `true` and specify the file name with ".xps" extension.

{% tabs %}
{% highlight C# %}

//Initialize the export settings
ExportSettings settings = new ExportSettings()
{  
  IsSaveToXps = true,
  FileName = "export.xps",
}; 

diagram.ExportSettings = settings;         
//Method to export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Export to PDF

SfDiagram does not have the built-in support to convert the diagram to PDF file, but you can achieve this by exporting the diagram as XPS file and then convert the exported XPS file to PDF using [Syncfusion.XPS.XPSToPdfConverter](https://help.syncfusion.com/cr/file-formats/Syncfusion.XPS.XPSToPdfConverter.html).

### Export specific region of diagram

SfDiagram provides the supports to export any specific region of the diagram by using the [`Clip`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_Clip) property of [`ExportSettings`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html) class.

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
{% highlight C# %}

//Initialize the export settings with clipping area
ExportSettings settings = new ExportSettings()
{  
    Clip = new Rect(200,0,200,500),
}; 
   
diagram.ExportSettings = settings;         
//Method to export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

![Export Specific Region in WPF Diagram](Exporting_images/wpf-diagram-export-specific-region.png)

### Change the size of the exported files

SfDiagram provides the supports to change the size of the exported image using the [`ImageSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ImageSize) property of [`ExportSettings`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html) class.

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
{% highlight C# %}

//Initialize the export settings with image size
ExportSettings settings = new ExportSettings()
{  
    ImageSize = new Size(400, 400),
}; 
   
diagram.ExportSettings = settings;         
//Method to export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Change the strech options of the exported files

SfDiagram provides the supports to strech the exported image within given image size using the [ImageShrunk](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ImageShrunk) property of [`ExportSettings`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html) class. The streching options are as follows:

| ImageShrunk | Description |
|---|---|
| None | Exported image will not be streched |
| Expand | Exported image will be expaned to the given image size |
| Shrink| Exported image will be shrinked to the given image size |
| BestFit| Exported image will be expaned/shrinked depends on given image size |

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
{% highlight C# %}

//Initialize the export settings with image shrunk options as expand
ExportSettings settings = new ExportSettings()
{  
    ImageShrunk = ImageShrunk.Expand,
}; 
   
diagram.ExportSettings = settings;         
//Method to export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Change the background of the exported files

SfDiagram provides the supports to change the background color of the exported image using the [`ExportBackground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html#Syncfusion_UI_Xaml_Diagram_ExportSettings_ExportBackground) property of [`ExportSettings`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExportSettings.html) class.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the export settings with clipping area-->
  <syncfusion:SfDiagram.ExportSettings>
    <syncfusion:ExportSettings ExportBackground="Blue"/>
  </syncfusion:SfDiagram.ExportSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}

//Initialize the export settings with clipping area
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
