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

Sfdiagram uses `BitmapEncoder` to convert the page as image with specified file format. When file format is not specified, image format will be referred from `BitmapEncoder` class.

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

`FileName` property of `ExportSettings` class is the name of the file to be exported.

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

SfDiagram allows to export the page region of the diagram or to export the content of the diagram only using `ExportMode` property of `ExportSettings` class.

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

| ExportMode| Description | Output |
|---|---|---|
| PageSettings| Region that fits all pages (single or multiple pages based on page settings) |![ExportingPageSettings](Exporting_images/ExportingPageSettings.png) |
| Content| Region that fits all nodes and connectors that are added to model | ![ExportingContent](Exporting_images/ExportingContent.png)|

### Export to XPS

To export the diagram into xps file format, enable the `IsSaveToXps` property of `ExportSettings` class.

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

SfDiagram provides support to export the Diagram as XPS format by using the `IsSaveToXps` property of `ExportSettings`.

We can convert the XPS document into PDF file through `Syncfusion.XPS.XPSToPdfConverter`.Please refer to the KB link to [Export the SfDiagram as PDF](https://www.syncfusion.com/kb/8494/how-to-export-the-diagram-as-pdf).

### Export specific region of diagram

Diagram supports to export any specific area of diagram page by using 'Clip' proerty of `ExportSettings` class.

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

Diagram supports to change the background color of the exported page using 'ExportBackground' property of `ExportSettings` class.

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