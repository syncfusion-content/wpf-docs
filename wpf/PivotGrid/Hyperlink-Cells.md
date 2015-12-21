---
layout: post
title: 1354-Hyperlink Cells
description:  1.3.5.4 hyperlink cells
platform: wpf
control: PivotGridControl
documentation: ug
---

# Hyperlink Cells

PivotGrid allows Hyperlinking of cells to retrieve a detailed information about a particular cell. PivotGrid generates a separate event called HyperLinkCellClick for the clicked hyperlink cell with  and the HyperLinkCellClickEventArgs will return the clicked PivotCellInfo.

**Hyperlink Cell** property can be applied individually to the following cells:

* Column Header 
* Row Header 
* Summary Header
* Summary Cell
* Value Cell

**Use Case Scenarios**

User could perform some custom operations on a Cell click and able to get the complete information of the cells like its Type, Range etc.

                                                                Property Table

<table>
<tr>
<th>
Property Name</th><th>
Description</th><th>
Type</th><th>
Value it Accepts</th><th>
Reference Link<th></tr>
<tr>
<td>
IsHyperlinkCell</td><td>
Gets or sets whether the to enable or disable the PivotGrid grid cells as hyperlink cells.</td><td>
bool</td><td>
True, False(Default)</td><td>
-</td></tr>
<tr>
</table>

## Defining the property in PivotGrid

It is possible to enable or disable the hyperlink for the cells separately for all Row header, Column header, Summary header and Value cells through **IsHyperlinkCell** property. It can be mentioned in *Code-Behind*.

Please refer the below code snippet.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        // Enabling Column Header cells as Hyperlink cell
        pivotGrid.ColumnHeaderCellStyle.IsHyperlinkCell = true;
        // Enabling Row Header cells as Hyperlink cell
        pivotGrid.RowHeaderCellStyle.IsHyperlinkCell = true;
        // Enabling both Row and Column summary Header cells as Hyperlink cell
        pivotGrid.SummaryHeaderStyle.IsHyperlinkCell = true;
        // Enabling both Row and Column summary cells as Hyperlink cell
        pivotGrid.SummaryCellStyle.IsHyperlinkCell = true;
        // Enabling Value cells as Hyperlink cell
        pivotGrid.ValueCellStyle.IsHyperlinkCell = true;
    }
}

{% endhighlight %}
 
 ![](Hyperlink-Cells-Images/PivotGrid shows column header hyperlink.png)
 
 _PivotGrid with Column header hyperlink_
 
 ![](Hyperlink-Cells-Images/PivotGrid shows row header hyperlink.png)
 
 _PivotGrid with Row header hyperlink_
 
 ![](Hyperlink-Cells-Images/PivotGrid shows summary cell hyperlink.png)
 
 _PivotGrid with Summary cell hyperlink_
 
 ![](Hyperlink-Cells-Images/PivotGrid shows summary header hyperlink.png)
 
 _PivotGrid with Summary header hyperlink_
 
 ![](Hyperlink-Cells-Images/PivotGrid shows value cell hyperlink.png)
 
 _PivotGrid with Value cell hyperlink_
