---
layout: post
title: Layout Types in WPF Radial Menu control | Syncfusion
description: Learn here all about Layout Types support in Syncfusion WPF Radial Menu (SfRadialMenu) control and more.
platform: wpf
control: SfRadialMenu 
 documentation: ug
---
# Layout Types in WPF Radial Menu (SfRadialMenu)

There are two different layout types available for SfRadialMenu.

* Default
* Custom

 Both the layout types divide the available space equally among all the children in the circular panel.

### Default

Number of segments in the panel is determined by children count in the level. Hence segment count in each hierarchical level differs. RadialMenuItem is arranged in the sequential order as added in the RadialMenu.

### Custom

Number of segments in the panel is determined by VisibleSegmentsCount property. Hence segment count in all the hierarchical levels are same. RadialMenuItem is arranged in any order based on the SegmentIndex property.

### VisibleSegmentsCount

VisibleSegmentsCount property is used to specify the number of segments available in circular panel. When children count is greater than the value given in VisibleSegmentsCount property then overflowing children are not arranged in the panel. When children count is lesser than VisibleSegmentsCount property then remaining segments are left free.

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

SegmentIndex property is used to specify the index of the SfRadialMenuItem in circular panel. Based on the index, the RadialMenuItems are inserted in the segment. When SegmentIndex is not specified for a RadialMenuItem (or) two or more RadialMenuItems having the same SegmentIndex, then the menu item is arranged in the next available free segment. 

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





