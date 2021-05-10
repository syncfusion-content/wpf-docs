---
layout: post
title: Multiline Text in WPF Split Button control | Syncfusion
description: Learn about Multiline Text support in Syncfusion Essential Studio WPF Split Button control, its elements and more.
platform: wpf
control: SplitButtonAdv
documentation: ug
---

## Multiline Text in WPF Split Button (SplitButtonAdv)

Multiline text support is used to render text content of the Split Button control in multiple lines for precise view. One can apply the multiline text by using the [IsMultiLine](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DropDownButtonAdv.html#Syncfusion_Windows_Tools_Controls_DropDownButtonAdv_IsMultiLine) property.

N> This property is only applicable for large size mode of the Split Button.

{% tabs %}
{% highlight xaml %}

<syncfusion:SplitButtonAdv Label="Sign in with your Syncfusion Account" LargeIcon="image\userlarge.png" SizeMode="Large" IsMultiLine="True"/>

{% endhighlight %}
{% highlight c# %}

SplitButtonAdv splitbutton = new SplitButtonAdv();
splitbutton.Label = "Sign in with your Syncfusion Account";
splitbutton.IsMultiLine =true;
splitbutton.SizeMode = SizeMode.Large;
splitbutton.SmallIcon = new BitmapImage(new Uri("image\userlarge.png"));

{% endhighlight %}
{% endtabs %}

![Multiline](Multi-Line-Support_images/Multi-Line-Support_img1.png)




