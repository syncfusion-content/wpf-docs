---
layout: post
title: Resource-ID-for-Syncfusion-Themes
description: resource id for syncfusion themes
platform: wpf
control: SkinManager
documentation: ug
---

# Resource ID for Syncfusion Themes

The WPF Skin Manager provides a swatch of theme colors that contains all Syncfusion theme brushes. These brushes are used by getting key names for the given particular theme. Brush names are stored as properties in the ThemeColors class.

## Use Case Scenarios

Users can customize brushes easily to get unique colors for all controls in the application.

### Tables for Properties, Methods, and Events

#### Properties

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
BackgroundBrush</td><td>
Sets the brush as the background color.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
HoverBrush</td><td>
Sets the brush when the mouse hovers over the control.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
SelectedBrush</td><td>
Sets the brush for when the control is selected.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
BorderBrush</td><td>
Sets the brush for the border color.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
Foreground</td><td>
Sets the brush as text foreground color.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
ActiveWindowTitleBrush</td><td>
Sets the brush for the active window header background.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
InActiveWindowTitleBrush</td><td>
Sets the brush for the inactive window header background.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
RibbonPanelBrush</td><td>
Sets the brush as for the ribbon panel background.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
MenuBackgroundBrush</td><td>
Sets the brush as the menu background.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
MenuHoverBrush</td><td>
Sets the brush when the mouse hovers over a menu item.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
GalleryHeaderSelectedBrush</td><td>
Sets the brush when the gallery header is selected.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
TrackBrush</td><td>
Sets the brush in the scrollbar background track.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
HorizontalThumbBrush</td><td>
Sets the brush for the background in horizontal thumbs.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
VerticalThumbBrush</td><td>
Sets the brush for the background in vertical thumbs.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
HorizontalThumbHoverBrush</td><td>
Sets the brush as the background when the mouse hovers over a horizontal thumb.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
VerticalThumbHoverBrush</td><td>
Sets the brush as the background when the mouse hovers over a vertical thumb.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
HorizontalThumbPressedBrush</td><td>
Sets the brush as the background when a horizontal thumb is pressed.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
VerticalThumbPressedBrush</td><td>
Sets the brush as the background when a vertical thumb is pressed.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
ColumnHeaderBrush</td><td>
Sets the brush as the background for the column header.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
TabHoverBrush</td><td>
Sets the brush as the background when the mouse hovers over the tab item.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
TabHoverBorderBrush</td><td>
Sets the brush as the border when the mouse hovers over the tab item.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
CardViewGroupingBarBrush</td><td>
Sets the brush as the background for the CardView grouping header.</td><td>
CLR</td><td>
Brush</td></tr>
</table>


### Adding Resource ID to an Application

## Setting Through XAML

The following code snippet explains how to set the Resource ID through XAML

1. Add the VisualStyle in the sample.


             syncfusion:SkinStorage.VisualStyle="Office2007Blue”



2. Set Resource ID as shown below.



              <Grid Background="{DynamicResource {x:Static syncfusion:ThemeColors.HoverBrush}}"/>

   {:.prettyprint}

## Setting Through C#



{% highlight C# %}

Grid.Background = ThemeColors.BackgroundBrush

{% endhighlight %}

