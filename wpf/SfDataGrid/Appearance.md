---
layout: post
title: Appearance | SfDataGrid | WPF | Syncfusion
description: appearance
platform: wpf
control: SfDataGrid
documentation: ug
---

# Appearance

## Freeze Panes


This section explains you how to set Freeze panes in SfDataGrid. SfDataGrid provides support to Freeze rows and columns at the top and also at the bottom similar to Excel Freeze panes. To enable Freeze panes in SfDataGrid you have to use the following properties.

Properties Table

<table>
<tr>
<th>
Property Name</th><th>
Description</th></tr>
<tr>
<td>
FrozenRowsCount</td><td>
Gets or Sets the count of frozen rows in top of the DataGrid.</td></tr>
<tr>
<td>
FooterRowsCount</td><td>
Gets or Sets the count of frozen rows in footer of the DataGrid.</td></tr>
<tr>
<td>
FrozenColumnCount</td><td>
Gets or Sets the count of frozen columns in left side of the DataGrid.</td></tr>
<tr>
<td>
FooterColumnCount</td><td>
Gets or Sets the count of frozen columns in right side of the DataGrid</td></tr>
</table>


## Limitations:

1. FreezePanes is not supported in DetailsViewGrid.
2. FrozenRows is disabled when AllowFrozenGroupHeaders is set to True.
3. Count should be less than the view port size.

The following code example illustrates how to use FreezePanes support in SfDataGrid.



{% highlight xml %}






<syncfusion:SfDataGrid AllowGrouping="True"

                       ShowGroupDropArea="True"

                       FrozenColumnCount="1"

                       FooterColumnCount="2"

                       FrozenRowsCount="2"

                       FooterRowsCount="1"

                       AllowFrozenGroupHeaders="False"

                       ShowRowHeader="True">


{% endhighlight %}


The following screenshot displays the SfDataGrid with Freeze Panes support.



![WPF](Features_images/Features_img173.png)


DataGrid with Freeze panes

N>  * While grouping, the FrozenColumnCount denotes only the actual DataColumns instead of any indent columns. So that the Indent columns automatically froze when initializing the FrozenColumnCount. * Header and TableSummary rows that are frozen by default works regardless of the FrozenRowsCount and FooterRowsCount properties. * The count should be less than the number of rows or columns in view.
