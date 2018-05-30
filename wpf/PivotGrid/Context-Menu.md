---
layout: post
title: Context Menu
description: Context menu
platform: wpf
control: Pivot grid
documentation: ug
---

# Context Menu

PivotGrid supports context menu option in Row Pivots Only mode. Following are the options available.

* **Allow Filtering** - Enable or disable filtering in the selected PivotComputation column.
* **Allow Sorting**  - Enable or disable sorting in the selected PivotComputation column.
* **HideValueColumn** - Hides the selected PivotComputation column.
* **ClearValueFilters** - To clear the filtered changes in all PivotComputation columns.
* **ClearValueSorts** - To clear sorted values in all PivotComputation columns.
* **ShowPivotValueChooser** - Launches the Pivot Value Chooser window to add or remove the items in PivotGrid.

The `EnableContextMenu` property is used to display the context menu on right clicking each column.

To do so, after defining PivotGrid control in RowPivotsOnly mode, raise the loaded event of PivotGrid. Inside the `PivotGrid_Loaded()` event, set the property `EnableContextMenu`.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        pivotGrid.Loaded += pivotGrid_Loaded;
    }

    void pivotGrid_Loaded(object sender, RoutedEventArgs e) {
        pivotGrid.RowHeaderCellStyle.EnableContextMenu = true;
        pivotGrid.ColumnHeaderCellStyle.EnableContextMenu = true;
    }
}

{% endhighlight %}

![](Features-in-RowPivotsOnly-images/PivotGrid shows Context menu.png)
