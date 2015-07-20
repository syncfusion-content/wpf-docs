---
layout: post
title: Selection-Mode-Support
description: selection mode support
platform: wpf
control: AutoComplete
documentation: ug
---

# Selection Mode Support

AutoComplete supports two kinds of Selection Mode namely Single and Multiple. You can select the Mode using the SelectionMode property. 

When the SelectionMode property is set as Single, only one item can be selected at a time. The following image illustrates the Single selection mode.

{{ '![C:/Users/Dhileep/Desktop/Vol4-Documentation/ScreenShots/WPF-AC/SingleSelection.png](Selection-Mode-Support_images/Selection-Mode-Support_img1.png)' | markdownify }}
{:.image }




When the SelectionMode is set as Multiple, you can select multiple items by using the SeparatorChar property to separate the selected items. By default the SeparatorChar is “;”. This allows you to select multiple items by using the SelectionMode property. Once an item is selected the Separatorchar is to be entered in the text box to select the next item.

The following image illustrates the Multiple selection mode.

{{ '![C:/Users/Dhileep/Desktop/Vol4-Documentation/ScreenShots/WPF-AC/MultipleSelection.png](Selection-Mode-Support_images/Selection-Mode-Support_img2.png)' | markdownify }}
{:.image }




When the SelectionMode is set as Extended, you can select multiple items at a time by pressing the Ctrl key. While selecting the multiple items, the selected items will be separated by the SeparatorChar automatically.

The following image illustrates the Multiple selection mode.

{{ '![C:/Users/Dhileep/Desktop/Vol4-Documentation/ScreenShots/WPF-AC/ExtendedSelection.png](Selection-Mode-Support_images/Selection-Mode-Support_img3.png)' | markdownify }}
{:.image }




Adding Single, Multiple & Extended Selection Support to an Application 

The Selectionmode property is used to attain these functionalities by setting its value as Single or Multiple or Extended. By default its value is Single. The following code snippet is used to set the SelectionMode property. 

<table>
<tr>
<td>
[XAML]<syncfusion:AutoComplete x:Name="AutoComplete2" SelectionMode="Multiple"/></td></tr>
<tr>
<td>
[C#]AutoComplete autoComplete1 = new AutoComplete();this.autoComplete2.SelectionMode = SelectionMode.Multiple;</td></tr>
</table>


Tables for properties, and events

Property

  _Property Table for Selection Mode_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td><td>
Reference links </td></tr>
<tr>
<td>
SelectionMode</td><td>
Gets or Sets the SelectionMode of the AutoComplete.</td><td>
DependencyProperty</td><td>
SelectionMode(Single)</td><td>
</td></tr>
</table>


Events

  _Event Table for Selection Mode_

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th><th>
Reference links </th></tr>
<tr>
<th>
SelectionModeChanged</th><th>
 When the SelectionMode property value is changed, this event will be triggered.It cannot be cancelled.</th><th>
DependencyObject,DependencyPropertyChangedEventArgs</th><th>
DependencyPropertyChangedCallBack </th><th>
</th></tr>
</table>


Sample Link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo

