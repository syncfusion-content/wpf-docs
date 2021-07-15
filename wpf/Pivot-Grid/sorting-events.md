---
layout: post
title: Sorting events | PivotGrid | Syncfusion
description: Support to keep tracking of the sorter value fields, which is invoked before and after the sort operation.
platform: wpf
control: Pivot grid
documentation: ug
---

# Sorting Events in WPF Pivot Grid Control

The pivot grid provides certain sorting events to keep track of the sorted value fields, which is invoked before and after the sort operation.

* **SortBegin**: An event that notifies before the sorting action begins and returns the index or position of value fields with its corresponding values in the pivot grid.
* **SortCompleted**: An event that notifies after the sort option is completed and returns the index or position of the sorted value fields with its corresponding values in the pivot grid.

**Using SortBegin and SortCompleted Events**

To do so, create a new pivot grid, bind the ItemSource, and then define the PivotItems and PivotComputations. Invoke the `SortBegin` and `SortCompleted` events and then save the indexes to a separate list as illustrated below.

{% highlight C# %}

public MainWindow() {
    InitializeComponent();
    this.Loaded += MainWindow_Loaded;
}
void MainWindow_Loaded(object sender, RoutedEventArgs e) {
    PivotGridControl pivotGrid = new PivotGridControl();
    grid1.Children.Add(pivotGrid);
    PivotItem m_PivotItem = new PivotItem() {
        FieldHeader = "Product", FieldMappingName = "Product", TotalHeader = "Total"
    };
    PivotItem m_PivotItem1 = new PivotItem() {
        FieldHeader = "Date", FieldMappingName = "Date", TotalHeader = "Total"
    };
    PivotItem n_PivotItem = new PivotItem() {
        FieldHeader = "Country", FieldMappingName = "Country", TotalHeader = "Total"
    };
    PivotItem n_PivotItem1 = new PivotItem() {
        FieldHeader = "State", FieldMappingName = "State", TotalHeader = "Total"
    };
    // Adding PivotItem to PivotRows
    pivotGrid.PivotRows.Add(m_PivotItem);
    pivotGrid.PivotRows.Add(m_PivotItem1);
    // Adding PivotItem to PivotColumns
    pivotGrid.PivotColumns.Add(n_PivotItem);
    pivotGrid.PivotColumns.Add(n_PivotItem1);
    PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() {
        CalculationName = "Amount", FieldName = "Amount", SummaryType = SummaryType.Count
    };
    PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
        CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.Count
    };
    pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
    pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);
    pivotGrid.ItemSource = ProductSales.GetSalesData();
    pivotGrid.SortBegin += pivotGrid_SortBegin;
    pivotGrid.SortCompleted += pivotGrid_SortCompleted;
}
void pivotGrid_SortCompleted(object sender, OnSortActionCompleted e) {
    Dictionary < int, object > indexesAfterSort = new Dictionary < int, object > ();
    indexesAfterSort = e.List;
}
void pivotGrid_SortBegin(object sender, OnSortActionStarted e) {
    Dictionary < int, object > indexesBeforeSort = new Dictionary < int, object > ();
    indexesBeforeSort = e.List;
}

{% endhighlight %}


N> You can refer to our [WPF Pivot Grid](https://www.syncfusion.com/wpf-controls/pivot-grid) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Pivot Grid example](https://github.com/syncfusion/wpf-demos) to knows how to organizes and summarizes business data and displays the result in a cross-table format.