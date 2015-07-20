---
layout: post
title: Orientation-Support
description: orientation support
platform: wpf
control: MenuAdv
documentation: ug
---

# Orientation Support

The MenuAdv control can align its content vertically and horizontally by using the Orientation property of the MenuAdv class.

When the value of the Orientation property is set to Horizontal, the Items of MenuAdv will be arranged horizontally.

{ ![C:/Users/Dhileep/Desktop/Vol4-Documentation/ScreenShots/SL-Menu/Createusingc#.png](Orientation-Support_images/Orientation-Support_img1.png) | markdownify }
{:.image }


Similarly, when the value of the Orientation property is set to Vertical, the Items of MenuAdv will be arranged vertically.

{ ![C:/Users/Dhileep/Desktop/Vol4-Documentation/ScreenShots/SL-Menu/Verti-Orien.png](Orientation-Support_images/Orientation-Support_img2.png) | markdownify }
{:.image }


Use Case Scenarios

MenuAdv helps users to set the Menu items in Horizontal or Vertical orientations.

Adding the Orientation Support to an Application

Users can add the Orientation support to MenuAdv used in the application as mentioned in the code snippet below.

[XAML]

&lt;shared:MenuAdv x:Name="Menu"  Orientation="Horizontal”/&gt;

                &lt;shared:MenuItemAdv Header="File"&gt;

                    &lt;shared:MenuItemAdv Header="New"&gt;

                        &lt;shared:MenuItemAdv.Icon&gt;

                            &lt;Image Source="/MenuControlDemo;component/Images/NewIcon.jpg"/&gt;

                        &lt;/shared:MenuItemAdv.Icon&gt;

                    &lt;/shared:MenuItemAdv&gt;

                    &lt;shared:MenuItemAdv Header="Copy"&gt;

                        &lt;shared:MenuItemAdv.Icon&gt;

                            &lt;Image Source="/MenuControlDemo;component/Images/CopyIcon.jpg"/&gt;

                        &lt;/shared:MenuItemAdv.Icon&gt;

                    &lt;/shared:MenuItemAdv&gt;

                    &lt;shared:MenuItemAdv Header="Cut"&gt;

                        &lt;shared:MenuItemAdv.Icon&gt;

                            &lt;Image Source="/MenuControlDemo;component/Images/CutIcon.jpg"/&gt;

                        &lt;/shared:MenuItemAdv.Icon&gt;

                    &lt;/shared:MenuItemAdv&gt;

                &lt;/shared:MenuItemAdv&gt;

                &lt;shared:MenuItemAdv Header="Edit"/&gt;

&lt;/shared:MenuAdv&gt;



Properties

The property for the Orientation support is described in the following tabulation:

_Property Table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td></tr>
<tr>
<td>
Orientation</td><td>
Gets or sets the Orientation of MenuAdv.</td><td>
DependencyProperty</td><td>
Orientation(Horizontal)</td></tr>
</table>


Sample Link

WPF Sample Browser-> Tools -> MenuAdv -> MenuAdv Demo

## Expand Modes Support

Expand Modes in MenuAdv is used to open the submenu of each MenuItemAdv, which is added in MenuAdv by doing click to open the submenu or by doing mouse hover to open the submenu. MenuAdv supports two kinds of Expand Modes, namely ExpandOnClick and ExpandOnMouseOver, which can be obtained by using the ExpandMode property. 

Use Case Scenarios

MenuAdv helps users to use Expand Modes to open the submenu of MenuItemAdv added in MenuAdv.

Using the Expand Modes Support in an Application 

When the ExpandMode property is set to ExpandOnClick, you can open the submenu of each MenuItemAdv, which is added MenuAdv by clicking it. This type of expand mode is used to open menus in Windows operating system. Similarly, when the ExpandMode property is set to ExpandOnMouseOver, you can open the submenu of each MenuItemAdv, which is added in MenuAdv by moving the mouse pointer over it. Therefore, you need not click to open the submenu. You can achieve this functionality by using the ExpandMode property, as shown in the following code snippet.

[XAML]



&lt;shared:MenuAdv x:Name="Menu"  ExpandMode="ExpandOnMouseOver”/&gt;

                &lt;shared:MenuItemAdv Header="File"&gt;

                    &lt;shared:MenuItemAdv Header="New"&gt;

                        &lt;shared:MenuItemAdv.Icon&gt;

                            &lt;Image Source="/MenuControlDemo;component/Images/NewIcon.jpg"/&gt;

                        &lt;/shared:MenuItemAdv.Icon&gt;

                    &lt;/shared:MenuItemAdv&gt;

                    &lt;shared:MenuItemAdv Header="Copy"&gt;

                        &lt;shared:MenuItemAdv.Icon&gt;

                            &lt;Image Source="/MenuControlDemo;component/Images/CopyIcon.jpg"/&gt;

                        &lt;/shared:MenuItemAdv.Icon&gt;

                    &lt;/shared:MenuItemAdv&gt;

                    &lt;shared:MenuItemAdv Header="Cut"&gt;

                        &lt;shared:MenuItemAdv.Icon&gt;

                            &lt;Image Source="/MenuControlDemo;component/Images/CutIcon.jpg"/&gt;

                        &lt;/shared:MenuItemAdv.Icon&gt;

                    &lt;/shared:MenuItemAdv&gt;

                &lt;/shared:MenuItemAdv&gt;

                &lt;shared:MenuItemAdv Header="Edit"/&gt;

&lt;/shared:MenuAdv&gt;





Properties

The property for the Expand Modes support is described in the following tabulation:

_Property Table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td></tr>
<tr>
<td>
ExpandMode</td><td>
Gets or sets the ExpandMode of MenuAdv.</td><td>
DependencyProperty</td><td>
ExpandModes(ExpandOnClick)</td></tr>
</table>


Sample Link

WPF Sample Browser-> Tools -> MenuAdv -> MenuAdv Demo

