---
layout: post
title: 13426-GetRawItem
description: 1.3.4.26 getrawitem
platform: wpf
control: PivotGridControl
documentation: ug
---

# GetRawItem

GetRawItemFor method is used to obtain the list of raw items for value cell, total cell or grand total cell in PivotGrid. This method has been implemented in the PivotEngine which can be used independently from the PivotGrid. 

Method Table

<table>
<tr>
<th>
Method </th><th>
Description </th><th>
Parameters </th><th>
Return Type </th></tr>
<tr>
<td>
GetRawItemFor</td><td>
This method allows you to get the raw item of the selected cell (Value cell or Summary cell). </td><td>
(int row, int column)</td><td>
List</td></tr>
</table>

## Defining GetRawItemFor method to PivotGrid

After defining the PivotGrid control, enable the Hyperlink for Value and Summary cells using **IsHyperlinkCell** property. Then, invoke the Hyperlink cell click event and call the GetRawItemFor method as illustrated below. 

Please refer the below code snippet.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        pivotGrid.ValueCellStyle.IsHyperlinkCell = true;
        pivotGrid.SummaryCellStyle.IsHyperlinkCell = true;
        pivotGrid.HyperlinkCellClick += pivotGrid_HyperlinkCellClick;
    }

    void pivotGrid_HyperlinkCellClick(object sender, HyperlinkCellClickEventArgs e) {
        pivotGrid.PivotEngine.GetRawItemsFor(e.RowColumnIndex.RowIndex, e.RowColumnIndex.ColumnIndex);
    }
}

{% endhighlight %}

![](GetRawItem-images/PivotGrid shows Raw Item.png)
