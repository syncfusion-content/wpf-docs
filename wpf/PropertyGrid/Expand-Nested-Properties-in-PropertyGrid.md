---
layout: post
title: Expand-Nested-Properties-in-PropertyGrid
description: expand nested properties in propertygrid
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Expand Nested Properties in PropertyGrid

The PropertyGrid control has support to expand instance properties of a class which has ExpandableObjectConverter as its TypeConverter.

##  Use Case Scenarios

Using the PropertyExpandMode property, users can choose whether the nested properties of the selected object can be expanded or not. By setting the PropertyExpandMode as NestedMode, the nested properties of the selected object can be expanded, and by setting the PropertyExpandMode as FlatMode, the selected object is shown in flat mode.

### Tables for Properties



_Property table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td></tr>
<tr>
<td>
PropertyExpandMode</td><td>
Gets or sets the PropertyExpandMode</td><td>
Dependency</td><td>
Enum</td></tr>
</table>


###  Sample Link

1. Select Start>Programs>Syncfusion>Essential Studio xx.x.x.xx>Dashboard.
2. Select Run Locally Installed Samples in WPF button.
3. Expand the PropertyGrid tree view item in the sample browser.
4. Choose the Getting Started samples listed under it to launch. 



## Adding Expand Nested Properties in Property Grid to an Application 

In the following code sample the PropertyVisiblityMode is set as NestedMode in both XAML and C#.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:PropertyGrid Name="propertyGrid" PropertyExpandMode="NestedMode"&gt;            &lt;/syncfusion:PropertyGrid&gt;</td></tr>
<tr>
<td>
[C#]propertyGrid.PropertyExpandMode = Syncfusion.Windows.PropertyGrid.PropertyGrid.PropertyExpandModes.NestedMode;  </td></tr>
</table>


