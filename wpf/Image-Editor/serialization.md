---
layout: post
title: Serialization in Syncfusion SfImageEditor for WPF
description: This section describes how to serialize and deserialize the annotations in the Syncfusion Essential Studio WPF ImageEditor (SfImageEditor) control.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Serialization in Image Editor (SfImageEditor)

The Image Editor control supports serializing and deserializing the shape, text, pen, and custom view annotations along with their settings. You can save the current state of the image editor annotations and restore it when needed.

## Serialization

The [`Serialize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Serialize_System_IO_Stream_) method is used to serialize the current edits of the annotations. It allows you to store the [`SfImageEditor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html) annotations to a stream by passing the stream as a parameter to the `Serialize` method.

{% tabs %}

{% highlight C# %}

using System.IO;
using Microsoft.Win32;
using Syncfusion.UI.Xaml.ImageEditor;

SaveFileDialog dialog = new SaveFileDialog();
dialog.Title = "Save XML";
dialog.Filter = "XML File (*.xml)|*.xml";
if (dialog.ShowDialog() == true)
{
    using (Stream stream = File.Open(dialog.FileName, FileMode.CreateNew))
    {
        editor.Serialize(stream);
    }
}

{% endhighlight %}

{% endtabs %}

## Deserialization

The [`Deserialize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Deserialize_System_IO_Stream_) method is used to deserialize the annotations over an image. It allows you to reload the [`SfImageEditor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html) control with the annotations available in the stream.

{% tabs %}

{% highlight C# %}

using System.IO;
using Microsoft.Win32;
using Syncfusion.UI.Xaml.ImageEditor;

OpenFileDialog dialog = new OpenFileDialog();
if (dialog.ShowDialog() == true)
{
    using (Stream myStream = dialog.OpenFile())
    {
        editor.Deserialize(myStream);
    }
}

{% endhighlight %}

{% endtabs %}

## Annotations collection

The Image Editor exposes a read-only collection of annotations through the [`Annotations`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Annotations) property. This property contains all the annotations currently visible in the image editor.

N> This collection is reset if the background image is changed.

The following code sample filters the rectangle shapes from the `Annotations` collection and re-adds them to the image editor.

{% tabs %}

{% highlight C# %}

using System.Linq;
using Syncfusion.UI.Xaml.ImageEditor;
using Syncfusion.UI.Xaml.ImageEditor.Enums;

var rectangleAnnotations = editor.Annotations
    .Where(item => item.Type == ShapeType.Rectangle)
    .ToList();
foreach (var item in rectangleAnnotations)
{
    editor.AddShape(item.Type, item.PenSettings);
}

{% endhighlight %}

{% endtabs %}