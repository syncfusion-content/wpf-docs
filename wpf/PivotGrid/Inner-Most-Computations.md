---
layout: post
title: 1355-Inner-Most-Computations
description: 1.3.5.5 inner most computations
platform: wpf
control: PivotGridControl
documentation: ug
---

# Inner Most Computations

Pivotgrid provides the support for the columns which are existing in engine to display only the calculation columns other than total and grand total columns.

** Use Case Scenario **

User could view only the calculation columns irrespective of viewing all the columns as per their requirement.

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
InnerMostComputationsOnly</td><td>
This property is used to display the grid with inner most computations only and without displaying the total values.</td><td>
SummaryDisplayLevel</td><td>
All (Default), InnerMostOnly</td><td>
-</td></tr>
</table>



## Defining the property in PivotGrid 

The property **InnerMostComputationsOnly** can be mentioned either in *XAML* or in *Code-Behind*. 

If through **XAML**, please refer the below code snippet.

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

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        pivotGrid.Loaded += pivotGrid_Loaded;
    }

    void pivotGrid_Loaded(object sender, RoutedEventArgs e) {
        // To define some PivotCalculatios 
        // Setting the property value to InnerMost to all the defined PivotCalculations
        for (int i = 0; i < pivotGrid.PivotCalculations.Count; i++)
            pivotGrid.PivotCalculations[i].InnerMostComputationsOnly = Syncfusion.PivotAnalysis.Base.SummaryDisplayLevel.InnerMostOnly;
    }
}

{% endhighlight %}

![](Features in RowPivotsOnly/Innermost Computation only in PivotGrid.png)

