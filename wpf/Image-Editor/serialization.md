---
layout: post
title: Serialization in syncfusion SfImageEditor WPF.
description: Serialization support in Syncfusion Essential Studio WPF ImageEditor (SfImageEditor) control, its elements and more.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Serialization in SfImageEditor

The Image Editor control provides support to serialize and deserialize the shape, text and pen annotations along with their settings. You can save the current state of the image editor annotations and load it back when it is needed.

## Serialization

The `Serialize` method is used to serialize the current edits of shapes. It allows you to store the `SfImageEditor` annotations to the stream by passing the stream as a parameter to the `Serialize` method.

{% tabs %}

{% highlight C# %}
    
	//To Save as stream in file
    SaveFileDialog dialog = new SaveFileDialog();
    dialog.Title = "Save XAML";
    dialog.Filter = "XAML File (*.xaml)|*.xaml";
    if (dialog.ShowDialog() == true)
    {
        using (Stream stream = File.Open(dialog.FileName, FileMode.CreateNew))
        {
            imageEditor.Serialize(stream);
            imageEditor.Reset();
        }
    }
    
	
{% endhighlight %}

{% endtabs %}

## Deserialization

The `Deserialize` method is used to deserialize the annotations over an image. It allows you to reload the `SfImageEditor` control with the annotations available in the stream.

{% tabs %}

{% highlight C# %}
       
    //Load from saved XAML file
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
