---
layout: post
title: Multiline Text in WPF Button control | Syncfusion
description: Learn here all about Multiline Text support in Syncfusion WPF Button (ButtonAdv) control, its elements and more details.
platform: WPF
control: ButtonAdv
documentation: ug
---

# Multiline Text in WPF Button (ButtonAdv)

Multiline support is used to render text content of the Button control in multiple lines for precise view. One can apply the multiline text by using the [IsMultiLine](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ButtonAdv.html#Syncfusion_Windows_Tools_Controls_ButtonAdv_IsMultiLine) property.

N> This property is only applicable for large size mode button.

{% tabs %}
{% highlight XAML %}

<syncfusion:ButtonAdv x:Name="ButtonAdv" IsMultiLine="True" LargeIcon="image1/employee.png" Label="Sign in with your Syncfusion Account" SizeMode="Large" />

{% endhighlight %}
{% highlight c# %}

ButtonAdv button = new ButtonAdv();
button.SizeMode = SizeMode.Large;
button.LargeIcon = new BitmapImage(new Uri("employee.png"));
button.IsMultiLine="true";
button.Label = "Sign in with your Syncfusion Account";

{% endhighlight %}
{% endtabs %}

![WPF ButtonAdv MultiLine](Multi-Line-Support_images/Multi-Line-Support_img1.png)
