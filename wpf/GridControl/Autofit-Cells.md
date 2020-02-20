---
layout: post
title: Autofit cells in GridControl| WPF | Syncfusion
description: Learn here about how to resizing the row heights and column widths in the Syncfusion WPF GridControl.
platform: wpf
control: GridControl
documentation: ug
---

# Autofit cells in GridControl

This section explains about AutoFit content of WPF GridControl.

## AutoFit content

The rows heights and column widths can be made to adjust themselves automatically to fit the content by using the methods ResizeRowsToFit() and ResizeColumnsToFit(), which accept the following two parameters:

1.A range of rows or columns whose size should be adjusted 
2.A GridResizeToFitOptions enumeration value. 

The GridResizeToFitOptions enum value specifies how the resizing action should be performed, whether to include covered cells, hidden cells, headers, and whether or not to shrink size, and the like.

The following code illustrates the usage of ResizeRowsToFit and ResizeColumnsToFit methods:

{% tabs %}
{% highlight c# %}
//Auto fit column 3
grid.Model.ResizeColumnsToFit(GridRangeInfo.Col(3), GridResizeToFitOptions.NoShrinkSize);

//Auto fit row 2
grid.Model.ResizeRowsToFit(GridRangeInfo.Row(2), GridResizeToFitOptions.NoShrinkSize);
{% endhighlight %}
{% endtabs %}

![Auto fit Column 3 in WPF GridControl](Autofit_images/autofit_column.jpeg)

![Auto fit Row 2 in WPF GridControl](Autofit_images/autofit_row.jpeg)

