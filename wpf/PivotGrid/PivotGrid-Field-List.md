---
layout: post
title: 13419-PivotGrid-Field-List
description: 1.3.4.19 pivotgrid field list
platform: wpf
control: PivotGridControl
documentation: ug
---

# PivotGrid Field List

With the current implementation of Grouping bar, we cannot able to add the deleted items in PivotGrid. The delete operation can be easily performed in the GroupingBar by using the AllowRemoving feature, but there is no possiblity to add again the deleted items. In order to achive this, we maintain a separate window called **PivotTable Field List** window, which holds the fields which are not present in the PivotGrid but available in the Item Source. We can bound a collection of PivotItems as **PivotFields** which gets included in the Field List window but not present in the PivotGrid. 

**Use Case Scenarios**

It will be useful for applications that need to configure PivotGrid at run-time. That is, to add/remove items to/from PivotGrid at run-time.

                                                      Property Table

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type</th><th>
Value it Accepts</th><th>
Reference link</th></tr>
<tr>
<td>
ShowFieldList</td><td>
Gets or Sets a value indication whether to show or hide the PivotGridFieldList window.</td><td>
bool</td><td>
True(Default), False</td><td>
 -</td></tr>
</table>
                                       
## PivotTable Field List window in PivotGrid

PivotTable Field List (or Dynamic Field List) can be launched by setting the **ShowFieldList** property to true or by clicking on the ShowFieldList menu item of Grouping bar context menu. Field List is bound to PivotFields property of PivotGridControl, which is a collection of PivotItems.This property can either be set through *XAML* or *Code-Behind*.

If through **XAML**, please refer the below code snippet.

{% highlight xaml %}

<Grid>
    <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" ShowFieldList="True" ItemSource="{Binding   Source={StaticResource data}}">

        <syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotItem FieldHeader="Product" FieldMappingName="Product" TotalHeader="Total" />
            <syncfusion:PivotItem FieldHeader="Date" FieldMappingName="Date" TotalHeader="Total" />
        </syncfusion:PivotGridControl.PivotRows>
        <syncfusion:PivotGridControl.PivotColumns>
            <syncfusion:PivotItem FieldHeader="Country" FieldMappingName="Country" TotalHeader="Total" />
            <syncfusion:PivotItem FieldHeader="State" FieldMappingName="State" TotalHeader="Total" />
        </syncfusion:PivotGridControl.PivotColumns>
        <syncfusion:PivotGridControl.PivotCalculations>
            <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Amount" Format="C" SummaryType="DoubleTotalSum" />
            <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Quantity" SummaryType="Count" />
        </syncfusion:PivotGridControl.PivotCalculations>

    </syncfusion:PivotGridControl>
</Grid>

{% endhighlight %}

Else if through **Code-Behind**, please refer the below code snippet.

{% highlight C# %}

public partial class MainWindow: Window {
    PivotGridControl pivotGrid = new PivotGridControl();
    public MainWindow() {
        InitializeComponent();
        grid1.Children.Add(pivotGrid);
        pivotGrid.ItemSource = ProductSales.GetSalesData();
        PivotItem m_PivotItem = new PivotItem() {
            FieldHeader = "Product", FieldMappingName = "Product", TotalHeader = "Total"
        };
        PivotItem m_PivotItem1 = new PivotItem() {
            FieldHeader = "Date", FieldMappingName = "Date", TotalHeader = "Total"
        };
        PivotItem n_PivotItem = new PivotItem() {
            FieldHeader = "Country", FieldMappingName = "Country", TotalHeader = "Total"
        };
        PivotItem n_PivotItem1 = new PivotItem() {
            FieldHeader = "State", FieldMappingName = "State", TotalHeader = "Total"
        };
        // Adding PivotItem to PivotRows
        pivotGrid.PivotRows.Add(m_PivotItem);
        pivotGrid.PivotRows.Add(m_PivotItem1);
        // Adding PivotItem to PivotColumns
        pivotGrid.PivotColumns.Add(n_PivotItem);
        pivotGrid.PivotColumns.Add(n_PivotItem1);
        PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() {
            CalculationName = "Amount", FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);

        pivotGrid.ShowFieldList = true;
    }
}

{% endhighlight %}

![](PivotGridFieldlist-images/PivotGrid Shows Field List.png)

