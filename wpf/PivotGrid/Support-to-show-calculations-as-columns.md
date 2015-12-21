---
layout: post
title: Support to show calculations as columns.
description: 1.3.20.10 Support to show calculations as columns.
platform: wpf
control: PivotGridControl
documentation: ug
---

# Support to show calculations as columns

PivotGrid provides support to show the calculation values in columns or in rows and it can be achieved either by using the property **ShowCalculationsAsColumns** of PivotGrid control or by uncheck/check the **ShowCalculationsAsColumns** check box of PivotSchemaDesigner.

**Use Case Scenarios**

It enables the user display the values in columns or rows as per their requirement.

Property Table
<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Value It Accepts</th><th>
Reference Link</th></tr>
<tr>
<td>
ShowCalculationsAsColumns</td><td>
Gets or sets the value whether to display the values as columns.</td><td>
bool</td><td>
True(Default), False</td><td>
-</td></tr>
</table>

## Defining the property in PivotGrid

The **ShowCalculationsAsColumns** property of PivotGrid control can be mentioned either in *XAML* and *Code-Behind*.

If through **XAML**, please refer the below code snippet.

{% highlight xaml %}

<Grid>
    <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" FreezeHeaders="False" VerticalAlignment="Top" VisualStyle="Metro" ShowCalculationsAsColumns="False" ItemSource="{Binding   Source={StaticResource data}}">

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

Else if through **Code-Snippet**, please refer the below code snippet.

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

        pivotGrid.ShowCalculationsAsColumns = false;
    }
}     
	 
{% endhighlight %}

## Setting ShowCalculationsAsColumns property through PivotSchemaDesigner

We can enable or disable the ShowCalculationsAsColumns property through the ShowCalculationsAsColumns checkbox of PivotSchemaDesigner. Uncheck the ShowCalculationsAsColumns check box in order to view the calculations values in rows.

![](PivotSchemaDesigner-Images/Layout section.png)

_ShowCalculationsAsColumns checkbox in PivotSchemaDesigner_

![](PivotSchemaDesigner-Images/PivotGrid displays the values as rows.png)

_ PivotGrid displays the calculation values as rows_
