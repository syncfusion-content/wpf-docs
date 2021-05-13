---
layout: post
title: ZOrdering in WPF Image Editor control | Syncfusion
description: Learn here all about ZOrdering support in Syncfusion WPF Image Editor (SfImageEditor) control and more.
platform: wpf
control: SfImageEditor
documentation: ug
---

# ZOrdering in WPF Image Editor (SfImageEditor)

The image editor allows you to change the position of shapes that are arranged in the editor. This can be achieved using the following methods:

1. BringToFront
2. SendToBack
3. BringForward
4. SendBackward

## BringToFront

This method brings the selected shape to the front of all the shapes added in the image.

{% tabs %} 

{% highlight C# %} 

        editor.BringToFront(); 

{% endhighlight %}

{% endtabs %} 

## BringForward

This method brings the selected shape to one step forward from its current position.

{% tabs %} 

{% highlight C# %} 

         editor.BringForward(); 

{% endhighlight %}

{% endtabs %} 

## SendToBack

This method pushes the selected shape to the back of all the shapes added.

{% tabs %} 

{% highlight C# %} 

       editor.SendToBack();

{% endhighlight %}

{% endtabs %} 

## SendBackward

This method pushes the selected shape one step back from its current position.

{% tabs %} 

{% highlight C# %} 

       editor.SendBackward();  

{% endhighlight %}

{% endtabs %} 

![Shapes](Images/ZOrdering.png)
