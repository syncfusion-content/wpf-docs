---
layout: post
title: Z-Ordering of Shapes in Syncfusion SfImageEditor WPF
description: This section describes how to arrange the shapes added in the image editor as required by changing their Z-order.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Z-Ordering in WPF ImageEditor (SfImageEditor)

The image editor allows you to change the position of shapes arranged in the editor. This can be achieved using the following methods:

1. BringToFront
2. SendToBack
3. BringForward
4. SendBackward

## BringToFront

This method brings the selected shape to the front of all the shapes added in the image.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

editor.BringToFront();

{% endhighlight %}

{% endtabs %}

## BringForward

This method brings the selected shape one step forward from its current position.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

editor.BringForward();

{% endhighlight %}

{% endtabs %}

## SendToBack

This method pushes the selected shape to the back of all the added shapes.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

editor.SendToBack();

{% endhighlight %}

{% endtabs %}

## SendBackward

This method pushes the selected shape one step backward from its current position.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

editor.SendBackward();

{% endhighlight %}

{% endtabs %}

![Shapes](Images/ZOrdering.png)