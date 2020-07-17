---
layout: post
title: Resource ID for Syncfusion Themes| SkinStorage (Classic) | Wpf | Syncfusion
description: resource id for syncfusion themes
platform: wpf
control: SkinStorage (Classic)
documentation: ug
---

# Resource ID for Syncfusion Themes

The WPF Skin Manager provides a swatch of theme colors that contains all Syncfusion theme brushes. These brushes are used by getting key names for the given particular theme. Brush names are stored as properties in the ThemeColors class.

N> ThemeColors class has been referred at application level by adding Syncfusion.Shared.WPF assembly.

### Use case scenarios

Users can customize brushes easily to get unique colors for all controls in the application.



### Properties

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
Gets the background color of the control</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
HoverBrush</td><td>
Gets the mouse hover color of the control</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
SelectedBrush</td><td>
Gets the foreground color of selected control</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
BorderBrush</td><td>
Gets the border color of the control</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
Foreground</td><td>
Gets the foreground color of text</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
ActiveWindowTitleBrush</td><td>
Gets the background color of active window header</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
InActiveWindowTitleBrush</td><td>
Gets the background color of inactive window header</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
RibbonPanelBrush</td><td>
Gets the background color of the ribbon panel</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
MenuBackgroundBrush</td><td>
Gets the background color of Menu</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
MenuHoverBrush</td><td>
Gets the mouse hover color of the MenuItem</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
GalleryHeaderSelectedBrush</td><td>
Gets the foreground color of selected GalleryHeader</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
TrackBrush</td><td>
Gets the background color of scrollbar track</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
HorizontalThumbBrush</td><td>
Gets the background color of horizontal thumb</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
VerticalThumbBrush</td><td>
Gets the background color of vertical thumb</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
HorizontalThumbHoverBrush</td><td>
Gets the background color of the horizontal thumb when mouse is hovered</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
VerticalThumbHoverBrush</td><td>
Gets the background color of the vertical thumb when mouse is hovered</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
HorizontalThumbPressedBrush</td><td>
Gets the background color of pressed horizontal thumb</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
VerticalThumbPressedBrush</td><td>
Gets the background color of pressed vertical thumb </td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
ColumnHeaderBrush</td><td>
Gets the background color of column header </td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
TabHoverBrush</td><td>
Gets the background color of hovered TabItem </td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
TabHoverBorderBrush</td><td>
Gets the border color of hovered TabItem </td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
CardViewGroupingBarBrush</td><td>
Gets the background color of the CardView grouping header </td><td>
CLR</td><td>
String</td></tr>
</table>


## Adding resource ID to an application

### Setting through XAML

The following code snippet explains how to set the Resource ID through XAML

1. Add the VisualStyle in the sample.

{% tabs %}
{% highlight xaml %}
 
syncfusion:SkinStorage.VisualStyle="Office2013"

{% endhighlight %}
{% endtabs %}

2. Set Resource ID as shown below.

{% tabs %}
{% highlight xaml %}

<Grid x:Name="grid" Background="{DynamicResource {x:Static syncfusion:ThemeColors.BackgroundBrush}}">

{% endhighlight %}
{% endtabs %}

## Setting through C#

{% tabs %}
{% highlight C# %}

SkinStorage.SetVisualStyle(this, "Office2013");
grid.SetResourceReference(BackgroundProperty, ThemeColors.BackgroundBrush);

{% endhighlight %}
{% endtabs %}
