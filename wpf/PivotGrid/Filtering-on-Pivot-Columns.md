---
layout: post
title: Filtering on Pivot Columns
description: Filtering on Pivot Columns
platform: wpf
control: PivotGrid
documentation: ug
---

# Filtering on Pivot Columns

## Filtering support for Calculation Columns

Pivot Grid allows you to restrict the display of records by using a mechanism called Filters. A filter enables you to extract a subset of records that meet certain filter criteria. Filters can be applied to one or more columns.

### Methods

The following methods are used to perform filtering on Pivot Columns.

Methods Table

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Prototype**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th></tr>
<tr>
<td>
ApplySavedValueFilter</td><td>
Void ApplySavedValueFilter(Dictionary(string,HashSet(string))</td><td>
This method is used to add the filter expression for the columns programmatically.</td></tr>
<tr>
<td>
ApplyFilters</td><td>
1. void ApplyFilters() 2. public void ApplyFilters(bool clearExistingFilter) </td><td>
This method uses the contents of HiddenRowIndexes to display pivot results filtered by using calculation values.Any previous filters are first cleared.This method uses the contents of HiddenRowIndexes to display pivot results filtered by using calculation values. Any previous filters are optionally cleared depending upon the Boolean value received from the “clearExisitingFilter” parameter.The preceding methods take effect only when the RowPivotsOnly property is set to _true_.</td></tr>
<tr>
<td>
ClearFilters</td><td>
1. void ClearFilters() 2. void ClearFilters(bool refresh) </td><td>
This method clears the current filtered state and redraws the pivot display.This method clears the current filtered state, and optionally redraws the pivot display.</td></tr>
<tr>
<td>
ReapplyFiltersAfterSort</td><td>
void ReapplyFiltersAfterSort()</td><td>
This method is used to reapply the filter after sort operation is performed.</td></tr>
<tr>
<td>
 RaiseFilterActionCompleted</td><td>
void RaiseFilterActionCompleted(FilterActionCompletedEventArgs e)</td><td>
This method is used raise the FilterActionCompleted event.</td></tr>
<tr>
<td>
GetFilteredValueFields()</td><td>
1. List(string) GetFilteredValueFields() 2. List[string] GetFilteredFieldValues(string fieldName, bool returnExclusions)</td><td>
This method returns the currently filtered value field names; RowPivotsOnly property must be set to _true_.This method returns a list of filtered values associated with a specific value column; RowPivotsOnly property must be set to _true_.</td></tr>
<tr>
<td>
UpdateAllSummariesRespectingHiddenRowIndexes</td><td>
void UpdateAllSummariesRespectingHiddenRowIndexes()</td><td>
This method will recompute all summaries, ignoring any summary row whose index is found under HiddenRowIndexes.</td></tr>
</table>


#### Properties

The following properties are used to perform filtering on Pivot Columns.

Properties Table

<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th></tr>
<tr>
<td>
AllowFilter</td><td>
Specifies whether the PivotGridControl allows to set a filter on the Calculation column.</td></tr>
<tr>
<td>
RowPivotOnly</td><td>
Specifies whether the PivotGridControl is used to pivot only rows, or both rows and columns. The default value is set to allow pivoting both rows and columns.Setting this property to true will produce the following changes:1. ShowGroupingBar property will be automatically set to _false_.2. The TopLeft covered cell that normally appears in a PivotGrid is replaced with individual header cells that have the same appearance as that of Calculation header cells.</td></tr>
</table>



#### Events

The following event is used to perform filtering on Pivot Columns.

Events Table

<table>
<tr>
<th>
{{ '**Event**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th></tr>
<tr>
<td>
FilterActionCompleted</td><td>
 object sender, FilterActionCompletedEventArgs e</td><td>
This event is triggered when the Filter action is completed.</td></tr>
</table>


The following code sample illustrates how to use the ApplySavedValueFilter method.

{% highlight C# %}  




Dictionary<string,HashSet<string>> dictionary = new Dictionary(string,HashSet(string))();

dictionary.Add("Cost", new HashSet(string)(){"701","230"});

this.pivotGridControl1.InternalGrid.ApplySavedValueFilter(dictionary);

{% endhighlight %} 

The following code sample illustrates how to use the AllowFilter property.

{% highlight C# %} 




pivotGridControl1.PivotCalculations[4].AllowFilter = true;



(or)



pivotGridControl1.PivotCalculations.Add(new PivotComputationInfo(){FieldName ="Cost", FieldHeader = "Cost", AllowFilter = true });

 {% endhighlight %} 
 
### Screenshot

![](Features_images/Features_img49.png)



Filtering on Pivot Columns

#### Sample Link

{InstallationDrive}:\Users\{UserName}\AppData\Local\Syncfusion\EssentialStudio\11.1.0.9\Wpf \PivotAnalysis.Wpf\Product Showcase\RowPivotsOnly Demo



