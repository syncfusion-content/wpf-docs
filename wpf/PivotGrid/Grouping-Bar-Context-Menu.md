---
layout: post
title: 13432-Grouping-Bar-Context-Menu
description: 1.3.4.3.2 grouping bar context menu
platform: wpf
control: PivotGridControl
documentation: ug
---

# Grouping Bar Context Menu

The Grouping bar context menu consists of the following menu items:

* **Reload Data** - Refresh the Grid with the Current Item source
* **Show Field List** - Launches the PivotGrid Field List
* **Order** – It is used to change the position of the item present in the Grouping bar. It contains the following sub menu items:

   * Move to Beginning - Moves the current item to the first position
   * Move to Left - Moves the current item one step towards its left
   * Move to Right - Moves the current item one step towards its right
   * Move to End - Moves the current item to the last position
   * Smallest to Largest—Arranges the pivot fields based on the field header from first letter to the last.
   * Largest to Smallest—Arranges the pivot fields based on the field header from last letter to the first.
		 
* **Calculated field** - Used to add a new calculation field at run time.

**Use Case Scenario**

It is useful for applications related to Stock Market where the data will change from time to time and users can refresh the grid as per their requirement.

Property Table

<table>
<tr>
<th>
Property Name</th><th>
Description</th><th>
Type</th><th>
Value it Accepts</th><th>
Reference link</th></tr>
<tr>
<td>
DisableContextMenu</td><td>
Gets or sets whether to enable/disable the grouping bar context menu.</td><td>
bool</td><td>
True, False(Default)</td><td>
 -</td></tr>
</table>

##Defining Grouping bar context menu in PivotGrid

**DisableContextMenu**

By Default, the context menu is enabled for the all the areas in the Grouping Bar. **DisableContextMenu** property needs to be set individually for each area such as Row, Column, Data header area in Grouping Bar in order to disable its visibility. 

After defining the PivotGrid control, raise the Loaded event for PivotGrid. Inside the PivotGrid_Loaded() event, raise the Loaded event for Grouping Bar. Inside GroupingBar_Loaded() event, set the visiblity of **DisableContextMenu** of each header areas.

Please refer the below code snippet.

{% highlight C# %}

public partial class MainWindow: Window {
    PivotGridControl pivotGrid = new PivotGridControl();
    public MainWindow() {
        InitializeComponent();
        grid1.Children.Add(pivotGrid);
        pivotGrid.ItemSource = ProductSales.GetSalesData();
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
            CalculationName = "Amount", FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);

        pivotGrid.Loaded += pivotGrid_Loaded;
    }

    void pivotGrid_Loaded(object sender, RoutedEventArgs e) {
        pivotGrid.GroupingBar.Loaded += GroupingBar_Loaded;
    }

    void GroupingBar_Loaded(object sender, RoutedEventArgs e) {
        pivotGrid.GroupingBar.ColumnHeaderArea.DisableContextMenu = false;
        pivotGrid.GroupingBar.RowHeaderArea.DisableContextMenu = true;
        pivotGrid.GroupingBar.DataHeaderArea.DisableContextMenu = false;
    }
}

{% endhighlight %}

![](Grouping-Bar-Images/Grouping bar context menu.png)
