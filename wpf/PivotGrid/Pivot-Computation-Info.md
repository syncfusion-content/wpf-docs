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


                                                       Properties Table

<table>
<tr>
<th>
Property Name</th><th>
Description</th><th>
Type</th><th>
Value it Accepts</th><th>
Reference link</th></tr>
<tr>
<td>
CalculationName</td><td>
Gets or sets what is displayed in the PivotTable if more than one calculation is included in the PivotGrid.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Description</td><td>
Gets or sets the description of the calculation.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FieldName</td><td>
Gets or sets the name of the property to be used in this calculation.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FieldHeader</td><td>
Gets or sets the title you want to see in the header for this PivotItem.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Format</td><td>
Gets of sets the format string to be used, to format the calculation results in the PivotGrid.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Summary</td><td>
Gets or sets the SummaryBase object that is used to define this calculation. When you specify SummaryType.Custom, then you are required to set Summary to be an instance of your custom SummaryBase-derived object.</td><td>
SummaryBase</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
SummaryType</td><td>
Gets or sets the SummaryType enumeration for this calculation. You can set some enumeration value to the summary type, otherwise by default it is set as Count.</td><td>
SummaryType</td><td>
DoubleTotalSum, DoubleAverage, DoubleMaximum, DoubleMinimum, DoubleStandardDeviation, DoubleVariance, Count, DecimalTotalSum, IntTotalSum, Custom, DisplayIfDiscreteValues</td><td>
<br>SummaryType</td></tr>
<tr>
<td>
AllowRunTimeGroupByField</td><td>
Gets or sets the value to enable/disable grouping for this PivotItem.</td><td>
bool</td><td>
True(Default), False</td><td>
-</td></tr>
<tr>
<td>
DisplayOption</td><td>
Gets or sets the calculation values to be displayed in PivotGrid</td><td>
DisplayOption</td><td>
None, Calculations, Summary, GrandTotals, All</td><td>
<br>DisplayOption</td></tr>
<tr>
<td>
CalculationType</td><td>
Gets or sets the CalculationType enumeration for this computation object. Used to define how to make the computational objects in PivotGrid visible.</td><td>
CalculationType</td><td>
NoCalculation, PercentageOfParentTotal, PercentageOfGrandTotal, PercentageOfColumnTotal, PercentageOfRowTotal, PercentageOfParentColumnTotal, PercentageOfParentRowTotal, Index, Formula, PercentageOf, DifferenceFrom, PercentageOfDifferenceFrom, RunningTotalIn, PercentageOfRunningTotalIn, RankLargestToSmallest, RankSmallestToLargest</td><td>
<br>CalculationType</td></tr>
<tr>
<td>
AllowFilter</td><td>
Gets or sets whether this calculation column can be filtered when RowPivotsOnly is true in the PivotEngine.</td><td>
bool</td><td>
True, False(Default)</td><td>
-</td></tr>
<tr>
<td>
AllowSort</td><td>
Gets or sets whether this calculation column can be sorted when RowPivotsOnly is true in the PivotEngine.</td><td>
bool</td><td>
True, False(Default)</td><td>
-</td></tr>
<tr>
<td>
BaseItem</td><td>
Gets or sets the value of the BaseItem for calculations.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
BaseField</td><td>
Gets or sets the Base Field value for calculations.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
EnableHyperlinks</td><td>
Gets or sets whether this calculation column should be hyperlinked when RowPivotsOnly is true in the PivotEngine.</td><td>
bool</td><td>
True, False(Default)</td><td>
-</td></tr>
<tr>
<td>
InnerMostComputationsOnly</td><td>
Gets or sets whether the aggregation results appear for only the innermost level. </td><td>
SummaryDisplayLevel</td><td>
All(Default), InnerMostOnly</td><td>
-</td></tr>
<tr>
<td>
PadString</td><td>
Gets or sets the PadString used when SummaryType is DisplayIfDiscreteValuesEqual.</td><td>
string</td><td>
'*'(Default)</td><td>
-</td></tr>
</table>

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

## Defining PivotComputationInfo in Code-Behind:

Include the *Synfusion.PivotAnalysis.Base* in MainWindow.xaml.cs and then define the PivotComputationInfo's for each calculation items. Add the defined PivotComputationInfo's to PivotCalculations collection of PivotGrid control. 

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


