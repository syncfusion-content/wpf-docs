---
layout: post
title: Pivot Value Chooser in WPF Pivot Grid control | Syncfusion
description: Learn about Pivot Value Chooser support in Syncfusion WPF Pivot Grid control and more.
platform: wpf
control: Pivot grid
documentation: ug
---

# Pivot Value Chooser in WPF Pivot Grid

The pivot value chooser is used to list all the PivotFields available in the data source when the pivot grid is in RowPivotsOnly mode. This window enables users to select a PivotCalculation and add it to the pivot grid, drag and drop the PivotFields, and rearrange the calculation column in the pivot grid control at runtime.

* **ShowPivotValueChooser**: Hides or shows a computation value column chooser dialog that allows users to hide, show, or reorder the PivotCalculations in the pivot grid.
* **PossiblePivotCalculations**: Gets or sets a collection of possible PivotCalculations that may appear in the pivot grid control and lists them in the pivot value chooser.

## Pivot value chooser with possible calculation values

`PossiblePivotCalculations` is a collection where user can define which PivotFields should appear in the pivot value chooser window. If it is not defined, then this collection will be automatically generated PivotFields from the ItemSource of the pivot grid control.

After defining the pivot grid control in RowPivotsOnly mode, raise the loaded event of the pivot grid. Inside the `PivotGrid_Loaded()` event, set the `ShowPivotValueChooser` property to true and define an observable collection of PivotComputationInfo to `PossiblePivotCalculations`.

{% highlight C# %}

public partial class MainWindow: Window
{
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

## Pivot value chooser with all the default values

After defining the pivot grid control in RowPivotsOnly mode, raise the loaded event of the pivot grid. Inside the `PivotGrid_Loaded()` event, set the `ShowPivotValueChooser` property to true.

{% highlight C# %}

public partial class MainWindow: Window
{
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

![Pivot value chooser window](Features-in-RowPivotsOnly-images/PivotGrid shows Value chooser window.png)
