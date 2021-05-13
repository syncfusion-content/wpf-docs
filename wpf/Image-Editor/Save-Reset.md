---
layout: post
title: Save Reset in WPF Image Editor control | Syncfusion
description: Learn here all about Save Reset support in Syncfusion WPF Image Editor (SfImageEditor) control and more.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Save Reset in WPF Image Editor (SfImageEditor)

Image can be saved along with the changes. An image can be saved in the following two ways:

* Saving an image using the toolbar.
* Saving an image programmatically.

## Saving an image using the toolbar

To save an image, click the save icon in the toolbar. You can choose the desired location from the save file dialog to save the edited image.

## Saving an image programmatically

An image can be saved programmatically using the Save method in image editor as follows. The save method takes the following three parameters:

* ImageFormat - Specifies the format in which image has to be saved.

* Size - Saves the image in the specified size.

* FilePath - Specifies the location in which image has to be saved.

{% tabs %} 

{% highlight C# %} 

editor.Save();

{% endhighlight %}

{% endtabs %} 

### Image size specification

You can save an image with the required size by specifying the size parameter in the save method as follows.

{% tabs %} 

{% highlight C# %} 

editor.Save(null, new Size(750,500), null);

{% endhighlight %}

{% endtabs %} 

### Image location

Image can be saved at the specified location as demonstrated in the following code.

{% tabs %} 

{% highlight C# %} 

editor.Save(null, default(Size), @"E:\Images\");

{% endhighlight %}

{% endtabs %} 

### Image format

You can specify the format, in which image has to be saved as the parameter in Save method as follows.

{% tabs %} 

{% highlight C# %} 

 editor.Save("png", default(Size), null);

{% endhighlight %}

{% endtabs %} 

## Reset

To reset the changes made, click the Reset icon in the toolbar. To programmatically reset, use the following code.

{% tabs %} 

{% highlight C# %} 

editor.Reset();

{% endhighlight %}

{% endtabs %} 

## Events

### Saving an events

Image editor has the following two events:

* [`ImageSaving`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html)
* [`ImageSaved`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html)

### Image saving

This event occurs before the image is saved to the destination location. [`ImageSavingEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ImageSavingEventArgs.html) is the parameter. This argument contains the following two properties:

* `Cancel` - Cancels the saving functionality.
* [`Stream`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ImageSavingEventArgs.html#Syncfusion_UI_Xaml_ImageEditor_ImageSavingEventArgs__ctor_System_IO_Stream_) - Stream of the image that is going to be saved.
* `FileName` - You can save the image in the specified name using the `ImageSaving` event. 

Hence, you can control the saving using the `Cancel` property, and you can also access the stream as needed.

The following code cancels the default saving and saves the stream in the specified location.

{% tabs %} 

{% highlight xaml %}

        <editor:SfImageEditor x:Name="editor" ImageSaving="editor_ImageSaving" ImageSource="Assets\Buldingimage.jpeg">
        </editor:SfImageEditor>

{% endhighlight %}

{% highlight C# %} 

        private void Editor_ImageSaving(object sender, ImageSavingEventArgs args)
        {
            args.Cancel = true; 
            FileStream stream = new FileStream(@"E:\Images\Resized.jpg", FileMode.Create);
            args.Stream.CopyTo(stream);
            stream.Seek(0, 0);
            args.FileName = "SavedImage";
        }

{% endhighlight %}

{% endtabs %} 

### Image saved

This event occurs after the image has been saved to the destination location. The [`ImageSavedEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ImageSavedEventArgs.html) will be the parameter. This parameter contains the [`Location`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ImageSavedEventArgs.html#Syncfusion_UI_Xaml_ImageEditor_ImageSavedEventArgs_Location) property, which specifies the location in which image is saved.

{% tabs %} 

{% highlight C# %} 

  private void Editor_ImageSaved(object sender, ImageSavedEventArgs args)
        {
            string filePath = args.Location;
        }

{% endhighlight %}

{% endtabs %} 

### Reset events

The Reset functionality has the following two events:

* [`BeginReset`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html)
* [`EndReset`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html)

### Begin reset

This event occurs before resetting the changes. Hence, you can control the reset operation using the Cancel property in the [`BeginResetEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.BeginResetEventArgs.html).

{% tabs %} 

{% highlight C# %} 

  private void Editor_BeginReset(object sender, BeginResetEventArgs e)
        {
            e.Cancel = true;
        }

{% endhighlight %}

{% endtabs %} 

### End reset

This event occurs after the reset function has been completed.

{% tabs %} 

{% highlight C# %} 

  private void Editor_EndReset(object sender, EndResetEventArgs e)
        {

        }

{% endhighlight %}

{% endtabs %} 

## See also

[How to capture and save signature using the image editor](https://www.syncfusion.com/kb/11213/how-to-capture-and-save-signature-using-the-image-editor)
