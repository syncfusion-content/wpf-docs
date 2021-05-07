---
layout: post
title: Display Options in WPF Pivot Grid control | Syncfusion
description: Learn about Display Options support in Syncfusion WPF Pivot Grid control, its elements and more details.
platform: wpf
control: Pivot grid
documentation: ug
---

# Display Options in WPF Pivot Grid

The pivot grid control provides support for the PivotComputationInfo to display calculation values in preferred areas of the pivot grid using the `DisplayOption` property.

For XAML, refer to the following code sample.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" ItemSource="{Binding   Source={StaticResource data}}">
            <syncfusion:PivotGridControl.PivotRows>
                <syncfusion:PivotItem FieldHeader="Product" FieldMappingName="Product" TotalHeader="Total" />
                <syncfusion:PivotItem FieldHeader="Date" FieldMappingName="Date" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotGridControl.PivotColumns>
                <syncfusion:PivotItem FieldHeader="Country" FieldMappingName="Country" TotalHeader="Total" />
                <syncfusion:PivotItem FieldHeader="State" FieldMappingName="State" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotColumns>

            <syncfusion:PivotGridControl.PivotCalculations>
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Amount" DisplayOption="Calculations" Format="C" SummaryType="DoubleTotalSum" />
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Quantity" DisplayOption="Summary" SummaryType="Count" />
            </syncfusion:PivotGridControl.PivotCalculations>
        </syncfusion:PivotGridControl>
    </Grid>

{% endhighlight %}

For code-behind, refer to the following code sample.

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
            CalculationName = "Amount", FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum, DisplayOption = DisplayOption.Calculations
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.Count, DisplayOption = DisplayOption.Summary
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);
    }
}

{% endhighlight %}

**All**

Displays the calculation values in all columns of the pivot grid.

![To display the calculation values in all columns](Display-options-Images/PivotComputationinfo using All option.png)

**Summary**

Data actually presents in the PivotEngine, but displays the calculation values only in the summary columns of the pivot grid.

![To display the calculation values only in summary columns](Display-options-Images/PivotComputationinfo using summary option.png)

**Calculations**

Data actually presents in the PivotEngine, but displays the calculation values only in the calculation columns and does not display in the summary and grand total columns of the pivot grid.

![To display the calculation values only in calculation columns](Display-options-Images/PivotComputationinfo using Calculations option.png)

**GrandTotal**

Data actually presents in the PivotEngine, but displays the calculation values only in the grand total columns of the pivot grid.

![To display the calculation values only in grand total columns](Display-options-Images/PivotComputationinfo using Grand Totals option.png)

**None**

Data actually presents in the PivotEngine, but hides all the calculation values in all columns of the pivot grid.

![To hide the calculation values in all columns](Display-options-Images/PivotComputationinfo using none option.png)
