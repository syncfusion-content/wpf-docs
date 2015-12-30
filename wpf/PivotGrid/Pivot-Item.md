---
layout: post
title: 131-Pivot-Item
description: 1.3.1 pivot item
platform: wpf
control: PivotGridControl
documentation: ug
---

# Pivot Item

A **PivotItem** is a container for items in PivotGrid control. An item in a PivotTable field which provides the information needed to define an item. The items are individual data entries in a field category. The PivotItem object is a member of PivotItems collection. It consists of the following fields.

Properties Table

<table>
<tr>
<th>
Property Name</th><th>
Description</th><th>
Data Type</th><th>
Value it Accepts</th><th>
Reference link</th></tr>
<tr>
<td>
FieldHeader</td><td>
Gets or sets the title you want to see in the header for this PivotItem.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FieldMappingName</td><td>
Gets or sets the property's mapping name for the PivotItem.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
TotalHeader</td><td>
Gets or sets the string you want appended to the pivotItem's summary cells.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Comparer</td><td>
Gets or sets the IComparer object used for sorting. If this value is null, then sorting will be performed under the assumption that this field is IComparable.</td><td>
IComparer</td><td>
-</td><td>
-</td>
</tr>
<tr>
<td>
Format</td><td>
Gets or sets the format item for the specified field.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
ShowSubTotal</td><td>
Gets or sets whether the subtotal for this item can be shown or hidden.</td><td>
bool</td><td>
True(Default), False</td><td>
-</td></tr>
<tr>
<td>
AllowRunTimeGroupByField</td><td>
Gets or sets the value to enable/disable grouping for this PivotItem.</td><td>
bool</td><td>
True(Default), False</td><td>
-</td></tr>
<tr>
<td>
AllowFilter</td><td>
Gets or sets whether enable or disable the filter for PivotItem</td><td>
bool</td><td>
True(Default), False</td><td>
-</td></tr>
<tr>
<td>
AllowSort</td><td>
Gets or sets whether enable or disable the sort for PivotItem.</td><td>
bool</td><td>
True(Default), False</td><td>
-</td></tr>
</table>

## Defining Pivot Item in XAML

Create a new PivotItem by using the **PivotGridControl.PivotItem** class. A PivotItem can be either a **PivotRow** or **PivotColumn**.
Please refer the code snippet below.

{% highlight xaml %}

<Grid>
    <syncfusion:PivotGridControl Name="pivotGrid" HorizontalAlignment="Left" VerticalAlignment="Top" ItemSource="{Binding Source={StaticResource data}}" VisualStyle="Metro">

        <syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotItem FieldHeader="Product" FieldMappingName="Product" TotalHeader="Total" />
        </syncfusion:PivotGridControl.PivotRows>

        <syncfusion:PivotGridControl.PivotColumns>
            <syncfusion:PivotItem FieldHeader="Country" FieldMappingName="Country" TotalHeader="Total" />
        </syncfusion:PivotGridControl.PivotColumns>

    </syncfusion:PivotGridControl>
</Grid>
    
{% endhighlight %} 

## Defining Pivot Item in Code-Behind

Include the *Synfusion.PivotAnalysis.Base* in MainWindow.xaml.cs and then define the PivotItems for each row and column items. Add the defined PivotItems to PivotRows and PivotColumns collection of PivotGrid control. Please refer the below code snippet.

{% highlight C# %}

public MainWindow() {
    InitializeComponent();
    this.Loaded += MainWindow_Loaded;
}
void MainWindow_Loaded(object sender, RoutedEventArgs e) {
    PivotGridControl pivotGrid = new PivotGridControl();
    PivotItem m_PivotItem = new PivotItem() {
        FieldHeader = "Product", FieldMappingName = "Product", TotalHeader = "Total"
    };
    PivotItem n_PivotItem = new PivotItem() {
        FieldHeader = "Country", FieldMappingName = "Country", TotalHeader = "Total"
    };
    // Adding PivotItem to PivotRows
    pivotGrid.PivotRows.Add(m_PivotItem);
    // Adding PivotItem to PivotColumns
    pivotGrid.PivotColumns.Add(n_PivotItem);
}

{% endhighlight %}	

