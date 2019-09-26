---
layout: post
title: Getting Started for the Syncfusion ImageEditor.
description: Getting start with simple application using SfImageEditor in WPF.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Getting Started

This section explains the steps required to load an image to the image editor control. It has a built-in toolbar that helps in performing the various editing operation such as Flip, Crop, Rotate, Save, annotating with shapes and text, zoom and pan.

## Adding ImageEditor Reference

After installing Essential Studio for WPF, you can find the required assemblies in the installation folder,

SfImageEditor is available in the following assembly and namespace:

Assembly: Syncfusion.SfImageEditor.WPF

Namespace: Syncfusion.UI.Xaml.ImageEditor

You can also refer [article](https://help.syncfusion.com/wpf/add-syncfusion-controls) to know how to add Syncfusion controls in Visual Studio projects through various way. 
 
## Initialize ImageEditor

Import the Image editor namespace as in the below code snippet.

{% tabs %} 

{% highlight xaml %} 

xmlns:editor="clr-namespace:Syncfusion.UI.Xaml.ImageEditor;assembly=Syncfusion.SfImageEditor.WPF"

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.UI.Xaml.ImageEditor;

{% endhighlight %}

{% endtabs %} 

Then initialize the image editor as in the below snippet.

{% tabs %} 

{% highlight xaml %} 

 <editor:SfImageEditor>
 </editor:SfImageEditor>

{% endhighlight %}

{% highlight C# %} 

 SfImageEditor editor = new SfImageEditor();

{% endhighlight %}

{% endtabs %} 


## Loading image in ImageEditor

Image can be loaded in following two ways.

Using image soure.

Using stream.

You can load the image source as in the below code snippet.

{% tabs %} 

{% highlight xaml %} 

<editor:SfImageEditor x:Name="editor" ImageSource="Assets/Buldingimage.jpeg">
</editor:SfImageEditor>

{% endhighlight %}

{% highlight C# %} 

   BitmapImage image = new BitmapImage();
   image.BeginInit();
   image.UriSource = new Uri(@"Assets/Buldingimage.jpeg", UriKind.Relative);
   image.EndInit();
   editor.ImageSource = image;

{% endhighlight %}

{% endtabs %} 


You can load the image as stream using the below code snippet.

{% highlight C# %} 

  OpenFileDialog openFileDialog = new OpenFileDialog();
            openFileDialog.Filter = "Image Files(*.BMP;*.JPG;*.GIF)|*.BMP;*.JPG;*.GIF|All files (*.*)|*.* ";

            if (openFileDialog.ShowDialog() == true)
            {
                var stream = openFileDialog.OpenFile();
                editor.Image = stream;
            }

{% endhighlight %}

![ImageEditor](Images/ImageEditor.png)   
