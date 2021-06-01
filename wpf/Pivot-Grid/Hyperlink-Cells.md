---
layout: post
title: Hyperlink Cells in WPF Pivot Grid control | Syncfusion
description: Learn about Hyperlink Cells support in Syncfusion Essential Studio WPF Pivot Grid control, its elements and more.
platform: wpf
control: Pivot grid
 documentation: ug
---

# Hyperlink Cells in WPF Pivot Grid

The pivot grid allows hyperlinking of cells to retrieve a detailed information about a particular cell. It generates a separate event called HyperLinkCellClick for the clicked hyperlink cell, and the HyperLinkCellClickEventArgs returns the clicked PivotCellInfo.

The `Hyperlink Cell` property can be applied individually to the following cells:

* Column header
* Row header
* Summary header
* Summary cell
* Value cell

Property

* **IsHyperlinkCell**: Gets or sets whether to enable or disable the grid cells of pivot grid as hyperlink cells.

## Defining the property in pivot grid

You can enable or disable the hyperlink for the cells separately for all row header, column header, summary header, and value cells through the `IsHyperlinkCell` property. It can be mentioned in code-behind.

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

 ![PivotGrid with Column header hyperlink](Hyperlink-Cells-Images/PivotGrid shows column header hyperlink.png)
 _PivotGrid with Column header hyperlink_

 ![PivotGrid with Row header hyperlink](Hyperlink-Cells-Images/PivotGrid shows row header hyperlink.png)

 _PivotGrid with Row header hyperlink_

 ![PivotGrid with Summary cell hyperlink](Hyperlink-Cells-Images/PivotGrid shows summary cell hyperlink.png)

 _PivotGrid with Summary cell hyperlink_

 ![PivotGrid with Summary header hyperlink](Hyperlink-Cells-Images/PivotGrid shows summary header hyperlink.png)
 _PivotGrid with Summary header hyperlink_

![PivotGrid with Value cell hyperlink](Hyperlink-Cells-Images/PivotGrid shows value cell hyperlink.png)

 _PivotGrid with Value cell hyperlink_
