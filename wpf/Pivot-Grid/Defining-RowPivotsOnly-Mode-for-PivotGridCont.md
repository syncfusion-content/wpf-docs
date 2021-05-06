---
layout: post
title: RowPivotsOnly Mode in WPF Pivot Grid control | Syncfusion
description: Learn about RowPivotsOnly Mode support in Syncfusion WPF Pivot Grid control and more.
platform: wpf
control: Pivot grid
documentation: ug
---

# RowPivotsOnly Mode in WPF Pivot Grid

RowPivotsOnly mode allows the pivot grid to display only the column values.

When displaying the pivot grid in RowPivotsOnly mode, it shows the row header cells and column header cells as value cells. Also, it supports column filtering, column sorting, and so on.

The `RowPivotsOnly` property is used to achieve this and it can be mentioned in XAML or code-behind.

For XAML, refer to the following code sample.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl Name="pivotGrid" RowPivotsOnly="True">

            <syncfusion:PivotGridControl.PivotRows>
                <syncfusion:PivotItem AllowFilter="False" FieldHeader="PID" FieldMappingName="PID" TotalHeader="Total" />
                <syncfusion:PivotItem AllowFilter="False" FieldHeader="Location" FieldMappingName="Location" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotGridControl.PivotCalculations>
                <syncfusion:PivotComputationInfo FieldHeader="Color" FieldName="Color" Format="0.0" SummaryType="DoubleTotalSum" />
                <syncfusion:PivotComputationInfo FieldHeader="Class" FieldName="Class" Format="0.0" SummaryType="DoubleTotalSum" />
                <syncfusion:PivotComputationInfo FieldHeader="PID" FieldName="PID" Format="0.0" SummaryType="DoubleTotalSum" />
                <syncfusion:PivotComputationInfo FieldHeader="Units" FieldName="Units" Format="0.0" SummaryType="DoubleTotalSum" />
                <syncfusion:PivotComputationInfo FieldHeader="Retail" FieldName="Retail" Format="0.0" SummaryType="DoubleTotalSum" />
                <syncfusion:PivotComputationInfo FieldHeader="Cost" FieldName="Cost" Format="0.0" SummaryType="DoubleTotalSum" />
                <syncfusion:PivotComputationInfo FieldHeader="TestStr" FieldName="TestStr" Format="0.0" PadString="***" SummaryType="DisplayIfDiscreteValuesEqual" />
                <syncfusion:PivotComputationInfo FieldHeader="TestInt" FieldName="TestInt" Format="0.0" PadString="***" SummaryType="DisplayIfDiscreteValuesEqual" />
                <syncfusion:PivotComputationInfo FieldHeader="TestDouble" FieldName="TestDouble" Format="0.00" PadString="***" SummaryType="DisplayIfDiscreteValuesEqual" />
            </syncfusion:PivotGridControl.PivotCalculations>
        </syncfusion:PivotGridControl>
    </Grid>

{% endhighlight %}

For code-behind, refer to the following code sample.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        pivotGrid.RowPivotsOnly = true;
    }
}

{% endhighlight %}

![RowPivotsOnly mode enabled in the pivotGrid](Features-in-RowPivotsOnly-images/PivotGrid when RowPivotsOnly mode is enabled.png)
