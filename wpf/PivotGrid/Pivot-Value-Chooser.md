---
layout: post
title: Pivot Value Chooser
description: Pivot value chooser
platform: wpf
control: Pivot grid
documentation: ug
---

# Pivot Value Chooser

Pivot Value Chooser is used to list all the PivotFields available in the data source when the PivotGrid is in RowPivotsOnly mode. This window enables user to select a PivotCalculation and add it to the PivotGrid, drag and drop the PivotFields, and re-arrange the calculation column in the PivotGrid control at runtime.

* **ShowPivotValueChooser** - Hides or shows a computation value column chooser dialog that allows users to hide, show, or re-order the PivotCalculations in the PivotGrid.
* **PossiblePivotCalculations** - Gets or sets a collection of possible PivotCalculations that may appear in the PivotGrid control and lists them in the PivotValueChooser.

## Pivot value chooser with possible calculation values

`PossiblePivotCalculations` is a collection where user can define which PivotFields should appear in the Pivot Value Chooser window. If it is not defined, then this collection will be automatically generated PivotFields from the ItemSource of PivotGrid control.

After defining PivotGrid control in RowPivotsOnly mode, raise the loaded event of PivotGrid. Inside the `PivotGrid_Loaded()` event, set the property `ShowPivotValueChooser` to true and define an observable collection of PivotComputationInfo to `PossiblePivotCalculations`.

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

After defining PivotGrid control in RowPivotsOnly mode, raise the loaded event of PivotGrid. Inside the `PivotGrid_Loaded()` event, set the property `ShowPivotValueChooser` to true.

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

![](Features-in-RowPivotsOnly-images/PivotGrid shows Value chooser window.png)