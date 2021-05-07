---
layout: post
title: Setting Caption in PivotTableFieldList in WPF Pivot Grid control | Syncfusion
description: Learn about Setting Caption in PivotTableFieldList support in Syncfusion Essential Studio WPF Pivot Grid control, its elements and more details.
platform: wpf
control: Pivot grid
documentation: ug
---

# Setting Caption in PivotTableFieldList in WPF Pivot Grid

The pivot grid supports duplicating the same fields in different names. This can be achieved by using the `FieldCaption` property of PivotItem and PivotComputationInfo. This support allows you to define multiple items in same underlying type for the pivot grid control.

The following code sample illustrates how to set the field caption for PivotItem and PivotComputationInfo.

{% tabs %}

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" FreezeHeaders="False" VerticalAlignment="Top" VisualStyle="Metro" ItemSource="{Binding   Source={StaticResource data}}">
        <syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotItem FieldMappingName="Product" FieldCaption="Product_1" TotalHeader="Total"/>
            <syncfusion:PivotItem FieldMappingName="Product" FieldCaption="Product_2" TotalHeader="Total"/>
            <syncfusion:PivotItem FieldMappingName="Date" FieldHeader="Date" FieldCaption="Date" TotalHeader="Total"/>
        </syncfusion:PivotGridControl.PivotRows>
        <syncfusion:PivotGridControl.PivotColumns>
            <syncfusion:PivotItem FieldMappingName="Country" FieldHeader="Country" FieldCaption="Country" TotalHeader="Total"/>
            <syncfusion:PivotItem FieldMappingName="State" FieldHeader="State" FieldCaption="State" TotalHeader="Total"/>
        </syncfusion:PivotGridControl.PivotColumns>
        <syncfusion:PivotGridControl.PivotCalculations>
            <syncfusion:PivotComputationInfo CalculationName="Total" Description="Summation of values" FieldName="Amount"  FieldCaption="Amount_1" Format="C" SummaryType="DoubleTotalSum"/>
            <syncfusion:PivotComputationInfo CalculationName="Total" Description="Summation of values" FieldName="Amount"  FieldCaption="Amount_2" Format="#,##" SummaryType="IntTotalSum"/>
            <syncfusion:PivotComputationInfo CalculationName="Total" Description="Summation of values" FieldName="Quantity" FieldCaption="Quantity" Format="#,##0"/>
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
            FieldCaption = "Product_1", FieldMappingName = "Product", TotalHeader = "Total"
        };
        PivotItem m_PivotItem1 = new PivotItem() {
            FieldCaption = "Product_2", FieldMappingName = "Product", TotalHeader = "Total"
        };
        PivotItem m_PivotItem2 = new PivotItem() {
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
        pivotGrid.PivotRows.Add(m_PivotItem2);
        // Adding PivotItem to PivotColumns
        pivotGrid.PivotColumns.Add(n_PivotItem);
        pivotGrid.PivotColumns.Add(n_PivotItem1);
        PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() {
            CalculationName = "Amount", FieldName = "Amount", FieldCaption = "Amount_1", Format = "C", SummaryType = SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Amount", FieldName = "Amount", FieldCaption = "Amount_2", Format="#,##", SummaryType = SummaryType.IntTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo2 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", Format="#,##0", SummaryType = SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo2);
    }
}

{% endhighlight %}

{% endtabs %}

![FieldCaption](Setting-caption-in-pivottablefieldlist-images/FieldCaption.png)
