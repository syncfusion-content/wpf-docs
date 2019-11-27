---
layout: post
title: Export Diagram content as image files| Syncfusion.
description: How to export the Diagram as image in different formates and how to change the exporting setting in diagram control.
platform: wpf
control: SfDiagram
documentation: ug
---

# Exporting

SfDiagram provides support to export its content as image/XPS files using [Export](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SfDiagram~Export.html "Export") method.
SfDiagram can be exported in the following File formats,

* PNG
* JPEG
* TIFF
* GIF
* BMP
* WDP
* XPS

The following code illustrates how to export the diagram as image,

{% tabs %}
{% highlight C# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Method to Export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

## Export settings

SfDiagram provides various options to customize the exported diagram using [SfDiagram.ExportSettings](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SfDiagram~ExportSettings.html "SfDiagram.ExportSettings") property of type [ExportSettings](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ExportSettings.html "ExportSettings").

### Image Format

You can use [ExportBitmapEncoder](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ExportSettings~ExportBitmapEncoder.html "ExportBitmapEncoder") or [ExportType](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ExportSettings~ExportType.html "ExportType") properties to specify the type/format of the exported image file.

{% tabs %}
{% highlight C# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Specify the file format of the image.
diagram.ExportSettings.ExportType = ExportType.PNG;
       
//Method to Export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Image File Name

You can save the exported image as stream or file system using [ExportStream](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ExportSettings~ExportStream.html "ExportStream") or [FileName](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ExportSettings~FileName.html "FileName") property of `ExportSettings` class respectively.

{% tabs %}
{% highlight C# %}

//Initialize the export settings
ExportSettings settings = new ExportSettings()
{  
  FileName = "export.png",
}; 

diagram.ExportSettings = settings;         
//Method to Export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### ExportMode

[ExportMode](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ExportSettings~ExportMode.html "ExportMode") specifies whether the complete page region the diagram is to be exported or the content region of the diagram. The exporting options are as follows:

| ExportMode| Description | Output |
|---|---|---|
| PageSettings| Region that fits all pages (single or multiple pages based on page settings) |![ExportingPageSettings](Exporting_images/ExportingPageSettings.png) |
| Content| Region that fits all nodes and connectors that are added to model | ![ExportingContent](Exporting_images/ExportingContent.png)|

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
//Method to Export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Export to XPS

SfDiagram has in-built support to export the diagram as XPS file instead of image file. To export diagram as XPS file, set the `IsSaveToXps` property of `ExportSettings` class as `true` and specify the file name with ".xps" extension.

{% tabs %}
{% highlight C# %}

//Initialize the export settings
ExportSettings settings = new ExportSettings()
{  
  IsSaveToXps = true,
  FileName = "export.xps",
}; 

diagram.ExportSettings = settings;         
//Method to Export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

### Export To PDF

SfDiagram does not have the built-in support to convert the diagram as PDF file but you can achieve it by exporting the diagram as XPS file and then convert the exported xps file as PDF using [Syncfusion.XPS.XPSToPdfConverter](https://help.syncfusion.com/cr/file-formats/Syncfusion.Pdf.Base~Syncfusion.XPS.XPSToPdfConverter.html "Syncfusion.XPS.XPSToPdfConverter"). Please refer the [Export the SfDiagram as PDF](https://www.syncfusion.com/kb/8494/how-to-export-the-diagram-as-pdf) KB link for more details.

### Export specific region of diagram

SfDiagram provides supports to export any specific region of the diagram by using 'Clip' proerty of `ExportSettings` class.

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
//Method to Export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

![ExportingClip](Exporting_images/ExportingClip.png)

### Change the background of the exported files

SfDiagram provides supports to change the background color of the exported image using 'ExportBackground' property of `ExportSettings` class.

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
//Method to Export the SfDiagram
diagram.Export();

{% endhighlight %}
{% endtabs %}

![Background](Exporting_images/ExportingBackground.png)