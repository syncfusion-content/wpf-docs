---
layout: post
title: Hyperlink Cells
description: Hyperlink Cells
platform: wpf
control: PivotGrid
documentation: ug
---


# Hyperlink Cells

The PivotGrid for WPF allows Hyperlinking of cells to retrieve a detailed description about a particular cell. The Hyperlink Cells property of PivotGrid generates a separate event called HyperLinkCellClick for the clicked cell and the HyperLinkCellClickEventArgs will return the clicked PivotCellInfo.

Hyperlink Cell’s property can be applied to the following cells:

* Column Header 
* Row Header 
* Summary Header
* Summary Cell
* Value Cell

### Use Case Scenarios

You can Hyperlink cells and can perform some custom operation on a Cell click. While doing so, you can get the complete information of the Cell like its Type, Range etc.

### Enabling Hyperlink Cells

You can enable a cell present in the Grid as a Hyperlink by setting the IsHyperlinkCell property of that cell style to True.

Example: To make a column header cell as a hyperlink, set PivotGrid.ColumnHeaderStyle.IsHyperlinkCell = True.

The property usage is illustrated in the code given below.

{% highlight C# %} 

// Instantiating PivotGridControl.

PivotGridControl PivotGrid1 = new PivotGridControl();

// Adding PivotRows.

PivotGrid1.PivotRows.Add(new PivotItem { FieldHeader = "Product" });

// Adding PivotColumns.

PivotGrid1.PivotColumns.Add(new PivotItem { FieldHeader = "Date" });

// Adding PivotCalculations.

PivotGrid1.PivotCalculations.Add(new PivotComputationInfo { FieldName="Amount" });



// To Enable Hyperlink for Column Header.

this.PivotGrid1.ColumnHeaderCellStyle.IsHyperlinkCell = true;

// To Enable Hyperlink for Row Header.

this.PivotGrid1.RowHeaderCellStyle.IsHyperlinkCell = true;

// To Enable Hyperlink for Summary Header.

this.PivotGrid1.SummaryHeaderStyle.IsHyperlinkCell = true;

// To Enable Hyperlink for Summary Cell.

this.PivotGrid1.SummaryCellStyle.IsHyperlinkCell = true;

// To Enable Hyperlink for Value Cell.

this.PivotGrid1.ValueCellStyle.IsHyperlinkCell = true;

 {% endhighlight %} 


{% highlight vbnet %} 


' Instantiating PivotGridControl.

Dim PivotGrid1 As PivotGridControl = New PivotGridControl()

' Adding PivotRows.

PivotGrid1.PivotRows.Add(New PivotItem With {.FieldHeader = "Product"})

' Adding PivotColumns.

PivotGrid1.PivotColumns.Add(New PivotItem With {.FieldHeader = "Date"})

' Adding PivotCalculations.

PivotGrid1.PivotCalculations.Add(New PivotComputationInfo With {.FieldName="Amount"})


' To Enable Hyperlink for Column Header.

Me.PivotGrid1.ColumnHeaderCellStyle.IsHyperlinkCell = True

' To Enable Hyperlink for Row Header.

Me.PivotGrid1.RowHeaderCellStyle.IsHyperlinkCell = True

' To Enable Hyperlink for Summary Header.

MePivotGrid1.SummaryHeaderStyle.IsHyperlinkCell = True

' To Enable Hyperlink for Summary Cell.

Me. PivotGrid1.SummaryCellStyle.IsHyperlinkCell = True

' To Enable Hyperlink for Value Cell.

Me.PivotGrid1.ValueCellStyle.IsHyperlinkCell = True

{% endhighlight %} 



The below screen shot shows how the Column Header is hyperlinked.

![C:/Users/dwarageshmb/Desktop/Vol 4 Docs/Images/PivotGrid Hyperlink Col.png](Features_images/Features_img7.png)



The below screen shot shows how the Row Header is hyperlinked.

![C:/Users/dwarageshmb/Desktop/Vol 4 Docs/Images/PivotGrid Hyperlink Row.png](Features_images/Features_img8.png)



The below screen shot shows how the value in a cell is hyperlinked.

![C:/Users/dwarageshmb/Desktop/Vol 4 Docs/Images/PivotGrid HyperlinkVal.png](Features_images/Features_img9.png)



#### Sample Link

..\..\ Syncfusion\BI\WPF\PivotAnalysis.WPF\Samples\Appearance\Hyperlink Cell Demo



