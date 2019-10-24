---
layout: post
title: Header Template | SfTreeNavigator | wpf | Syncfusion
description: header template
platform: wpf
control: SfTreeNavigator 
documentation: ug
---

# Header Template

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

![4](Header-Template_images/Header-Template_img1.png)
