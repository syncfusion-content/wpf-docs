---
layout: post
title: PivotComputationInfo in WPF Pivot Grid control | Syncfusion
description: Learn about PivotComputationInfo support in Syncfusion Essential Studio WPF Pivot Grid control, its elements and more details.
platform: wpf
control: Pivot grid
documentation: ug
---

# PivotComputationInfo in WPF Pivot Grid

Pivot computation holds the information needed for calculations that appear in the pivot grid control. For each calculation, there is an associated `PivotComputationInfo` object added to the PivotCalculations collection.

Properties

* **CalculationName**: Gets or sets what needs to be displayed in the pivot table if more than one calculation is included in the pivot grid.
* **Description**: Gets or sets the description of the calculation.
* **FieldName**: Gets or sets the name of the property to be used in this calculation.
* **FieldHeader**: Gets or sets the title you want to view in the header.
* **Format**: Gets of sets the format string to be used, to format the calculation results in the pivot grid.
* **Summary**: Gets or sets the SummaryBase object used to define the calculation. When you specify SummaryType.Custom, set summary as an instance of your custom SummaryBase-derived object.
* **SummaryType**: Gets or sets the SummaryType enumeration for the calculation. You can set some enumeration values to the summary type; otherwise, by default it is set as count.
* **AllowRunTimeGroupByField**: Gets or sets the value to enable/disable grouping for the pivot item.
* **DisplayOption**: Gets or sets the calculation values to be displayed in pivot grid.
* **CalculationType**: Gets or sets the CalculationType enumeration for this computation object and defines how to make the computational objects in pivot grid visible.
* **AllowFilter**: Gets or sets whether the calculation column can be filtered when RowPivotsOnly is true in the PivotEngine.
* **AllowSort**: Gets or sets whether the calculation column can be sorted when RowPivotsOnly is true in the PivotEngine.
* **BaseItem**: Gets or sets the value of the BaseItem for calculations.
* **BaseField**: Gets or sets the base field value for calculations.
* **EnableHyperlinks**: Gets or sets whether the calculation column should be hyperlinked when RowPivotsOnly is true in the PivotEngine.
* **InnerMostComputationsOnly**: Gets or sets whether the aggregation results appear only for the innermost level.
* **PadString**: Gets or sets the PadString that is used when SummaryType is DisplayIfDiscreteValuesEqual.

## Defining PivotComputationInfo in XAML

Create a new PivotComputationInfo item using the `PivotGridControl.PivotComputationInfo` class and it can be added to a PivotCalculations collection.

Refer to the following code sample.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl Name="pivotGrid" HorizontalAlignment="Left" Margin="131,131,0,0" VerticalAlignment="Top" Height="48" Width="117">
            <syncfusion:PivotGridControl.PivotCalculations>
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldHeader="Quantity" FieldName="Quantity" SummaryType="Count" />
            </syncfusion:PivotGridControl.PivotCalculations>
        </syncfusion:PivotGridControl>
    </Grid>

{% endhighlight%}

## Defining PivotComputationInfo in code-behind

Include the *Syncfusion.PivotAnalysis.Base* in the MainWindow.xaml.cs file, and then define the PivotComputationInfo's for each calculation items. Add the defined PivotComputationInfo's to PivotCalculations collection of the pivot grid control.

Refer to the following code sample.

{% highlight C# %}

public MainWindow() {
    InitializeComponent();
    this.Loaded += MainWindow_Loaded;
}
void MainWindow_Loaded(object sender, RoutedEventArgs e) {
    PivotGridControl pivotGrid = new PivotGridControl();
    PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() {
        CalculationName = "Total", FieldName = "Quantity", FieldHeader = "Quantity", SummaryType = SummaryType.Count
    };
    pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
}

{% endhighlight %}
