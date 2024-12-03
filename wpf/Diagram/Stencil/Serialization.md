---
layout: post
title: Stencil Serialization in WPF Diagram | Syncfusion
description: Learn how to serialize and deserialize stencils in Syncfusion WPF Diagram (SfDiagram) control, including individual symbol groups.
platform: wpf
control: SfDiagram
documentation: ug
---

# Stencil Serialization in WPF Diagram (SfDiagram)

[Stencil](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.html) serialization allows users to save and restore the state of a stencil, including all symbol groups and their properties, in SfDiagram. By serializing to XAML format, you can easily persist the stencil across sessions or share it between applications, ensuring it retains its original state when reloaded.

### Saving the Stencil

Serialization of a stencil involves converting its current state into a format that can be stored and retrieved later. Here we use the [DataContractSerializer](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.serialization.datacontractserializer?view=net-8.0) to serialize and save your stencil either as a file or to memory.


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

During the stencil loading process, the saved stream is utilized to restore stencil elements into the current diagram. This allows you to seamlessly continue using a previously saved stencil by loading the corresponding stream.

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

## Exporting and Importing Individual Symbol Groups

The Stencil also supports exporting and importing specific symbol groups. This functionality is particularly beneficial where only a subset of symbols need to be shared or reused.

### Exporting a Symbol Group

To export a specific symbol group in stencil, follow this example:

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

To import a symbol group into the stencil, follow this example:

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



