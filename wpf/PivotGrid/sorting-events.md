---
layout: post
title: 1342-GroupinBar-Sorting-events
description: 1.3.4.2 sorting events
platform: wpf
control: PivotGridControl
documentation: ug
---

# Sorting Events

PivotGrid provides certain sorting events to keep track of the sorted value fields which could be invoked before and after the sort actions.

* **SortBegin** - An event that notifies before the sorting action begins and returns the index or position of value fields with its corresponding values in PivotGrid.
* **SortCompleted** - An event that notifies after the sort option completed and returns the index or position of the sorted value fields with its corresponding values in PivotGrid.

**Using the SortBegin and SortCompleted Events**

We could make use of this mentioned events by invoking them whenever we want as per our requirement. Please refer the below guidelines and code snippets.

Create a new PivotGrid, bind the Itemsource and define the PivotItems and PivotComputations. Invoke the **SortBegin** and **SortCompleted** events and then we could save the indexes to a separate list  as illustrated below.

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
        CalculationName = "Quanity", FieldName = "Quanity", SummaryType = SummaryType.Count
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

