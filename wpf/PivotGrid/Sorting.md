---
layout: post
title: 1342-GroupinBar-Sorting
description: 1.3.4.2 sorting
platform: wpf
control: PivotGridControl
documentation: ug
---

# Sorting

Sorting enables you to quickly visualize and understand your data better, organize, find the data that you want and ultimately make more effective decisions. By default, PivotGrid holds built-in Comparers for all datatypes so that it will populate the data in ascending order according to its datatype. You can also define your own CustomComparer in order to view the data in your respective Sorting order.

## Sorting using Custom Comparer 
Sorting the data with your own CustomComparer can be achieved by defining your **CustomComparer** and initializing its instance to the **Comparer** of corresponding **PivotItem**

For example, we defined a custom **ReverseOrderComparer** for the PivotItems. Please find the CustomComparer code snippet below.

{% highlight C# %}
   
/// <summary>
/// Reverse Order Comparer for Descending sort order
/// </summary>
public class ReverseOrderComparer: IComparer {
    public int Compare(object x, object y) {
        if (x == null && y == null)
            return 0;
        else if (y == null)
            return 1;
        else if (x == null)
            return -1;
        else
            return -x.ToString().CompareTo(y.ToString());
    }
}

{% endhighlight %}

In order to apply this comparer to PivotItem, we have created the instance for the **ReverseOrderComparer** and assigned it to the Comparer property of **Product** PivotItem. Please refer the below code snippet.

{% highlight C# %}

public MainWindow() {
    InitializeComponent();
    this.Loaded += MainWindow_Loaded;
}

void MainWindow_Loaded(object sender, RoutedEventArgs e) {
    PivotGridControl pivotGrid = new PivotGridControl();
    grid1.Children.Add(pivotGrid);
    PivotItem m_PivotItem = new PivotItem() {
        FieldHeader = "Product", FieldMappingName = "Product", TotalHeader = "Total", Comparer = new ReverseOrderComparer()
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
}
  
{% endhighlight %}

![](Sorting Images/Not Sorted PivotGrid.png)

_PivotGrid without ReverseOrderComparer_

![](Sorting Images/Sorted PivotGrid.png)

_PivotGrid with ReverseOrderComparer_

## Sorting Events

PivotGrid provides certain sorting events to keep track of the sorted value fields which could be invoked before and after the sort actions.

* SortBegin - An event that notifies before the sorting action begins and returns the index or position of value fields with its corresponding values in PivotGrid.
* SortCompleted - An event that notifies after the sort option completed and returns the index or position of the sorted value fields with its corresponding values in PivotGrid.

** Using the SortBegin and SortCompleted Events **

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

