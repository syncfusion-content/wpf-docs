---
layout: post
title: 1357-Pivot-Value-Chooser
description:  1.3.5.7 pivot value chooser
platform: wpf
control: PivotGridControl
documentation: ug
---

# Pivot Value Chooser

**Pivot Value Chooser** is used to list all the PivotFields in the data source when the pivot grid is in RowPivotsOnly mode. This window enables users to select a PivotCalculation and add it to the PivotGrid, drag and drop the grid fields, and rearrange the calculation column in the PivotGrid control at run time.

**Use Case Scenario**

It enables user to show or hide particular PivotCalculation in the PivotGrid at run time.

Properties Table

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
ShowPivotValueChooser</td><td>
Hides or shows a computation value column chooser dialog that allows users to hide, show, or reorder the PivotCalculations in the PivotGrid.</td><td>
bool</td><td>
True, False(Default)</td><td>
-</td></tr>
<tr>
<td>
PossiblePivotCalculations</td><td>
Gets or sets a collection of possible pivot calculations that may appear in the PivotGrid control and lists them in the PivotValueChooser.</td><td>
OservableCollection(PivotComputationInfo)</td><td>
-</td><td>
-</td></tr>
</table>

## Using the Pivot Value Chooser in PivotGrid

###Pivot value chooser with possible calculation values

**PossiblePivotCalculations** is a collection where users can define which fields should appear in the Pivot Value Chooser window. If it is not defined, then this collection will be automatically generated from the Itemsource of PivotGrid control.

After defining PivotGrid control in RowPivotsOnly mode, raise the Loaded event of PivotGrid. Inside the PivotGrid_Loaded() event, set the property **ShowPivotValueChooser** and define a observable collection of PivotComputationInfo to **PossiblePivotCalculations**.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        pivotGrid.Loaded += pivotGrid_Loaded;
    }

    void pivotGrid_Loaded(object sender, RoutedEventArgs e) {
        ObservableCollection < PivotComputationInfo > possibleComputations = new ObservableCollection < PivotComputationInfo > () {
            //Add computation collection.
        };
        pivotGrid.PossiblePivotCalculations = possibleComputations;
        pivotGrid.RowPivotsOnly = true;
        pivotGrid.ShowPivotValueChooser = true;
    }
}

{% endhighlight %}

### Showing the Pivot value chooser with all the default values

After defining PivotGrid control in RowPivotsOnly mode, raise the Loaded event of PivotGrid. Inside the PivotGrid_Loaded() event, set the property **ShowPivotValueChooser**.

Please refer the below code snippet.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        pivotGrid.Loaded += pivotGrid_Loaded;
    }

    void pivotGrid_Loaded(object sender, RoutedEventArgs e) {
        pivotGrid.RowPivotsOnly = true;
        pivotGrid.ShowPivotValueChooser = true;
    }
}

{% endhighlight %}

![](Features-in-RowPivotsOnly-images/PivotGrid shows Value chooser window.png)
