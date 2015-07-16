---
layout: post
title: Animation-Support
description: animation support
platform: wpf
control: MenuAdv
documentation: ug
---

# Animation Support

MenuAdv supports animation types to open the submenu pop-up. The following animation types are supported by MenuAdv:

* Fade
* Slide
* Scroll

The Animation support can be used by using the PopUpAnimationType property. If the PopUpAnimationType property is set to None, the submenu will open without any animation.

Adding the Animation Support to an Application

If the PopUpAnimationType property is set to Fade, the submenu will open with faded animation. If the PopUpAnimationType property is set to Slide, the submenu will open like the slide. If the PopUpAnimationType property is set to Scroll, the submenu popup open with scroll animation. The Animation support can be added to an application, as shown in the following code snippet.

[XAML]

&lt;shared:MenuAdv x:Name="Menu" Margin="10" PopUpAnimationType="Slide”&gt;

                &lt;shared:MenuItemAdv Header="File"/&gt;

                &lt;shared:MenuItemAdv Header="Edit"/&gt;

                &lt;shared:MenuItemAdv Header="View"/&gt;

                &lt;shared:MenuItemAdv Header="Project"/&gt;

                &lt;shared:MenuItemAdv Header="VerticalAnimation"&gt;

                    &lt;shared:MenuItemAdv Header="HorizontalAnimation"&gt;

                          &lt;shared:MenuItemAdv Header="Item1"/&gt;

                          &lt;shared:MenuItemAdv Header="Item2"/&gt;

                          &lt;shared:MenuItemAdv Header="Item3"/&gt;

                          &lt;shared:MenuItemAdv Header="Item4"/&gt;

                          &lt;shared:MenuItemAdv Header="Item5"/&gt;

                    &lt;/shared:MenuItemAdv&gt;

                    &lt;shared:MenuItemAdv Header="Item1"/&gt;

                    &lt;shared:MenuItemAdv Header="Item2"/&gt;

                    &lt;shared:MenuItemAdv Header="Item3"/&gt;

                    &lt;shared:MenuItemAdv Header="Item4"/&gt;

                    &lt;shared:MenuItemAdv Header="Item5"/&gt;

                &lt;/shared:MenuItemAdv&gt;

&lt;/shared:MenuAdv&gt;



Properties

The property for the Animation support is described in the following tabulation:

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
PopUpAnimationType</td><td>
Gets or sets the PopUpAnimationType of MenuAdv.</td><td>
DependencyProperty</td><td>
PopUpAnimationType(None)</td></tr>
</table>


Sample Link

WPF Sample Browser-> Tools -> MenuAdv -> MenuAdv Demo

