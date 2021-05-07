---
layout: post
title: GetRawItem in WPF Pivot Grid control | Syncfusion
description: Learn about GetRawItem support in Syncfusion Essential Studio WPF Pivot Grid control, its elements and more details.
platform: wpf
control: Pivot grid
documentation: ug
---

# GetRawItem in WPF Pivot Grid

GetRawItemFor method is used to obtain the list of raw items for value cell, total cell, or grand total cell in the pivot grid.

To achieve this, define the pivot grid control and enable the hyperlink option of the value and summary cells using the `IsHyperlinkCell` property. Then, invoke the hyperlink cell click event and call the `GetRawItemFor` method as illustrated in the following code snippet.

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

![Getting the list of raw items for specific cells](GetRawItem-images/PivotGrid shows Raw Item.png)
