---
layout: post
title: 1342-GroupinBar-Sorting
description: 1.3.4.2 sorting
platform: wpf
control: PivotGridControl
documentation: ug
---

# Sorting

Sorting enables you to quickly visualize and understand your data better, organize, find the data that you want and ultimately make more effective decisions. By default, PivotGrid holds built-in Comparers for all data types so that it will populate the data in ascending order according to its data type. You can also define your own CustomComparer in order to view the data in your respective Sorting order.

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

![](Sorting-Images/Not Sorted PivotGrid.png)

_PivotGrid without ReverseOrderComparer_

![](Sorting-Images/Sorted PivotGrid.png)

_PivotGrid with ReverseOrderComparer_

