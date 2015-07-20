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



[XAML]

&lt;navigation:SfTreeNavigator.HeaderTemplate&gt;

   &lt;DataTemplate&gt;

      &lt;TextBlock Text="{Binding}" FontStyle="Italic"/&gt;

   &lt;/DataTemplate&gt;

&lt;/navigation:SfTreeNavigator.HeaderTemplate&gt;





Tree Navigator now displayed as shown below.



{ ![4](Header-Template_images/Header-Template_img1.png) | markdownify }
{:.image }




