---
layout: post
title: Animation Support in WPF Menu | Syncfusion®
description: Animation Support in MenuAdv provides visual transition effects when opening and interacting with menu items.
platform: wpf
control: MenuAdv
documentation: ug
---

# Animation Support in WPF Menu (MenuAdv)

MenuAdv supports animation types to open the submenu pop-up. The following animation types are supported by MenuAdv:

* Fade - The submenu will open with a faded animation.
* Slide - The submenu will open like a slide.
* Scroll - The submenu pop-up will open with a scroll animation.
* None - The submenu will open without any animation.

The Animation support can be used by using the PopUpAnimationType property. If the PopUpAnimationType property is set to None, the submenu will open without any animation.

## Adding the Animation Support to an Application

The Animation support can be added to an application, as shown in the following code snippet.

{% highlight xaml %}

<shared:MenuAdv x:Name="Menu" Margin="10" PopUpAnimationType="Slide">
    <shared:MenuItemAdv Header="File" />
    <shared:MenuItemAdv Header="Edit" />
    <shared:MenuItemAdv Header="View" />
    <shared:MenuItemAdv Header="Project" />
    <shared:MenuItemAdv Header="VerticalAnimation">
        <shared:MenuItemAdv Header="HorizontalAnimation">
            <shared:MenuItemAdv Header="Item1" />
            <shared:MenuItemAdv Header="Item2" />
            <shared:MenuItemAdv Header="Item3" />
            <shared:MenuItemAdv Header="Item4" />
            <shared:MenuItemAdv Header="Item5" />
        </shared:MenuItemAdv>
        <shared:MenuItemAdv Header="Item1" />
        <shared:MenuItemAdv Header="Item2" />
        <shared:MenuItemAdv Header="Item3" />
        <shared:MenuItemAdv Header="Item4" />
        <shared:MenuItemAdv Header="Item5" />
    </shared:MenuItemAdv>
</shared:MenuAdv>

{% endhighlight %}


### Properties

The property for the Animation support is described in the following table:


<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
PopUpAnimationType</td><td>
Gets or sets the PopUpAnimationType of MenuAdv.</td><td>
DependencyProperty</td><td>
PopUpAnimationType(None)</td></tr>
</table>


### Sample Link

WPF Sample Browser-> Tools -> MenuAdv -> MenuAdv Demo

