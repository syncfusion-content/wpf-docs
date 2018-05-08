---
layout: post
title: ScRGB Color | ColorPicker | wpf | Syncfusion
description: scrgb color
platform: wpf
control: ColorPicker
documentation: ug
---

# ScRGB Color

Using the IsScRGBColor property, user can set the value indicating whether this instance is ScRGB color. To enable this property use the following code.

{% tabs %}
{% highlight xaml %}

<!-- Adding ColorEdit -->
<syncfusion:ColorEdit IsScRGBColor="True" Margin="20" Name="colorEdit"/>

{% endhighlight %}

{% highlight C# %}

//Creating an instance of color edit
ColorEdit colorEdit = new ColorEdit();

//Setting ScRGBColorEdit.
IsScRGBColor = true;

//Adding control to the window
this.Content = colorEdit;

{% endhighlight %}
{% endtabs %}

![](ScRGB-Color_images/ScRGB-Color_img1.jpeg)
