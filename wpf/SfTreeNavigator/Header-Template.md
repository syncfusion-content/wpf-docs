---
layout: post
title: Header-Template
description: header template
platform: wpf
control: Tree Navigator 
documentation: ug
---

# Header Template

The HeaderTemplate property of Tree Navigator can be used to customize the Tree Navigator header. 


{% highlight xml %}
[XAML]

<navigation:SfTreeNavigator.HeaderTemplate>

   <DataTemplate>

      <TextBlock Text="{Binding}" FontStyle="Italic"/>

   </DataTemplate>

</navigation:SfTreeNavigator.HeaderTemplate>
{% endhighlight %}




Tree Navigator now displayed as shown below.



![](Header-Template_images/Header-Template_img1.png)




