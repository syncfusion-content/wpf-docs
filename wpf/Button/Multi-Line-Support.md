---
layout: post
title: Multi Line Support | wpf | Syncfusion
description: This section deals with how to enable the multiline of text support in a buttonadv control on wpf platform.
platform: wpf
control: ButtonAdv
documentation: ug
---

# How to show multi-line text in WPF Button?

[ButtonAdv](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ButtonAdv.html) control allows to show text in multiple lines by setting `IsMultiLine` property to `true`. 

{% tabs %}
{% highlight xaml %}

<syncfusion:ButtonAdv x:Name="ButtonAdv" IsMultiLine="True"  Width="75" Height="75" IconHeight="35" IconWidth="35" Label="Hello World!" SizeMode="Large" />

{% endhighlight %}
{% endtabs %}

![WPF ButtonAdv MultiLine](Multi-Line-Support_images/Multi-Line-Support_img1.png)

[View Sample in GitHub](https://github.com/SyncfusionExamples/How-to-show-the-multi-line-text-in-wpf-button)

N> This property is applicable only for large size mode button.