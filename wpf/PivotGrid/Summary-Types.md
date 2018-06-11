---
layout: post
title: Summary Types
description: Summary types
platform: wpf
control: Pivot grid
documentation: ug
---

# Summary Types

PivotGrid summarizes the data for various data types by using the `SummaryType` enumerator. SummaryType should be defined while defining the PivotCalculation using `PivotComputationInfo` class to specify the type of the summary. It holds the following summary types.

* **DoubleTotalSum** - Computes the sum of double or integer from PivotValues for corresponding PivotItem
* **DoubleAverage** - Computes average of double or integer from PivotValues for corresponding PivotItem.
* **DoubleMaximum** - Computes maximum of double or integer from PivotValues for corresponding PivotItem.
* **DoubleMinimum** - Computes minimum of double or integer from PivotValues for corresponding PivotItem.
* **DoubleStandardDeviation** - Computes the standard deviation of double or integer from PivotValues for corresponding PivotItem.
* **DoubleVariance** - Computes the variance of double or integer from PivotValues for corresponding PivotItem.
* **Count** - Computes count of double or integer from PivotValues for corresponding PivotItem.
* **DecimalTotalSum** - Computes the sum of decimal from PivotValues for corresponding PivotItem.
* **IntTotalSum** - Computes the sum of integer from PivotValues for corresponding PivotItem.
* **Custom** - Specifies that you are using a custom SummaryBase object to define the calculation.
* **DisplayIfDiscreteValuesEqual** - Displays the aggregated value in the Pivot Computation column if all the values are common.

`SummaryType` property can be set for the corresponding PivotCalculation item through `PivotComputationInfo` class. It can be set either through *XAML* or through *Code-behind*.

For *XAML*, refer to the following code sample.

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
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Amount" SummaryType="DoubleTotalSum" />
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Quantity" SummaryType="Count" />
            </syncfusion:PivotGridControl.PivotCalculations>
    </Grid>

{% endhighlight %}

For *Code-behind*, refer to the following code sample.

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
            CalculationName = "Amount", FieldName = "Amount", SummaryType = SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);
    }
}

{% endhighlight %}

![](Summary-Images/PivotGrid shows summary type Double variance.png)

## DisplayIfDiscreteValuesEqual SummaryType in PivotGrid

**DisplayIfDiscreteValuesEqual** is a new summary type that has been added to the `SummaryType` enumerator of the PivotGrid control. This summary type displays the aggregated value in the PivotCalculation column if all the values are common, else the default value will be displayed as **'*'**.
It is also possible to change the default value to any custom string of your choice by using the `PadString` property.

Set the SummaryType as **DisplayIfDiscreteValuesEqual** along with value for the `PadString` while defining PivotCalculations in PivotGrid control.

If setting these properties through *XAML*, please refer the below code sample.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" VisualStyle="Metro" ItemSource="{Binding   Source={StaticResource data}}">
            <syncfusion:PivotGridControl.PivotRows>
                <syncfusion:PivotItem FieldHeader="Product" FieldMappingName="Product" TotalHeader="Total" />
                <syncfusion:PivotItem FieldHeader="Date" FieldMappingName="Date" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotGridControl.PivotColumns>
                <syncfusion:PivotItem FieldHeader="Country" FieldMappingName="Country" TotalHeader="Total" />
                <syncfusion:PivotItem FieldHeader="State" FieldMappingName="State" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotColumns>
            <syncfusion:PivotGridControl.PivotCalculations>
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Amount" SummaryType="DoubleTotalSum" />
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Quantity" SummaryType="DisplayIfDiscreteValuesEqual" PadString="***" />
            </syncfusion:PivotGridControl.PivotCalculations>
        </syncfusion:PivotGridControl>
    </Grid>

{% endhighlight %}

Else if setting these properties through *Code-behind*, please refer the below code sample.

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
            CalculationName = "Amount", FieldName = "Amount", SummaryType = SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.DisplayIfDiscreteValuesEqual, PadString = "***"
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);
    }
}

{% endhighlight %}

![](Summary-Images/PivotGrid Shows DisplayIfDiscretevaluesequal summary type.png)