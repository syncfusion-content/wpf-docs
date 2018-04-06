---
layout: post
title: Sub-total-Hiding
description: sub-total hiding
platform: wpf
control: PivotGrid
documentation: ug
---

# Grand Total Row Visibility

PivotGrid provides support to make the grand total row always visible in RowPivotsOnly mode.

It can be achieved by using the `GrandTotalRowAlwaysVisible` property of PivotGrid control. This property can be defined either in *XAML* or *Code-behind*.

If through *XAML*, please refer the below code sample.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl Name="pivotGrid" GrandTotalRowAlwaysVisible="True" RowPivotsOnly="True">
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

Else if through *Code-behind*, please refer the below code sample.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        pivotGrid.GrandTotalRowAlwaysVisible = true;
    }
}

{% endhighlight %}

![](GrandTotalRows-always-visible-images/PivotGrid shows the GrandTotals at all the times.png)