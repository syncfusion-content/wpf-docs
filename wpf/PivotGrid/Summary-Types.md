---
layout: post
title: 13425-Summary-Types
description: 1.3.4.25 summary types
platform: wpf
control: PivotGridControl
documentation: ug
---

# Summary Types

PivotGrid summarizes the data for various datatypes by using the **SummaryType** enumerator. SummaryType should be defined while defining the PivotCalculation using **PivotComputationInfo** class to specify the type of the summary. It holds the following summary types.

* **DoubleTotalSum** - Computes the sum of double or integer from PivotValues for corresponding PivotItem
* **DoubleAverage** - Computes average of double or integer from PivotValues for corresponding PivotItem.
* **DoubleMaximum** - Computes maximum of double or integer from PivotValues for corresponding PivotItem.
* **DoubleMinimum** - Computes Minimum of double or integer from PivotValues for corresponding PivotItem.
* **DoubleStandardDeviation** - Computes the standard deviation of double or integer from PivotValues for corresponding PivotItem.
* **DoubleVariance** - Computes the variance of double or integer from PivotValues
* **Count** - Computes count of double or integer from PivotValues for corresponding PivotItem.
* **DecimalTotalSum** - Computes the sum of decimal from PivotValues
* **IntTotalSum** - Computes the sum of integer from PivotValues for corresponding PivotItem.
* **Custom** - Specifies that you are using a custom SummaryBase object to define the calculation.
* **DisplayIfDiscreteValuesEqual** - Displays the aggregated value in the Pivot Computation column if all the values are common.


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
SummaryType</td><td>
Gets or sets the summary type to the PivotComputationInfo.</td><td>
SummaryType</td><td>
DoubleTotalSum, DoubleAverage, DoubleMaximum, DoubleMinimum, DoubleStandardDeviation, 
DoubleVariance, Count, DecimalTotalSum, IntTotalSum, Custom, DisplayIfDiscreteValues</td>
<td>-</td></tr>
</table>

## Defining the property in PivotGrid

**SummaryType** is the property can be set for the corresponding PivotCalculation item through **PivotComputationInfo** class. It can be set either through *XAML* or through *Code-Behind*.

If through **XAML**, please refer the below code snippet.

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

**DisplayIfDiscreteValuesEqual** is a new summary type that has been added to the **SummaryType** enumerator of the Pivot Grid control. This summary type displays the aggregated value in the Pivot Calculation column if all the values are common, else the default value will be displayed as **'*'**.
It is also possible to change the default value to any custom string of your choice by using the **PadString** property. 

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
PadString</td><td>
Gets or sets the PadString for the discrete value in numeric format to display.</td><td>
string</td><td>
* (default)</td><td>
-</td></tr>
</table>

### Defining DisplayIfDiscreteValuesEqual SummaryType with PadString in PivotGrid 

Set the SummaryType as **DisplayIfDiscreteValuesEqual** along with value for the **PadString** while defining PviotCalculations in PivotGrid control.

If setting these properties through **XAML**, please refer the below code snippet.

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

Else if setting these properties through **Code-Behind**, please refer the below code snippet.

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



