---
layout: post
title: 132-PivotComputationInfo
description: 1.3.2 pivotcomputationinfo
platform: wpf
control: PivotGridControl
documentation: ug
---

# PivotComputationInfo

PivotComputation holds the information needed for calculations that appear in a PivotGrid control. For each calculation, there is an associated PivotComputationInfo object that is added to the PivotCalculations collection. 


Properties 

* **CalculationName** - Gets or sets what is displayed in the PivotTable if more than one calculation is included in the PivotGrid.
* **Description** - Gets or sets the description of the calculation.
* **FieldName** - Gets or sets the name of the property to be used in this calculation.
* **FieldHeader** - Gets or sets the title you want to see in the header for this PivotItem.
* **Format** - Gets of sets the format string to be used, to format the calculation results in the PivotGrid.
* **Summary** - Gets or sets the SummaryBase object that is used to define this calculation. When you specify SummaryType.Custom, then you are required to set Summary to be an instance of your custom SummaryBase-derived object.
* **SummaryType** - Gets or sets the SummaryType enumeration for this calculation. You can set some enumeration value to the summary type, otherwise by default it is set as Count.
* **AllowRunTimeGroupByField** -Gets or sets the value to enable/disable grouping for this PivotItem.
* **DisplayOption** - Gets or sets the calculation values to be displayed in PivotGrid
* **CalculationType** - Gets or sets the CalculationType enumeration for this computation object. Used to define how to make the computational objects in PivotGrid visible.
* **AllowFilter** - Gets or sets whether this calculation column can be filtered when RowPivotsOnly is true in the PivotEngine.
* **AllowSort** - Gets or sets whether this calculation column can be sorted when RowPivotsOnly is true in the PivotEngine.
* **BaseItem** - Gets or sets the value of the BaseItem for calculations.
* **BaseField** - Gets or sets the Base Field value for calculations.
* **EnableHyperlinks** - Gets or sets whether this calculation column should be hyperlinked when RowPivotsOnly is true in the PivotEngine.
* **InnerMostComputationsOnly** - Gets or sets whether the aggregation results appear for only the innermost level.
* **PadString** - Gets or sets the PadString used when SummaryType is DisplayIfDiscreteValuesEqual.

## Defining PivotComputationInfo in XAML

Create a new PivotComputationInfo item by using the **PivotGridControl.PivotComputationInfo** class and it can be added to a **PivotCalculations** collection.

Please refer the code snippet below.

{% highlight xaml %}

<Grid>
    <syncfusion:PivotGridControl Name="pivotGrid" HorizontalAlignment="Left" Margin="131,131,0,0" VerticalAlignment="Top" Height="48" Width="117">
        <syncfusion:PivotGridControl.PivotCalculations>
            <syncfusion:PivotComputationInfo CalculationName="Total" FieldHeader="Quantity" FieldName="Quantity" SummaryType="Count" />
        </syncfusion:PivotGridControl.PivotCalculations>
    </syncfusion:PivotGridControl>
</Grid>

{% endhighlight%}

## Defining PivotComputationInfo in Code-Behind

Include the *Syncfusion.PivotAnalysis.Base* in MainWindow.xaml.cs and then define the PivotComputationInfo's for each calculation items. Add the defined PivotComputationInfo's to PivotCalculations collection of PivotGrid control. 

Please refer the below code snippet.

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


