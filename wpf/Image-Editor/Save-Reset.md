---
layout: post
title: Saving edited image in Syncfusion SfImageEditor for WPF
description: This section describes how to save, reset, and handle image-saving events using the SfImageEditor control through the toolbar or code in WPF.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Save and Reset functionality in Image Editor

An image can be saved along with the changes. An image can be saved in the following two ways:

* Saving an image using the toolbar.
* Saving an image programmatically.

## Saving an image using the toolbar

To save an image, click the save icon in the toolbar. You can choose the desired location from the **Save As** dialog to save the edited image.

## Saving an image programmatically

An image can be saved programmatically using the [`Save`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Save_System_String_System_Windows_Size_System_String_) method in the image editor, as shown in the following code sample. The `Save` method accepts the following three parameters:

* `ImageFormat` - Specifies the format in which the image has to be saved.
* `Size` - Saves the image in the specified size.
* `FilePath` - Specifies the location in which the image has to be saved.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

editor.Save();

{% endhighlight %}

{% endtabs %}

### Image size specification

You can save an image with the required size by specifying the size parameter in the `Save` method, as shown in the following code sample.

{% tabs %}

{% highlight C# %}

using System.Windows;
using Syncfusion.UI.Xaml.ImageEditor;

editor.Save(null, new Size(750, 500), null);

{% endhighlight %}

{% endtabs %}

### Image location

An image can be saved at the specified location, as demonstrated in the following code sample.

{% tabs %}

{% highlight C# %}

using System.Windows;
using Syncfusion.UI.Xaml.ImageEditor;

editor.Save(null, default(Size), @"E:\Images\");

{% endhighlight %}

{% endtabs %}

### Image format

You can specify the format in which the image has to be saved by passing the format as a parameter in the `Save` method, as shown in the following code sample.

{% tabs %}

{% highlight C# %}

using System.Windows;
using Syncfusion.UI.Xaml.ImageEditor;

editor.Save("png", default(Size), null);

{% endhighlight %}

{% endtabs %}

## Reset

To reset the changes, click the **Reset** icon in the toolbar. To reset programmatically, use the following code.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

editor.Reset();

{% endhighlight %}

{% endtabs %}

## Events

### Saving events

The image editor has the following two events:

* [`ImageSaving`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_ImageSaving)
* [`ImageSaved`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_ImageSaved)

### Image saving

This event occurs before the image is saved to the destination location. [`ImageSavingEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ImageSavingEventArgs.html) is the parameter. This argument contains the following three properties:

* `Cancel` - Cancels the saving functionality.
* [`Stream`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ImageSavingEventArgs.html#Syncfusion_UI_Xaml_ImageEditor_ImageSavingEventArgs__ctor_System_IO_Stream_) - Stream of the image that is going to be saved.
* `FileName` - Specifies the name with which the image will be saved. You can override the file name in the `ImageSaving` event.

You can control the saving operation using the `Cancel` property, and you can also access the stream as needed.

The following code sample cancels the default saving and saves the stream to the specified location.

{% tabs %}

{% highlight xaml %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:editor="clr-namespace:Syncfusion.UI.Xaml.ImageEditor;assembly=Syncfusion.SfImageEditor.WPF">
    <Grid>
        <editor:SfImageEditor x:Name="editor"
                              ImageSaving="Editor_ImageSaving"
                              ImageSource="Assets\Buldingimage.jpeg" />
    </Grid>
</Window>

{% endhighlight %}

{% highlight C# %}

using System.IO;
using Syncfusion.UI.Xaml.ImageEditor;

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

This event occurs after the image has been saved to the destination location. [`ImageSavedEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ImageSavedEventArgs.html) is the parameter. It contains the [`Location`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.ImageSavedEventArgs.html#Syncfusion_UI_Xaml_ImageEditor_ImageSavedEventArgs_Location) property, which specifies the location in which the image is saved.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

private void Editor_ImageSaved(object sender, ImageSavedEventArgs args)
{
    string filePath = args.Location;
}

{% endhighlight %}

{% endtabs %}

### Reset events

The Reset functionality has the following two events:

* [`BeginReset`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_BeginReset)
* [`EndReset`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_EndReset)

### Begin reset

This event occurs before the changes are reset. You can cancel the reset operation using the `Cancel` property in [`BeginResetEventArgs`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.BeginResetEventArgs.html).

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

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

using Syncfusion.UI.Xaml.ImageEditor;

private void Editor_EndReset(object sender, EndResetEventArgs e)
{
}

{% endhighlight %}

{% endtabs %}

## See also

[How to capture and save a signature using the image editor](https://support.syncfusion.com/kb/article/9774/how-to-capture-and-save-signature-using-the-image-editor)
