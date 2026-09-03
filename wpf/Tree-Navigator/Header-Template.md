---
layout: post
title: Header Template in WPF Tree Navigator | Syncfusion®
description: Header Template support in Tree Navigator allows customization of item headers using templates to display content with a tailored appearance.
platform: wpf
control: Tree Navigator 
documentation: ug
---

# Header Template in WPF Tree Navigator

The HeaderTemplate property of [SfTreeNavigator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Navigation.SfTreeNavigator.html) control can be used to customize the Tree Navigator header. 

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

![Header Template in WPF Tree Navigator](Header-Template_images/Header-Template_img1.png)
