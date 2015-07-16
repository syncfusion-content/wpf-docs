---
layout: post
title: Scroll-Bar-Support
description: scroll bar support
platform: wpf
control: DropDownButtonAdv
documentation: ug
---

# Scroll Bar Support

The DropDownMenuGroup is shipped with the built-in scrollbar support. It can be made visible by using the property ScrollBarVisibility.

Setting ScrollBarVisibility property to Visible:



[XAML]

&lt;shared:DropDownButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png"&gt;

   &lt;shared:DropDownMenuGroup IsResizable=”True” ScrollBarVisibility=”Visible”&gt;       

&lt;shared:DropDownMenuItem Header="Menu Item 1"/&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 2"/&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 3"/&gt;

   &lt;/shared:DropDownMenuGroup&gt;

&lt;/shared:DropDownButtonAdv&gt;



{ ![](Scroll-Bar-Support_images/Scroll-Bar-Support_img1.png) | markdownify }
{:.image }


