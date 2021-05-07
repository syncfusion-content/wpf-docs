---
layout: post
title: Context Menu in WPF Pivot Grid control | Syncfusion
description: Learn about Context Menu support in Syncfusion WPF Pivot Grid control, its elements and more.
platform: wpf
control: Pivot grid
documentation: ug
---

# Context Menu in WPF Pivot Grid

The pivot grid supports the context menu option in RowPivotsOnly mode. Following are the available options.

* **Allow Filtering**: Enables or disables filtering in the selected pivot computation column.
* **Allow Sorting**: Enables or disables sorting in the selected pivot computation column.
* **HideValueColumn**: Hides the selected pivot computation column.
* **ClearValueFilters**: Clears the filtered changes in all pivot computation columns.
* **ClearValueSorts**: Clears the sorted values in all pivot computation columns.
* **ShowPivotValueChooser**: Launches the pivot value chooser window to add or remove the items in pivot grid.

The `EnableContextMenu` property is used to display the context menu by right-clicking each column.

To do so, after defining the pivot grid control in RowPivotsOnly mode, raise the loaded event of pivot grid. Inside the `PivotGrid_Loaded()` event, set the `EnableContextMenu` property.

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

![Displaying the context menu](Features-in-RowPivotsOnly-images/PivotGrid shows Context menu.png)
