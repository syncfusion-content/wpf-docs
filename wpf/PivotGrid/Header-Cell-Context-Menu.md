---
layout: post
title: Header Cell Context Menu
description: Header Cell Context Menu
platform: wpf
control: PivotGrid
documentation: ug
---

# Header Cell Context Menu

## Programmatic and UI level support for expand collapse operation

Expand/collapse operations can be done at both the UI and programmatic level. The context menu will be shown while right-clicking on the expander cell. Its skin will change with respect to the grid’s background color, and it is localizable too. Expand/collapse operations can be handled at the row level and column level individually. The header cell’s UniqueText will be shown as a ToolTip for each context menu item.

### Use Case Scenarios

Enabling UI-level expand/collapse operations will allow the end user to expand and collapse the particular cell and entire row or column individually. Programmatically, they can expand/collapse any number of rows or columns.

![C:/Users/arulraja/AppData/Local/Syncfusion/EssentialStudio/10.2.0.48/BI/WPF/PivotAnalysis.Wpf/Samples/Grouping Bar/Context Menu Demo/Images/ExpandCollapse.png](Features_images/Features_img44.png)



## Tables for Properties, Methods, and Events

## Properties

Properties Table

<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Data Type**' | markdownify }}</th></tr>
<tr>
<td>
EnableContextMenu</td><td>
Gets or sets the context menu for expander cells (row header and column header cells only) </td><td>
Dependency</td><td>
Boolean </td></tr>
</table> 

### Methods

Methods Table

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<td>
ExpandRow(string)  </td><td>
Expands the group for the given row UniqueText.</td><td>
string </td><td>
NA </td><td>
void </td></tr>
<tr>
<td>
ExpandColumn (string)  </td><td>
Expands the group for the given column UniqueText.</td><td>
string</td><td>
NA</td><td>
void</td></tr>
<tr>
<td>
CollapseRow(string)  </td><td>
Collapse the group for the given row UniqueText.</td><td>
string</td><td>
NA</td><td>
void</td></tr>
<tr>
<td>
CollapseColumn (string)  </td><td>
Collapse the group for the given column UniqueText.</td><td>
string</td><td>
NA</td><td>
void</td></tr>
<tr>
<td>
ExpandRow(List[string])  </td><td>
Expands the group for the given list of row UniqueText.</td><td>
List(string)</td><td>
NA</td><td>
void</td></tr>
<tr>
<td>
ExpandColumn (List[string])  </td><td>
Expands the group for the given list of column UniqueText.</td><td>
List(string)</td><td>
NA</td><td>
void</td></tr>
<tr>
<td>
Col
lapseRow(List[string])  </td><td>
Collapse the group for the given list of row UniqueText.</td><td>
List(string)</td><td>
NA</td><td>
void</td></tr>
<tr>
<td>
CollapseColumn (List[string])  </td><td>
Collapse the group for the given list of column UniqueText.</td><td>
List(string)</td><td>
NA</td><td>
void</td></tr>
</table> 

### Events

Event Table

<table>
<tr>
<th>
 {{ '**Event**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }} </th><th>
{{ '**Arguments**' | markdownify }} </th><th>
{{ '**Type**' | markdownify }} </th></tr>
<tr>
<td>
ExpandCollapse</td><td>
Provides enabling/disabling option for expand/collapse for a specific group (using UniqueText).</td><td>
NA </td><td>
Event</td></tr>
</table>


#### Sample Link

A sample is available in the Syncfusion WPF BI dashboard in the following location.

PivotAnalysis > GroupingBar > Context Menu Demo

{InstalledDrive}\Users\ {User}\AppData\ Local \Syncfusion\ EssentialStudio\{Installed Version}\BI\WPF\PivotAnalysis.Wpf\Samples\Grouping Bar \Context Menu Demo

### Adding to an Application 

You can enable the context menu for row/column header cells present in the grid by setting the EnableContextMenu Boolean property of that cell style to true.

The property usage is illustrated in the code given below.

{% highlight C# %}  


// To Enable Context Menu for Column Header.

this.PivotGrid1.ColumnHeaderCellStyle.EnableContextMenu = true;

// To Enable Context Menu for Row Header.

this.PivotGrid1.RowHeaderCellStyle.EnableContextMenu = true;

{% endhighlight %} 

{% highlight vbnet %} 


// To Enable Context Menu for Column Header.

Me.PivotGrid1.ColumnHeaderCellStyle.EnableContextMenu = True

// To Enable Context Menu for Row Header.

Me.PivotGrid1.RowHeaderCellStyle.EnableContextMenu = True

{% endhighlight %} 

![C:/Users/arulraja/AppData/Local/Syncfusion/EssentialStudio/10.2.0.48/BI/WPF/PivotAnalysis.Wpf/Samples/Grouping Bar/Context Menu Demo/Images/ExpandCollapse.png](Features_images/Features_img45.png)



![](Features_images/Features_img46.png)



To perform the expand/collapse operations programmatically, you can make use of the eight methods respectively as per your requirement. Passing the UniqueText as a parameter you can expand/collapse one or more columns/rows. The method usage is illustrated in the following code sample.

{% highlight C# %}   


/// Expands the Bike from row       

this.pivotGrid1.ExpandRow("Bike");

/// Collapses the Bike from row        

this.pivotGrid1.CollapseRow("Bike");        

/// Expands the Canada from column        

this.pivotGrid1.ExpandColumn("Canada");        

/// Collapses the Canada from column        

this.pivotGrid1.CollapseColumn("Canada");        

/// Collapses the given collection of UniqueText string values for row        

this.pivotGrid1.CollapseRow(new List<string> { "Bike", "Car" });        

/// Expands the given collection of UniqueText string values for row        

this.pivotGrid1.ExpandRow(new List<string> { "Bike", "Car" });        

/// Collapses the given collection of UniqueText string values for Column        

this.pivotGrid1.CollapseColumn(new List<string> { "Canada", "France" });        

/// Expands the given collection of UniqueText string values for Column        

this.pivotGrid1.ExpandColumn(new List<string> { "Canada", "France" });

{% endhighlight %}

{% highlight vbnet %}  


/// Expands the Bike from row       

Me.pivotGrid1.ExpandRow("Bike")

/// Collapses the Bike from row        

Me.pivotGrid1.CollapseRow("Bike")

/// Expands the Canada from column        

Me.pivotGrid1.ExpandColumn("Canada")

/// Collapses the Canada from column        

Me.pivotGrid1.CollapseColumn("Canada")

/// Collapses the given collection of UniqueText string values for row        

Me.pivotGrid1.CollapseRow(New String() {"Bike", "Car"}.ToList())

/// Expands the given collection of UniqueText string values for row        

Me.pivotGrid1.ExpandRow(New String() {"Bike", "Car"}.ToList())

/// Collapses the given collection of UniqueText string values for Column        

Me.pivotGrid1.CollapseColumn(New String() {"Canada", "France"}.ToList())

/// Expands the given collection of UniqueText string values for Column        

Me.pivotGrid1.ExpandColumn(New String() {"Canada", "France"}.ToList())

{% endhighlight %} 



