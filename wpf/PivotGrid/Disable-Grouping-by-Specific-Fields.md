---
layout: post
title: Prevent Grouping of Specific Pivot Item | Syncfusion
description: Support to prevent the drag and drop of certain pivot items in the pivot schema designer or grouping bar.
platform: wpf
control: Pivot grid
documentation: ug
---

# Prevent Grouping of Specific Pivot Item

The pivot grid control allows preventing the drag and drop of certain pivot items in the pivot schema designer or grouping bar.

**AllowRunTimeGroupByField**

You can prevent the grouping (i.e., drag and drop) for specific pivot item using the `AllowRunTimeGroupByField` property. It can be defined both in XAML and code-behind.

**ShowDisabledGroupBackground**

You can provide enabled or disabled background color for corresponding grouping bar item that prevents grouping using the `ShowDisabledGroupBackground` property of the pivot item. It can be defined both in XAML and code-behind.

If setting both the properties through XAML, refer to the following code sample.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" ShowDisabledGroupBackground="True" ItemSource="{Binding   Source={StaticResource data}}">
            <syncfusion:PivotGridControl.PivotRows>
                <syncfusion:PivotItem FieldHeader="Product" FieldMappingName="Product" TotalHeader="Total" AllowRunTimeGroupByField="False" />
                <syncfusion:PivotItem FieldHeader="Date" FieldMappingName="Date" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotGridControl.PivotColumns>
                <syncfusion:PivotItem FieldHeader="Country" FieldMappingName="Country" TotalHeader="Total" AllowRunTimeGroupByField="False" />
                <syncfusion:PivotItem FieldHeader="State" FieldMappingName="State" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotColumns>
            <syncfusion:PivotGridControl.PivotCalculations>
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Amount" Format="C" SummaryType="DoubleTotalSum" AllowRunTimeGroupByField="False" />
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Quantity" SummaryType="Count" />
            </syncfusion:PivotGridControl.PivotCalculations>
        </syncfusion:PivotGridControl>
    </Grid>

{% endhighlight %}

If setting both the properties through code-behind, refer to the following code sample.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        pivotGrid.ItemSource = ProductSales.GetSalesData();
        PivotItem m_PivotItem = new PivotItem() {
            FieldHeader = "Product", FieldMappingName = "Product", TotalHeader = "Total", AllowRunTimeGroupByField = false
        };
        PivotItem m_PivotItem1 = new PivotItem() {
            FieldHeader = "Date", FieldMappingName = "Date", TotalHeader = "Total"
        };
        PivotItem n_PivotItem = new PivotItem() {
            FieldHeader = "Country", FieldMappingName = "Country", TotalHeader = "Total", AllowRunTimeGroupByField = false
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
            CalculationName = "Amount", FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum, AllowRunTimeGroupByField = false;
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);
        // Enabling Disabled Background for Grouping disabled items.
        pivotGrid.ShowDisabledGroupBackground = true;

    }
}

{% endhighlight %}

![To disable the background color of specific grouping bar items](Grouping-Bar-Images/Grouping bar with disabled grouping fields.png)