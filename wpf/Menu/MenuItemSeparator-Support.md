---
layout: post
title: MenuItemSeparator Support in WPF Menu control | Syncfusion
description: Learn here all about MenuItemSeparator Support in Syncfusion WPF Menu (MenuAdv) control, its elements and more.
platform: wpf
control: MenuAdv
 documentation: ug
---

# MenuItemSeparator Support in WPF Menu (MenuAdv)

MenuItemSeparator is a line, which is used to separate MenuItemAdv’s. MenuItemSeparator can be included in the items list of MenuItemAdv.  

### Use Case Scenarios

MenuAdv helps users to separate MenuItemAdv’s by using MenuItemSeparator. In the case of separating the radio button group of items from other items, separator can be used.

## Adding the MenuItemSeparator Support to an Application 

MenuItemSeparator can be added to an application, as shown in the following code snippet.

{% highlight xaml %}




<shared:MenuAdv x:Name="Menu" Margin="10">

<shared:MenuItemAdv Header="File"/>

<shared:MenuItemAdv Header="Edit"/>

<shared:MenuItemAdv Header="View">

<shared:MenuItemAdv Header="Immediate" 

IsCheckable="True" CheckIconType="CheckBox" IsChecked="True"/>

<shared:MenuItemAdv Header="CallStack" 

IsCheckable="True" CheckIconType="CheckBox" IsChecked="False"/>

<shared:MenuItemSeparator/>

<shared:MenuItemAdv Header="SolutionExplorer" 

IsCheckable="True" CheckIconType="RadioButton" GroupName="group1" 

IsChecked="False"/>

<shared:MenuItemAdv Header="TeamExplorer" 

IsCheckable="True" CheckIconType="RadioButton" GroupName="group1" 

IsChecked="True"/>

<shared:MenuItemAdv Header="ServerExplorer" 

IsCheckable="True" CheckIconType="RadioButton" GroupName="group1" 

IsChecked="False"/>

</shared:MenuItemAdv>

<shared:MenuItemAdv Header="Project"/>

<shared:MenuItemAdv Header="Build"/>

</shared:MenuAdv>

{% endhighlight %}

![MenuItemSeparator support in WPF MenuAdv](MenuItemSeparator-Support_images/MenuItemSeparator-Support_img1.png)



### Sample Link

WPF Sample Browser-> Tools -> MenuAdv -> MenuAdv Demo

