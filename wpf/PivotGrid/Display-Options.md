---
layout: post
title: 13424-Display-Options
description: 1.3.4.24 display options
platform: wpf
control: PivotGridControl
documentation: ug
---

# Display Options

PivotGrid control offers various display options such as **Calculations, Summary, Grand Totals, None, All** for the PivotComputationInfo to display calculation values in certain areas of PivotGrid by using the **DisplayOption** enumerator.

Property 
																	 										 
* **DisplayOption** - Gets or sets the calculation values to be displayed in PivotGrid.

##Defining the Display Option for PivotComputationInfo in PivotGrid

**DisplayOption** is the property can be set for the corresponding PivotCalculation item through **PivotComputationInfo** class. It can be set either through *XAML* or through *Code-Behind*.

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
            <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Amount" DisplayOption="Calculations" Format="C" SummaryType="DoubleTotalSum" />
            <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Quantity" DisplayOption="Summary" SummaryType="Count" />
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

It is used to display the calculation values in all the columns of the PivotGrid.

![](Display-options-Images/PivotComputationinfo using All option.png)

**Summary**

Data actually present in the PivotEngine but displays the calculation values only in the summary columns of the PivotGrid.

![](Display-options-Images/PivotComputationinfo using summary option.png)

**Calculations**

Data actually present in the PivotEngine but displays the calculation values only in the calculation columns other than summary and grand total of the PivotGrid.

![](Display-options-Images/PivotComputationinfo using Calculations option.png)

**GrandTotal**

Data actually present in the PivotEngine but displays the calculation values only in the grand total columns of the PivotGrid.

![](Display-options-Images/PivotComputationinfo using Grand Totals option.png)

**None**

Data actually present in the PivotEngine but hides all the calculation values in all the columns of the PivotGrid.

![](Display-options-Images/PivotComputationinfo using none option.png)

