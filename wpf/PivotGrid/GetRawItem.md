---
layout: post
title: GetRawItem
description: Define GetRawItemFor method
platform: wpf
control: Pivot grid
documentation: ug
---

# GetRawItem

GetRawItemFor method is used to obtain the list of raw items for value cell, total cell or grand total cell in PivotGrid.

To achieve this, define the PivotGrid control and enable the hyperlink option of the value and summary cells using `IsHyperlinkCell` property. Then, invoke the hyperlink cell click event and call the `GetRawItemFor` method as illustrated below.

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
