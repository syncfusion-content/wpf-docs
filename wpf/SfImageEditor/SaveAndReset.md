---
layout: post
title: Saving edited image in syncfusion SfImageEditor WPF.
description: Image saving
platform: wpf
control: SfImageEditor
documentation: ug
---

# Save

Image can be saved along with the edited changes. Saving can be done in the following 2 ways.

* Using Toolbar
* Programmatically using code.

## Toolbar saving

To save the image, click the save icon in the toolbar. You can choose the desired location from the save file dialog to save the edited image.

## Using code

Programmatically image can be saved using the Save method in image editor as follows. Save method takes the following 3 parameters.

* ImageFormat - Specify the format in which image has to be saved.

* Size - Image will be saved in the specified size.

* FilePath - LOcation in which image has to be saved.

{% tabs %} 

{% highlight C# %} 

editor.Save();

{% endhighlight %}

{% endtabs %} 

### Image size specification

You can save the image at the required size by specifying the size parameter in the save method as follows.

{% tabs %} 

{% highlight C# %} 

editor.Save(null, new Size(750,500), null);

{% endhighlight %}

{% endtabs %} 

### Image location

Image can be saved at the specified location as in the below code.

{% tabs %} 

{% highlight C# %} 

editor.Save(null, default(Size), @"E:\Images\");

{% endhighlight %}

{% endtabs %} 

### Image format

You can specify the format in which image has to be saved as the parameter in Save method as follows.

{% tabs %} 

{% highlight C# %} 

 editor.Save("png", default(Size), null);

{% endhighlight %}

{% endtabs %} 

## Reset

To reset the changes made you can click the Reset icon in the toolbar. To programmatically reset use the below code.

{% tabs %} 

{% highlight C# %} 

editor.Reset();

{% endhighlight %}

{% endtabs %} 

## Events

### Saving events.

Image editor has the following 2 events.

* ImageSaving
* ImageSaved

### Image saving

This event will be invoked before the image gets saved to the destination location. `ImageSavingEventArgs` will be the parameter.
This argument contains the following 2 properties.

* Cancel - Cancels the saving functionality.
* Stream - Stream of the image that is going to be saved.

Hence you can control the saving by using the `Cancel` property and also you can access the stream as per your requirement.

Below code cancels the default saving and save the stream in the specified location.

{% tabs %} 

{% highlight C# %} 

 private void Editor_ImageSaving(object sender, ImageSavingEventArgs args)
        {
            args.Cancel = true; 
            FileStream stream = new FileStream(@"E:\Images\Resized.jpg", FileMode.Create);
            args.Stream.CopyTo(stream);
            stream.Seek(0, 0);
        }

{% endhighlight %}

{% endtabs %} 

### Image saved

Image saved event will be invoked after the image has been saved to the destination location. `ImageSavedEventArgs` will be the parameter.
This parameter contains the `Location` property which specify the location in which image is saved.

{% tabs %} 

{% highlight C# %} 

  private void Editor_ImageSaved(object sender, ImageSavedEventArgs args)
        {
            string filePath = args.Location;
        }

{% endhighlight %}

{% endtabs %} 

### Reset events

Reset functionality has the below 2 events.

* BeginReset
* EndReset

### Begin reset

This event is invoked before resetting the changes. Hence you can control the reset operation using the Cancel property in the `BeginResetEventArgs`.

{% tabs %} 

{% highlight C# %} 

  private void Editor_BeginReset(object sender, BeginResetEventArgs e)
        {
            e.Cancel = true;
        }

{% endhighlight %}

{% endtabs %} 

### End reset.

This event is invoked after the reset function gets completed.

{% tabs %} 

{% highlight C# %} 

  private void Editor_EndReset(object sender, EndResetEventArgs e)
        {

        }

{% endhighlight %}

{% endtabs %} 

