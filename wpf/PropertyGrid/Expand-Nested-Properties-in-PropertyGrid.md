---
layout: post
title: Expand Nested Properties in WPF PropertyGrid control | Syncfusion
description: Learn about expanding nested properties of selected object in Syncfusion WPF PropertyGrid control and more details.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Expand Nested Properties in PropertyGrid

The [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control has support to expand instance properties of a class which has [ExpandableObjectConverter](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.expandableobjectconverter?view=netframework-4.8) as its [TypeConverter](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.typeconverter?view=netframework-4.8).

###  Navigate to the Inner Properties

The Users can choose whether the nested properties of the [SelectedObject](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~SelectedObject.html) can be expanded or not by using the [PropertyExpandMode](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~PropertyExpandMode.html) property. The Value of `PropertyExpandMode` are `NestedMode` and `FlatMode`.  By setting the `PropertyExpandMode` as `NestedMode`, the nested properties of the `SelectedObject` can be expanded, and by setting the `PropertyExpandMode` as `FlatMode`, the `SelectedObject` is shown in flat mode. The Default value of `PropertyExpandMode` property is `FlatMode`.

### Tables for properties

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
PropertyExpandMode</td><td>
Gets or sets the PropertyExpandMode</td><td>
Dependency</td><td>
Enum</td></tr>
</table>
