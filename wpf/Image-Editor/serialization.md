---
layout: post
title: Serialization in Syncfusion SfImageEditor WPF.
description: This section describes how to serialize and deserialize the annotations in Syncfusion Essential Studio WPF ImageEditor (SfImageEditor) control
platform: wpf
control: SfImageEditor
documentation: ug
---

# Serialization in Image Editor (SfImageEditor)

The Image Editor control provides support to serialize and deserialize the shape, text, pen annotations, and custom view along with their settings. You can save the current state of the image editor annotations and load it back when it is needed.

## Serialization

The [Serialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Serialize_System_IO_Stream_) method is used to serialize the current edits of annotations. It allows you to store the [SfImageEditor](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html) annotations to the stream by passing the stream as a parameter to the [Serialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Serialize_System_IO_Stream_) method.

{% tabs %}

{% highlight C# %}
    
    SaveFileDialog dialog = new SaveFileDialog();
    dialog.Title = "Save XML";
    dialog.Filter = "XML File (*.xml)|*.xml";
    if (dialog.ShowDialog() == true)
    {
        using (Stream stream = File.Open(dialog.FileName, FileMode.CreateNew))
        {
            imageEditor.Serialize(stream);
        }
    }
    
	
{% endhighlight %}

{% endtabs %}

## Deserialization

The [Deserialize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Deserialize_System_IO_Stream_) method is used to deserialize the annotations over an image. It allows you to reload the [SfImageEditor](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html) control with the annotations available in the stream.

{% tabs %}

{% highlight C# %}
       
    OpenFileDialog dialog = new OpenFileDialog();
    if (dialog.ShowDialog() == true)
    {
        using (Stream myStream = dialog.OpenFile())
        {
            imageEditor.Deserialize(myStream);
        }
    }

{% endhighlight %}

{% endtabs %}

## Annotations collection

The Image Editor provides the read-only collection of annotations using the [Annotations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Annotations) property. The [Annotations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Annotations) property contains all the annotations currently visible in image editor.

N> This collection will be reset if the background image has been changed.

The following code sample only adds a rectangle shape from the [Annotations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Annotations) collection.

{% tabs %}

{% highlight C# %}
       
    var rectangleAnnotations = this.imageEditor.Annotations.ToList().Where(item => item.Type == ShapeType.Rectangle);
    foreach (var item in rectangleAnnotations)
    {
        this.imageEditor.AddShape(item.Type, item.PenSettings);
    }

{% endhighlight %}

{% endtabs %}