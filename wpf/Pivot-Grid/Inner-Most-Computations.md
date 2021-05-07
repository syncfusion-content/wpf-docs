---
layout: post
title: Display Innermost Computations in WPF Pivot Grid control | Syncfusion
description: Learn about Display Innermost Computations support in Syncfusion Essential Studio WPF Pivot Grid control, its elements and more details.
platform: wpf
control: Pivot grid
documentation: ug
---

# Display Innermost Computations in WPF Pivot Grid

The pivot grid supports displaying the grid with inner most computations alone without displaying the total values by using the `InnerMostComputationsOnly` property. It can be mentioned in XAML or code-behind.

For XAML, refer to the following code sample.

{% highlight xaml %}

<syncfusion:PivotGridControl Name="pivotGrid" RowPivotsOnly="True">

    <syncfusion:PivotGridControl.PivotRows>
        <syncfusion:PivotItem AllowFilter="False" FieldHeader="PID" FieldMappingName="PID" TotalHeader="Total" />
        <syncfusion:PivotItem AllowFilter="False" FieldHeader="Location" FieldMappingName="Location" TotalHeader="Total" />
    </syncfusion:PivotGridControl.PivotRows>
    <syncfusion:PivotGridControl.PivotCalculations>
        <syncfusion:PivotComputationInfo FieldHeader="Color" FieldName="Color" Format="0.0" SummaryType="DoubleTotalSum" InnerMostComputationsOnly="InnerMostOnly" />
        <syncfusion:PivotComputationInfo FieldHeader="Class" FieldName="Class" Format="0.0" SummaryType="DoubleTotalSum" InnerMostComputationsOnly="InnerMostOnly" />
        <syncfusion:PivotComputationInfo FieldHeader="PID" FieldName="PID" Format="0.0" SummaryType="DoubleTotalSum" InnerMostComputationsOnly="InnerMostOnly" />
        <syncfusion:PivotComputationInfo FieldHeader="Units" FieldName="Units" Format="0.0" SummaryType="DoubleTotalSum" InnerMostComputationsOnly="InnerMostOnly" />
        <syncfusion:PivotComputationInfo FieldHeader="Retail" FieldName="Retail" Format="0.0" SummaryType="DoubleTotalSum" InnerMostComputationsOnly="InnerMostOnly" />
        <syncfusion:PivotComputationInfo FieldHeader="Cost" FieldName="Cost" Format="0.0" SummaryType="DoubleTotalSum" InnerMostComputationsOnly="InnerMostOnly" />
        <syncfusion:PivotComputationInfo FieldHeader="TestStr" FieldName="TestStr" Format="0.0" PadString="***" SummaryType="DisplayIfDiscreteValuesEqual" InnerMostComputationsOnly="InnerMostOnly" />
        <syncfusion:PivotComputationInfo FieldHeader="TestInt" FieldName="TestInt" Format="0.0" PadString="***" SummaryType="DisplayIfDiscreteValuesEqual" InnerMostComputationsOnly="InnerMostOnly" />
        <syncfusion:PivotComputationInfo FieldHeader="TestDouble" FieldName="TestDouble" Format="0.00" PadString="***" SummaryType="DisplayIfDiscreteValuesEqual" InnerMostComputationsOnly="InnerMostOnly" />
    </syncfusion:PivotGridControl.PivotCalculations>

</syncfusion:PivotGridControl>

{% endhighlight %}

For code-behind, refer to the following code sample.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        pivotGrid.Loaded += pivotGrid_Loaded;
    }

    void pivotGrid_Loaded(object sender, RoutedEventArgs e) {
        // To define some PivotCalculations 
        // Setting the property value to InnerMost to all the defined PivotCalculations
        for (int i = 0; i < pivotGrid.PivotCalculations.Count; i++)
            pivotGrid.PivotCalculations[i].InnerMostComputationsOnly = Syncfusion.PivotAnalysis.Base.SummaryDisplayLevel.InnerMostOnly;
    }
}

{% endhighlight %}

![Displaying the pivot grid without total values](Features-in-RowPivotsOnly-images/Innermost Computation only in PivotGrid.png)
