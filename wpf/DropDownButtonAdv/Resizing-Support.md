---
layout: post
title: Resizing-Support
description: resizing support
platform: wpf
control: DropDownButtonAdv
documentation: ug
---

# Resizing Support

The DropDownMenuGroup supports resizing, if the property IsResizable is set to true.

Setting IsResizable property to true:



 [XAML]

&lt;shared:DropDownButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png"&gt;

   &lt;shared:DropDownMenuGroup IsResizable=”True”&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 1"/&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 2"/&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 3"/&gt;

   &lt;/shared:DropDownMenuGroup&gt;

&lt;/shared:DropDownButtonAdv&gt;



{ ![](Resizing-Support_images/Resizing-Support_img1.png) | markdownify }
{:.image }


