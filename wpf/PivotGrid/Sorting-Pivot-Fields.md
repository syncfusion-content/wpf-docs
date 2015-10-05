---
layout: post
title: Sorting Pivot Fields| PivotGrid | Wpf | Syncfusion
description: Sorting Pivot Fields
platform: wpf
control: PivotGrid
documentation: ug
---

# Sorting Pivot Fields

The pivot row fields, pivot column fields, and PivotComputationInfo fields can be arranged individually either in ascending or descending order. The following options to handle this arrangement are available in the context menu that appears in the grouping bar:

*Smallest to Largest—Arranges the pivot fields based on the field header from first letter to the last.

*Largest to Smallest—Arranges the pivot fields based on the field header from last letter to the first.

The above mentioned options will rearrange the fields in the respective pivot item area.

![](Features_images/Features_img34.png)



### Sample Link

A demo of this feature is available in the following location:

C:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\x.x.x.x\ BI\WPF\PivotAnalysis.WPF\Samples\Grouping Bar\Context Menu Demo\


## Sort by value of computations fields

This feature allows users to sort column values in ascending or descending order. 

There are five options for sorting:

1.Sort all the columns.

2.Sort all columns other than total and grand total columns.

3.Sort only total columns.

4.Sort only grand total columns.

5.Disable sort.


### Use Case Scenarios

Using this feature, the values in the columns can be sorted in given order, either ascending or descending. 

![](Features_images/Features_img35.png)



### Properties




<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
SortDirection</td><td>
Gets or sets the sort order to ascending or descending. </td><td>
CLR </td><td>
ListSortDirection</td><td>
NA</td></tr>
<tr>
<td>
SortOption</td><td>
Gets or sets the sorting option as all, none, columnsorting, total sorting, or grandtotal sorting.</td><td>
DependencyProperty</td><td>
PivotSortOption</td><td>
NA</td></tr>
</table>


### Methods



<table>
<tr>
   <th>Method</th>
   <th>Description</th>
   <th>Parameters</th>
   <th>Type</th>
   <th>Return Type</th>
   <th>Reference links</th>
</tr>
<tr>
    <th>SortByCalculation</th>
	<th>Sorts the values in the columns in ascending or descending order.</th>
	<th>columnIndex </th>
	<th>NA</th>
	<th>void</th>
	<th>NA</th>
</tr>
</table>


### Enum



<table>
<tr>
<td>
Name</td><td>
Options</td></tr>
<tr>
<td>
PivotSortOption</td><td>
NoneAll Column SortingTotal SortingGrandTotal Sorting </td></tr>
</table>


### Sample Link

{InstalledDrive}:\Users\{username}\AppData\Local\Syncfusion\EssentialStudio\11.1.0.9\Wpf\PivotAnalysis.WPF\Interactivity features\SortingDemo

Adding sort by value of computations fields to an application

The following code sample illustrates how to sort computations fields by value:


{% highlight C# %}


Sorting Options

//All: Enables sort on all the columns in pivot grid.

this.pivotGrid.SortOption = PivotSortOption.All;



//Column Sorting: Enables sort on all the columns other than total and grand total columns.

this.pivotGrid.SortOption = PivotSortOption.ColumnSorting;



//Total Sorting: Enables sort on total columns.

this.pivitGrid.SortOption = PivotSortOption.TotalSorting;



//GrandTotal Sorting: Enables sort on grand total columns.

this.pivotGrid.SortOption = PivotSortOption.GrandTotalSorting;



//None: It is the default option and it disables sorting on columns.

this.pivotGrid.SortOption = PivotSortOption.None;


{% endhighlight %}


## Providing the option to add/remove Report Filters in the PivotGrid control

This feature provides programmatic-level support to apply filtering (Add, Remove, Insert, RemoveAt, InsertAt) to the pivot grid.

The following filter operations can be done from programmatic level:

1.Add – Includes a filter item at the end of the filter collection.

2.InsertAt – Used to insert the filter item at the given position in the collection.

3.Remove – Removes the given filter item.

4.RemoveAt- Used to remove the item present at the given position.

5.Clear- Removes all the items in the filter collection.


### Use Case Scenarios

This feature helps the user to add or remove the filter items from programmatic level instead of UI.

![](Features_images/Features_img36.png)



### Properties



<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
Data Type</td><td>
Reference links</td></tr>
<tr>
<td>
DimensionName</td><td>
Name of the dimension (FieldMappingName). </td><td>
CLR </td><td>
string</td><td>
NA</td></tr>
<tr>
<td>
DimensionHeader</td><td>
Name of the dimension header (FieldHeader).</td><td>
CLR</td><td>
string</td><td>
NA</td></tr>
<tr>
<td>
ItemCollection</td><td>
Returns the list of elements under the filter item.</td><td>
CLR</td><td>
FilterItemsCollection</td><td>
NA</td></tr>
</table>


### Methods



<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Type</th><th>
Return Type</th><th>
Reference links</th></tr>
<tr>
<th>
AddFilter</th><th>
Used to add a filter item in the filter collection.</th><th>
(FilterExpression item) </th><th>
NA </th><th>
void</th><th>
NA</th></tr>
<tr>
<th>
RemoveFilter</th><th>
Used to remove the given item from the filter collection.</th><th>
(FilterExpress item)</th><th>
NA</th><th>
void</th><th>
NA</th></tr>
</table>


### Sample Link

{InstallationDrive}:\Users\{UserName} \AppData\Local\Syncfusion\EssentialStudio\11.1.0.9\Wpf \PivotAnalysis.Wpf\Interactivity features\FilteringDemo

## Adding the providing option to add or remove Report Filters in the PivotGrid control to an application


{% highlight C# %}  

 

 //Add:            

               this.pivotGrid.Filters.Add(new FilterExpression("Product"));

//Remove:

               this.pivotGrid.Filters.Remove(this.Target.Filters.Where(i => i.DimensionName == "Product").FirstOrDefault());

//Insert:

               this.pivotGrid.Filters.Insert(0, new FilterExpression("State"));

//RemoveAt:

               this.pivotGrid.Filters.RemoveAt(1);

//Clear:                    
               this.pivotGrid.Filters.Clear();

{% endhighlight %}



