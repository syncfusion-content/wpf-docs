---
layout: post
title: 138-Skin-Customization
description: 1.3.8 skin customization
platform: wpf
control: PivotGridControl
documentation: ug
---

# Skin Customization

Skin Customization is the process of applying particular style settings to the visual elements of a product. PivotGrid provides the following skin customization options:

* Office 2010 Blue
* Office 2010 Black
* Office 2010 Silver
* Transparent
* Office 2007 Blue
* Office 2007 Black
* Office 2007 Silver
* Blend
* Metro
* Office 2003
* Default

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
VisualStyle</td><td>
Gets or Sets the VisualStyle of PivotGrid control.</td><td>
PivotGridVisualStyle</td><td>
Default (Default), Metro, Blend, Office2003, Office2007Black, Office2007Blue, Office2007Silver,Office2010Black, Office2010Blue, 
Office2010Silver, Transparent</td><td>
-</td></tr>
<tr>
</table>

## Defining the property in PivotGrid

The property **VisualStyle** can be mentioned either in *XAML* or *Code-Behind*.
 
 If through **XAML**, please refer the below code snippet.

{% highlight xaml %}

    <Grid>
            <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" 
                    VisualStyle="Office2010Blue" ItemSource="{Binding   Source={StaticResource data}}" >

            <syncfusion:PivotGridControl.PivotRows>
                <syncfusion:PivotItem FieldHeader="Product" FieldMappingName="Product" TotalHeader="Total" />
                <syncfusion:PivotItem FieldHeader="Date" FieldMappingName="Date" TotalHeader="Total"/>
            </syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotGridControl.PivotColumns>
                <syncfusion:PivotItem FieldHeader="Country" FieldMappingName="Country" TotalHeader="Total" />
                <syncfusion:PivotItem FieldHeader="State" FieldMappingName="State" TotalHeader="Total"/>
            </syncfusion:PivotGridControl.PivotColumns>
            <syncfusion:PivotGridControl.PivotCalculations>
                <syncfusion:PivotComputationInfo CalculationName = "Total" FieldName = "Amount" Format="C" SummaryType="DoubleTotalSum" />
                <syncfusion:PivotComputationInfo CalculationName = "Total" FieldName = "Quantity" SummaryType="Count" />
            </syncfusion:PivotGridControl.PivotCalculations>
        </syncfusion:PivotGridControl>            
    </Grid>

{% endhighlight %}

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

        pivotGrid.VisualStyle = PivotGridVisualStyle.Office2010Blue;
    }
}

{% endhighlight %}

![](Skin-Customization-Images/PivotGrid shows customized visual style.png)

