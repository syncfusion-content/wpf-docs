---
layout: post
title: DropDownMenuItem
description: dropdownmenuitem
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# DropDownMenuItem

Adding Icon to DropDownMenuItem

The DropDownMenuItem control is the basic MenuItem, which forms the actual item of the DropDownMenuGroup. The icon of the DropDownMenuItem can be added as follows:



[XAML]

&lt;shared:SplitButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png"&gt;

   &lt;shared:DropDownMenuGroup&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 1"&gt;

          &lt;shared:DropDownMenuItem.Icon&gt;

              &lt;Image Source="Images/Drink2.png"/&gt;

          &lt;/shared:DropDownMenuItem.Icon&gt;

       &lt;/shared:DropDownMenuItem&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 2"/&gt;

       &lt;shared:DropDownMenuItem Header="Menu Item 3"/&gt;

   &lt;/shared:DropDownMenuGroup&gt;

&lt;/shared:SplitButtonAdv&gt;



{ ![](DropDownMenuItem_images/DropDownMenuItem_img1.png) | markdownify }
{:.image }




Checkable DropDownMenuItem

The DropDownMenuItem can be checked by setting the IsCheckable property to true. 

The feature can be enabled by using the property IsCheckable:



[XAML]

&lt;shared:SplitButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png"&gt;

   &lt;shared:DropDownMenuGroup&gt;

        &lt;shared:DropDownMenuItem Header="Menu Item 1" IsCheckable="True"/&gt;

        &lt;shared:DropDownMenuItem Header="Menu Item 2"/&gt;

        &lt;shared:DropDownMenuItem Header="Menu Item 3" IsCheckable="True"/&gt;

   &lt;/shared:DropDownMenuGroup&gt;

&lt;/shared:SplitButtonAdv&gt;



{ ![](DropDownMenuItem_images/DropDownMenuItem_img2.png) | markdownify }
{:.image }




