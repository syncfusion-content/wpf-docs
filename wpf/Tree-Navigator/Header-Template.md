---
layout: post
title: Header Template in WPF Tree Navigator control | Syncfusion
description: Learn here all about Header Template support in Syncfusion WPF Tree Navigator (SfTreeNavigator) control and more.
platform: wpf
control: SfTreeNavigator 
documentation: ug
---

# Header Template in WPF Tree Navigator (SfTreeNavigator)

The HeaderTemplate property of Tree Navigator can be used to customize the Tree Navigator header. 

{% tabs %}
{% highlight xaml %}

<navigation:SfTreeNavigator.HeaderTemplate>
<DataTemplate>
<TextBlock Text="{Binding}" FontStyle="Italic"/>
</DataTemplate>
</navigation:SfTreeNavigator.HeaderTemplate>
{% endhighlight %}
{% endtabs %}

Tree Navigator now displayed as shown below.

![Header-Template_images1](Header-Template_images/Header-Template_img1.png)
