---
layout: post
title: 1352-Column-Filtering
description:  1.3.5.2 column filtering
platform: wpf
control: PivotGridControl
documentation: ug
---

# Column Filtering

Pivot Grid allows you to restrict the display of records by using a mechanism called Filters. A filter enables you to extract a subset of records that meet certain filter criteria. Filters can be applied to one or more columns.

Property

* **AllowFilter** - Specifies whether the PivotGridControl allows to set a filter on the Calculation column.


Methods Table

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Return Type</th></tr>
<tr>
<td>
ApplySavedValueFilter</td><td>
When RowPivotsOnly is true, this method filters the value computation columns using the information in the passed-in dictionary.</td><td>
(Dictionary<(string),HashSet<(string)>> exclusions)</td><td>
void</td></tr>
</table>

## Defining the property in PivotGrid

It is possible to do the filtering operations for the PivotCalculation items in both run time and creating the filters in the load time itself.

After defining PivotGrid control in RowPivotsOnly mode, add the respective PivotCalculations as per your requirement and set the **AllowFilter** property to true.

Create the Dictionary by using Dictionary class and add the PivotItems which are need to be filtered. Invoke the **ApplySavedValueFilter()** method for applying filters.

Please refer the below code snippet.

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

![](Features-in-RowPivotsOnly-images/Filtering Enable in RowPivotsOnly.png)

