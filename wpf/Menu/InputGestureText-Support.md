---
layout: post
title: InputGestureText Support in WPF Menu control | Syncfusion
description: Learn here all about InputGestureText Support in Syncfusion WPF Menu (MenuAdv) control, its elements and more.
platform: wpf
control: MenuAdv
 documentation: ug
---

# InputGestureText Support in WPF Menu (MenuAdv)

InputGestureText is used to set MenuItemAdv to display shortcut keys along with its Header. This support can be utilized by using the InputGestureText property. The value given by using this property will be displayed along with the Header of MenuItemAdv. Also, InputGestureText can be displayed in MenuItemAdv by using the command support. If you set the value of the Command property by using ApplicationCommands the corresponding InputGestureText will be displayed along with its header value automatically.

### Use Case Scenarios

MenuAdv helps users to display the shortcut keys along with the MenuItemAdv header.

## Adding the InputGestureText Support to an Application 

The value assigned by using the InputGestureText property will be displayed in MenuItemAdv along with the Header property value of MenuItemAdv. The InputGestureText support can be added to an application, as shown in the following code snippet.

{% highlight xaml %}




<shared:MenuAdv x:Name="Menu" Margin="10">

<shared:MenuItemAdv Header="File">

<shared:MenuItemAdv Header="New" InputGestureText="Ctrl+n">

<shared:MenuItemAdv.Icon>

<Image Source="/MenuControlDemo;component/Images/NewIcon.jpg"/>

</shared:MenuItemAdv.Icon>

</shared:MenuItemAdv>

<shared:MenuItemAdv Header="Cut" InputGestureText="Ctrl+x">

<shared:MenuItemAdv.Icon>

<Image Source="/MenuControlDemo;component/Images/CutIcon.jpg"/>

</shared:MenuItemAdv.Icon>

</shared:MenuItemAdv>

<shared:MenuItemAdv Header="Copy" InputGestureText="Ctrl+c">

<shared:MenuItemAdv.Icon>

<Image Source="/MenuControlDemo;component/Images/CopyIcon.jpg"/>

</shared:MenuItemAdv.Icon>

</shared:MenuItemAdv>

<shared:MenuItemAdv Header="Paste" InputGestureText="Ctrl+v">

<shared:MenuItemAdv.Icon>

<Image Source="/MenuControlDemo;component/Images/PasteIcon.jpg"/>

</shared:MenuItemAdv.Icon>

</shared:MenuItemAdv>

<shared:MenuItemAdv Header="Undo" InputGestureText="Ctrl+z">

<shared:MenuItemAdv.Icon>

<Image Source="/MenuControlDemo;component/Images/UndoIcon.jpg"/>

</shared:MenuItemAdv.Icon>

</shared:MenuItemAdv>

<shared:MenuItemAdv Header="Redo" InputGestureText="Ctrl+y">

<shared:MenuItemAdv.Icon>

<Image Source="/MenuControlDemo;component/Images/RedoIcon.jpg"/>

</shared:MenuItemAdv.Icon>

</shared:MenuItemAdv>

<shared:MenuItemSeparator/>

</shared:MenuItemAdv>

<shared:MenuItemAdv Header="Edit"/>

<shared:MenuItemAdv Header="View"/>

<shared:MenuItemAdv Header="Project"/>

<shared:MenuItemAdv Header="Build"/>

</shared:MenuAdv>

{% endhighlight %}

![InputGestureText-Support_img1](InputGestureText-Support_images/InputGestureText-Support_img1.png)



### Properties

The property for the InputGestureText support is described in the following tabulation:



<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
InputGestureText</td><td>
Gets or sets the value of InputGestureText of MenuItemAdv.</td><td>
DependencyProperty</td><td>
String(string.Empty)</td></tr>
</table>


### Sample Link

WPF Sample Browser-> Tools -> MenuAdv -> MenuAdv Demo

