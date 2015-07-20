---
layout: post
title: MenuItemSeparator-Support
description: menuitemseparator support
platform: wpf
control: MenuAdv
documentation: ug
---

# MenuItemSeparator Support

MenuItemSeparator is a line, which is used to separate MenuItemAdv’s. MenuItemSeparator can be included in the items list of MenuItemAdv.  

Use Case Scenarios

MenuAdv helps users to separate MenuItemAdv’s by using MenuItemSeparator. In the case of separating the radio button group of items from other items, separator can be used.

Adding the MenuItemSeparator Support to an Application 

MenuItemSeparator can be added to an application, as shown in the following code snippet.

[XAML]

&lt;shared:MenuAdv x:Name="Menu" Margin="10"&gt;

                &lt;shared:MenuItemAdv Header="File"/&gt;

                &lt;shared:MenuItemAdv Header="Edit"/&gt;

                &lt;shared:MenuItemAdv Header="View"&gt;

                    <shared:MenuItemAdv Header="Immediate" 

IsCheckable="True" CheckIconType="CheckBox" IsChecked="True"/>

                    <shared:MenuItemAdv Header="CallStack" 

IsCheckable="True" CheckIconType="CheckBox" IsChecked="False"/>

                    &lt;shared:MenuItemSeparator/&gt;

                    <shared:MenuItemAdv Header="SolutionExplorer" 

IsCheckable="True" CheckIconType="RadioButton" GroupName="group1" 

IsChecked="False"/>

                    <shared:MenuItemAdv Header="TeamExplorer" 

IsCheckable="True" CheckIconType="RadioButton" GroupName="group1" 

IsChecked="True"/>

                    <shared:MenuItemAdv Header="ServerExplorer" 

IsCheckable="True" CheckIconType="RadioButton" GroupName="group1" 

IsChecked="False"/>

                &lt;/shared:MenuItemAdv&gt;

                &lt;shared:MenuItemAdv Header="Project"/&gt;

                &lt;shared:MenuItemAdv Header="Build"/&gt;

            &lt;/shared:MenuAdv&gt;



{ ![C:/Users/Dhileep/Desktop/Vol4-Documentation/ScreenShots/SL-Menu/Chk&Radio.png](MenuItemSeparator-Support_images/MenuItemSeparator-Support_img1.png) | markdownify }
{:.image }


Sample Link

WPF Sample Browser-> Tools -> MenuAdv -> MenuAdv Demo

