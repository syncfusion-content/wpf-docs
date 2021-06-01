---
layout: post
title: PivotItem in WPF Pivot Grid control | Syncfusion
description: Learn about PivotItem support in Syncfusion Essential Studio WPF Pivot Grid control, its elements and more.
platform: wpf
control: Pivot grid
documentation: ug
---

# PivotItem in WPF Pivot Grid

A pivot item is a container for items in the pivot grid control. An item in a pivot table field provides the information needed to define an item. The items are individual data entries in a field category. The pivot item object is a member of the pivot items collection and consists of the following fields.

* **FieldHeader**: Gets or sets the title you want to view in the header for the pivot item.
* **FieldMappingName**: Gets or sets the pivot item property's mapping name.
* **TotalHeader**: Gets or sets the string you want to append to the pivot item's summary cells.
* **Comparer**: Gets or sets the IComparer object used for sorting. If this value is null, then sorting will be performed under the assumption that this field is IComparable.
* **Format**: Gets or sets the format string for the specified field.
* **ShowSubTotal**: Gets or sets whether the subtotal for this item can be shown or hidden.
* **AllowRunTimeGroupByField**: Gets or sets a value to enable or disable grouping for the pivot item.
* **AllowFilter**: Enables or disables filtering for the pivot item.
* **AllowSort**: Enables or disables sorting for the pivot item.

## Defining pivot item in XAML

Create a new pivot item by using the `PivotGridControl.PivotItem` class. A pivot item can be either a `PivotRow` or `PivotColumn`. Refer to the following code sample.

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

## Defining pivot item in code-behind

Include the *Syncfusion.PivotAnalysis.Base* in the MainWindow.xaml.cs file, and then define the pivot item for row and column. Add the defined pivot item to the pivot rows and pivot columns collections of the pivot grid control. Refer to the following code sample.

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
