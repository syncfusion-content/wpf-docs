---
layout: post
title: Grouping and Sorting | custom order | PropertyGrid  | wpf | Syncfusion
description: grouping and sorting
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Grouping and Sorting

PropertyGrid groups the properties based on Category Attribute of the property and you can also sort the properties in both ascending and descending order. Sorting will be done based on the SortDirection property of the PropertyGrid control.

## Using grouping and sorting in an application

You can change the Sorting order by setting the SortDirection property. 

When you click the SortButton in PropertyGrid, the properties in PropertyGrid will be sorted automatically based on the SortDirection property. Properties will be sorted based on the `Name` of the property, not by `DisplayName`

If the `SortDirection` is null and the properties doesn't have any custom order then the properties will be arranged based on the order they were added in the property items collection of PropertyGrid. Otherwise, the properties will be arranged based on the order specified in each property of the DisplayAttribute.

When you click the GroupButton, then the properties will be displayed by grouping based on the Category Attribute of the property.

### Properties

Grouping and Sorting Table

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
EnableGrouping</td><td>
Groups between the group mode and the sort mode.</td><td>
DependencyProperty</td><td>
Bool</td><td>
</td></tr>
<tr>
<td>
SortDirection</td><td>
Gets or sets the SortDirection for the PropertyGrid control.</td><td>
DependencyProperty</td><td>
Nullable ListSortDirection</td><td>
</td></tr>
</table>

#### Sample link

1. Select Start -> Programs -> Syncfusion -> Essential Studio xx.x.x.xx -> Dashboard.
2. Select   Run Locally Installed Samples in WPF Button.
3. Now expand the PropertyGrid treeview item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 