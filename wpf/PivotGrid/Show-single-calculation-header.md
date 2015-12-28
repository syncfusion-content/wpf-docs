---
layout: post
title: Show Single Calculation Header
description: Show Single Calculation Header
platform: wpf
control: PivotGrid
documentation: ug
---

# Show Single Calculation Header

By default, PivotGrid will not show the calculation headers when there is only one PivotCalculation. Now we can able to show the calculation headers even when there is only one PivotCalculation by using **ShowSingleCalculationHeader** property of PivotGrid control.

Property Table

<table>
<tr>
<th>
Property Name</th><th>
Description</th><th>
Type</th><th>
Value it Accepts</th><th>
Reference Link</th></tr>
<tr>
<td>
ShowSingleCalculationHeader</td><td>
Gets or sets whether a calculation header row is visible when there is a single calculation.</td><td>
bool</td><td>
True, False(Default)</td><td>
-</td></tr>
</table>

## Defining the property in PivotGrid

This property can be mentioned in Code-Behind. Please refer the below code snippet.

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

        pivotGrid.PivotEngine.ShowSingleCalculationHeader = true;
    }
}
	 
{% endhighlight %}

![](Show-Single-calculation-header-images/PivotGrid shows single calculation header.png)



