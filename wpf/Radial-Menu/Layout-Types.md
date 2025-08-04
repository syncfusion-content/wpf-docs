---
layout: post
title: Layout Types in WPF Radial Menu Control | Syncfusion®
description: Learn about the layout types supported in the Syncfusion® WPF Radial Menu (SfRadialMenu) control.
platform: WPF
control: SfRadialMenu 
documentation: ug
---
# Layout Types in WPF Radial Menu (SfRadialMenu)

The SfRadialMenu offers two different layout types:
- Default
- Custom

Both layout types divide the available space equally among all the children in the circular panel.

### Default

In this layout, the number of segments in the panel is determined by the count of children at each level. Thus, the segment count differs at each hierarchical level. `RadialMenuItems` are arranged in the sequence they are added to the RadialMenu.

### Custom

In this layout, the number of segments in the panel is determined by the `VisibleSegmentsCount` property, ensuring the segment count remains constant across all hierarchical levels. `RadialMenuItems` can be arranged in any order based on the `SegmentIndex` property.

### VisibleSegmentsCount

The `VisibleSegmentsCount` property specifies the number of segments available in the circular panel. If the number of children exceeds `VisibleSegmentsCount`, the extra children are not displayed. If fewer children exist, the remaining segments are left empty.

{%tabs%}
{%highlight xaml%}

<navigation:SfRadialMenu LayoutType="Custom" VisibleSegmentsCount="7" />

{%endhighlight%}

{%highlight c#%}
SfRadialMenu radialMenu = new SfRadialMenu();
radialMenu.LayoutType = LayoutType.Custom;
 radialMenu.VisibleSegmentsCount = 7; 
{%endhighlight%}

{%endtabs%}


### SegmentIndex

The `SegmentIndex` property specifies the index of a `SfRadialMenuItem` within the circular panel. Based on this index, `RadialMenuItems` are inserted into segments. If `SegmentIndex` is not specified or multiple `RadialMenuItems` have the same `SegmentIndex`, the menu items are placed in the next available free segment.

{%tabs%}
{%highlight xaml%}

<navigation:SfRadialMenu LayoutType="Custom" VisibleSegmentsCount="7" />  
 <navigation:SfRadialMenuItem Header="Item  2" SegmentIndex="1" />   
 <navigation:SfRadialMenuItem Header="Item 5" SegmentIndex="4" />   
 <navigation:SfRadialMenuItem Header="Item 1" SegmentIndex="0" />  
 <navigation:SfRadialMenuItem Header="Item 6" SegmentIndex="5" />  
 <navigation:SfRadialMenuItem Header="Item 3" SegmentIndex="2" />
 </navigation:SfRadialMenu> 
{%endhighlight%}

{%highlight c#%}

SfRadialMenu radialMenu = new SfRadialMenu();
radialMenu.LayoutType = LayoutType.Custom; 
radialMenu.VisibleSegmentsCount = 7; 
SfRadialMenuItem item2 = new SfRadialMenuItem() { Header = "Item 2", SegmentIndex = 1 };               
SfRadialMenuItem item5 = new SfRadialMenuItem() { Header   ="Item 5", SegmentIndex = 4 };
SfRadialMenuItem item1 = new SfRadialMenuItem() { Header = "Item 1", SegmentIndex = 0 };
SfRadialMenuItem item6 = new SfRadialMenuItem() { Header = "Item 6", SegmentIndex = 5 };
SfRadialMenuItem item3 = new SfRadialMenuItem() { Header = "Item 3",SegmentIndex = 2 };
radialMenu.Items.Add(item2);radialMenu.Items.Add(item5);radialMenu.Items.Add(item1);
radialMenu.Items.Add(item6); radialMenu.Items.Add(item3); </td></tr>
{%endhighlight%}

{%endtabs%}

![Concepts_img7](Concepts_images/Concepts_img7.png)






