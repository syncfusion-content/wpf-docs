---
layout: post
title: Icon Support in WPF Menu control | Syncfusion
description: Learn here all about Icon Support in Syncfusion WPF Menu (MenuAdv) control, its elements and more details.
platform: wpf
control: MenuAdv
documentation: ug
---

# Icon Support in WPF Menu (MenuAdv)

MenuItemAdv allows users to display an image on the left of the control. Icon for MenuItemAdv can be set by providing the image source as a value for the Icon property of the MenuItemAdv class.

## Use Case Scenarios

MenuAdv helps users to display an image on the left of the control.

## Adding the Icon Support to an Application 

The Icon support can be added to an application by using the Icon property of MenuItemAdv, as shown in the following code snippet.

{% highlight xaml %}






<shared:MenuAdv x:Name="Menu"/>

<shared:MenuItemAdv Header="File">

<shared:MenuItemAdv Header="New">

<shared:MenuItemAdv.Icon>

<Image Source="/MenuControlDemo;component/Images/NewIcon.jpg"/>

</shared:MenuItemAdv.Icon>

</shared:MenuItemAdv>

<shared:MenuItemAdv Header="Copy">

<shared:MenuItemAdv.Icon>

<Image Source="/MenuControlDemo;component/Images/CopyIcon.jpg"/>

</shared:MenuItemAdv.Icon>

</shared:MenuItemAdv>

<shared:MenuItemAdv Header="Cut">

<shared:MenuItemAdv.Icon>

<Image Source="/MenuControlDemo;component/Images/CutIcon.jpg"/>

</shared:MenuItemAdv.Icon>

</shared:MenuItemAdv>

</shared:MenuItemAdv>

<shared:MenuItemAdv Header="Edit"/>

</shared:MenuAdv>
{% endhighlight %}


![Icon-Support_img1](Icon-Support_images/Icon-Support_img1.png)


### Properties

The property for the Icon support is described in the following tabulation:



<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
Icon</td><td>
Gets or sets the Icon of MenuItemAdv.</td><td>
DependencyProperty</td><td>
Object(null)</td></tr>
</table>


### Sample Link

WPF Sample Browser-> Tools -> MenuAdv -> MenuAdv Demo

