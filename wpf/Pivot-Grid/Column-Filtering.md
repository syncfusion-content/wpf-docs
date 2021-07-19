---
layout: post
title: Filtering in WPF Pivot Grid control | Syncfusion
description: Learn about Filtering support in Syncfusion Essential Studio WPF Pivot Grid control, its elements and more.
platform: wpf
control: Pivot grid
documentation: ug
---

# Filtering in WPF Pivot Grid

The [WPF Pivot Grid](https://www.syncfusion.com/wpf-controls/pivot-grid) allows you to restrict the display of records by using a mechanism called filter. A filter enables you to extract a subset of records that meet certain criteria.

Property

* **AllowFilter**: Specifies whether the pivot grid control allows you to set a filter on the calculation column.

Method

* **ApplySavedValueFilter**: When RowPivotsOnly is true, this method filters the values in computation columns using the information passed in the dictionary.

It is possible to do filtering operations for pivot calculation during runtime as well as during initial load.

To do so, define the pivot grid control in RowPivotsOnly mode. Add the respective pivot calculations and set the `AllowFilter` property to "true".

Create the dictionary using the `Dictionary` class and add the pivot items that are to be filtered. Invoke the `ApplySavedValueFilter()` method for applying the filters.

Refer to the following code sample.

{% highlight C# %}

    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            pivotGrid.Loaded += pivotGrid_Loaded;
        }

      void pivotGrid1_Loaded(object sender, RoutedEventArgs e)
      {
        pivotGrid.PivotCalculations.Add(new PivotComputationInfo(){FieldName ="Cost", FieldHeader = "Cost", AllowFilter = true });
        Dictionary<string,HashSet<string>>  dictionary = new Dictionary<string,HashSet<string>>();
        dictionary.Add("Cost", new HashSet<string>(){"701","230"});
        pivotGrid.InternalGrid.ApplySavedValueFilter(dictionary);
      }
    }

{% endhighlight %}

![To filter the records using column filter popup](Features-in-RowPivotsOnly-images/Filtering Enable in RowPivotsOnly.png)

N> You can also explore our [WPF Pivot Grid example](https://github.com/syncfusion/wpf-demos) to knows how to organizes and summarizes business data and displays the result in a cross-table format.
