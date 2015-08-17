---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: CheckListBox
documentation: ug
---

# Getting Started

This section guides you on getting started with CheckListBox control. It covers the following topics:

## Why to use our CheckListBox control

Here are some highlights about our CheckListBox control.

* Selecting items is made much easier on a first mouse-click
* You can align the check box to the right, or left side of the CheckListBox Item
* Drag items between list boxes
* Built-in Visual Styles and Themes support
## Create CheckListBox control


You can create a CheckListBox control either by using XAML code or C# code. To create a CheckListBox control, use the following code.


{%highlight xml%}

[XAML]
    <!-- Adding CheckListBox -->
    <syncfusion:CheckListBox Name="checkListBox">
    <!-- Adding CheckListBox items -->    
	<syncfusion:CheckListBoxItem Content="Mexico"/>  
	<syncfusion:CheckListBoxItem Content="Canada" />   
	<syncfusion:CheckListBoxItem Content="Bermuda" />    
	<syncfusion:CheckListBoxItem Content="Belize" />   
	<syncfusion:CheckListBoxItem Content="Panama" />
	</syncfusion:CheckListBox></td></tr>
	
{%endhighlight%}


{%highlight c#%}

[C#]
// Creating an instance of CheckListBox
   CheckListBox checkListBox = new CheckListBox();
// Creating an instance of CheckListBoxItem
   CheckListBoxItem checkListBoxItem1 = new CheckListBoxItem();
// Adding content to CheckListBoxItem
   checkListBoxItem1.Content = "Mexico";
// Adding CheckListBoxItem to CheckListBox
  checkListBox.Items.Add(checkListBoxItem1);   
// Creating an instance of CheckListBoxItem
   CheckListBoxItem checkListBoxItem2 = new CheckListBoxItem();
// Adding content to CheckListBoxItem
   checkListBoxItem1.Content = "Bermuda";
// Adding CheckListBoxItem to CheckListBox
   checkListBox.Items.Add(checkListBoxItem2); 
// ........
// ........
this.Content = checkListBox;   </td></tr>

{%endhighlight%}


![](Getting-Started_images/Getting-Started_img1.jpeg)



