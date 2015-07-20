---
layout: post
title: Scroll-Bar-Support
description: scroll bar support
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# Scroll Bar Support

The DropDownMenuGroup is shipped with the built-in scrollbar support. It can be made visible by using the ScrollBarVisibility property.

Setting ScrollBarVisibility property to Visible:



[XAML]

&lt;shared:SplitButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png"&gt;

   &lt;shared:DropDownMenuGroup IsResizable=”True” ScrollBarVisibility=”True”&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 1"/&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 2"/&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 3"/&gt;

   &lt;/shared:DropDownMenuGroup&gt;

&lt;/shared:SplitButtonAdv&gt;



{ ![](Scroll-Bar-Support_images/Scroll-Bar-Support_img1.png) | markdownify }
{:.image }


