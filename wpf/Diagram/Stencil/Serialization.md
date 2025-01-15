---
layout: post
title: Stencil Serialization in WPF Diagram | Syncfusion®
description: Learn how to serialize and deserialize stencils in Syncfusion WPF Diagram (SfDiagram) control, including individual symbol groups.
platform: wpf
control: SfDiagram
documentation: ug
---

# Stencil Serialization in WPF Diagram (SfDiagram)

[Stencil](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.html) serialization is the process of converting the state of stencil into a stream of bytes to recreate them when needed. Such streams can be stored in a database, as a file, or in memory. The reverse process is called deserialization.

### Saving the Stencil

In Stencil, [DataContractSerializer](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.serialization.datacontractserializer?view=net-8.0) is used for serialization. It allows you to serialize and save your stencil into a stream. Here is a simple code example showing how to save the stencil:

{% tabs %}
{% highlight C# %}

// To Save as stream in file
SaveFileDialog dialog = new SaveFileDialog();
dialog.Title = "Save XAML";
dialog.Filter = "XAML File (*.xaml)|*.xaml";
if (dialog.ShowDialog() == true)
{
    using (Stream str = File.Open(dialog.FileName, FileMode.OpenOrCreate))
    {
        stencil.Save(str);
    }
}

// To Save as memory stream
MemoryStream str = new MemoryStream();
stencil.Save(str);

{% endhighlight %}
{% endtabs %}

### Loading the Stencil

On deserialization, the saved stream is used to load the Stencil. We can continue using previously saved stencil by loading the saved stream. Here is a simple code example showing how to load the stencil:

{% tabs %}
{% highlight C# %}

// Load from saved XAML file
OpenFileDialog dialog = new OpenFileDialog();
if (dialog.ShowDialog() == true)
{
    using (Stream myStream = dialog.OpenFile())
    {
        stencil.Load(myStream);
    }
}

// Load from saved memory stream
myStream.Position = 0;
stencil.Load(myStream);

{% endhighlight %}
{% endtabs %}

## Exporting and Importing Symbol Group in Stencil

The Stencil also supports exporting and importing specific symbol groups. This functionality is useful when you need to save and reuse only certain symbol groups.

### Exporting a Symbol Group

In Stencil, the [ExportGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_ExportGroup_System_IO_Stream_System_String___) method allows you to export SymbolGroups. By providing the symbol group names as parameters to this method, you can save the specified SymbolGroups to a stream, preserving all their properties for easy sharing or future use. Here is a simple code example showing how to export the symbol groups:

{% tabs %}
{% highlight C# %}

string[] symbolGroupNames = { "Basic Shapes", "Flow Shapes", "BPMN Editor Shapes" };

SaveFileDialog dialog = new SaveFileDialog();
dialog.Title = "Save XAML";
dialog.Filter = "XAML File (*.xaml)|*.xaml";
if (dialog.ShowDialog() == true)
{
    using (Stream s = File.Open(dialog.FileName, FileMode.OpenOrCreate))
    {
        stencil.ExportGroup(s, symbolGroupNames);
    }
}

{% endhighlight %}
{% endtabs %}

### Importing a Symbol Group

To import the saved symbol groups back into the stencil, use the [ImportGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_ImportGroup_System_IO_Stream_) method with the saved stream. This will load the stencil with the saved symbol groups. Here is a simple code example showing how to import the symbol groups:

{% tabs %}
{% highlight C# %}

OpenFileDialog dialog = new OpenFileDialog();
if (dialog.ShowDialog() == true)
{
    using (Stream myStream = dialog.OpenFile())
    {
        stencil.ImportGroup(myStream);
    }
}

{% endhighlight %}
{% endtabs %}


[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/SymbolGroupSerialize)

## See Also
[How to change the color of a node in the stencil and diagram while loading a saved file in WPF Diagram(SfDiagram)?](https://support.syncfusion.com/kb/article/18669/how-to-change-the-color-of-a-node-in-the-stencil-and-diagram-while-loading-a-saved-file-in-wpf-diagramsfdiagram)

[How to serialize the LinearGradientBrush type as a Fill value in the ShapeStyle of a Node in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18058/how-to-serialize-the-lineargradientbrush-type-as-a-fill-value-in-the-shapestyle-of-a-node-in-the-wpf-diagram-sfdiagram)