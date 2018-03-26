---
layout: post
title: 131-Pivot-Item
description: 1.3.1 pivot item
platform: wpf
control: PivotGridControl
documentation: ug
---

# PivotItem

A PivotItem is a container for items in PivotGrid control. An item in a PivotTable field which provides the information needed to define an item. The items are individual data entries in a field category. The PivotItem object is a member of PivotItems collection. It consists of the following fields.

Properties:

* **FieldHeader** - Gets or sets the title you want to view in the header for this PivotItem.
* **FieldMappingName**- Gets or sets the property's mapping name for the PivotItem.
* **TotalHeader** - Gets or sets the string you want to appended to the PivotItem's summary cells.
* **Comparer** - Gets or sets the IComparer object used for sorting. If this value is null, then sorting will be performed under the assumption that this field is IComparable.
* **Format** - Gets or sets the format string for the specified field.
* **ShowSubTotal** - Gets or sets whether the sub-total for this item can be shown or hidden.
* **AllowRunTimeGroupByField** - Gets or sets the value to enable/disable grouping for this PivotItem.
* **AllowFilter** - Gets or sets whether to enable or disable filtering for the PivotItem.
* **AllowSort** - Gets or sets whether to enable or disable sorting for the PivotItem.

## Defining PivotItem in XAML

Create a new PivotItem by using the `PivotGridControl.PivotItem` class. A PivotItem can be either a `PivotRow` or `PivotColumn`. Please refer the code sample below.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl Name="pivotGrid" HorizontalAlignment="Left" VerticalAlignment="Top" ItemSource="{Binding Source={StaticResource data}}" VisualStyle="Metro">

            <syncfusion:PivotGridControl.PivotRows>
                <syncfusion:PivotItem FieldHeader="Product" FieldMappingName="Product" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotRows>

            <syncfusion:PivotGridControl.PivotColumns>
                <syncfusion:PivotItem FieldHeader="Country" FieldMappingName="Country" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotColumns>

        </syncfusion:PivotGridControl>
    </Grid>

{% endhighlight %}

## Defining Pivot Item in Code-Behind

Include the *Syncfusion.PivotAnalysis.Base* in MainWindow.xaml.cs and then define the PivotItem for row and column. Add the defined PivotItem to PivotRows and PivotColumns collection of PivotGrid control. Please refer the below code sample.

{% highlight C# %}

public MainWindow() {
    InitializeComponent();
    this.Loaded += MainWindow_Loaded;
}
void MainWindow_Loaded(object sender, RoutedEventArgs e) {
    PivotGridControl pivotGrid = new PivotGridControl();
    PivotItem m_PivotItem = new PivotItem() {
        FieldHeader = "Product", FieldMappingName = "Product", TotalHeader = "Total"
    };
    PivotItem n_PivotItem = new PivotItem() {
        FieldHeader = "Country", FieldMappingName = "Country", TotalHeader = "Total"
    };
    // Adding PivotItem to PivotRows
    pivotGrid.PivotRows.Add(m_PivotItem);
    // Adding PivotItem to PivotColumns
    pivotGrid.PivotColumns.Add(n_PivotItem);
}

{% endhighlight %}