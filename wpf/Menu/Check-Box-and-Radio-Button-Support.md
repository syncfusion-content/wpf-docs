---
layout: post
title: Check Box and Radio Button Support in WPF Menu control | Syncfusion
description: Learn here all about Check Box and Radio Button Support in Syncfusion WPF Menu (MenuAdv) control and more.
platform: wpf
control: MenuAdv
 documentation: ug
---

# Check Box and Radio Button Support in WPF Menu (MenuAdv)

MenuAdv provides a support for selecting several items. MenuItemAdv can be checked by setting the IsCheckable property of the MenuItemAdv to “true”. You can change the icon type (Check Box or Radio Button) by using the CheckIcon property also it can be checked by using the IsChecked property.

### Use Case Scenarios

MenuAdv helps users to use MenuItemAdv with the CheckBox or RadioButton support.

## Using the Check Box and Radio Button Support in an Application

If you set the CheckIcon property to RadioButton, then MenuItemAdv’s will be grouped based on the value of the GroupName property and end user can select only one item from the group. Similarly, if you set the CheckIcon property to CheckBox, then MenuItemAdv can be checked and unchecked. The Check Box and Radio Button support can be used in an application, as shown in the following the code snippet.

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

![CheckBox and Radio Button Support in wpf MenuAdv](Check-Box-and-Radio-Button-Support_images/Check-Box-and-Radio-Button-Support_img1.png)



### Properties

The properties for the Check box and Radio button support are described in the following tabulation:   



<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
IsCheckable</td><td>
Gets or sets the value of IsCheckable in MenuItemAdv.</td><td>
DependencyProperty</td><td>
bool(false)</td></tr>
<tr>
<td>
CheckIconType</td><td>
Gets or sets the CheckIconType of MenuItemAdv.</td><td>
DependencyProperty</td><td>
CheckIconType(CheckBox)</td></tr>
<tr>
<td>
IsChecked</td><td>
Gets or sets the IsChecked value of MenuItemAdv.</td><td>
DependencyProperty</td><td>
bool(false)</td></tr>
</table>


### Sample Link

WPF Sample Browser-> Tools -> MenuAdv -> MenuAdv Demo

