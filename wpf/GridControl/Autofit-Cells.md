---
layout: post
title: Autofit Cells in WPF GridControl control | Syncfusion
description: Learn about Autofit Cells support in Syncfusion WPF GridControl control and more.
platform: wpf
control: GridControl
documentation: ug
---

# Autofit Cells in WPF GridControl

GridControl provides support to autofit rows and columns based on the content of cells.

## Autofit row height

GridControl provides the support to auto fit the row height based on content of the cells using [ResizeRowsToFit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridModel.html#Syncfusion_Windows_Controls_Grid_GridModel_ResizeRowsToFit_Syncfusion_Windows_Controls_Grid_GridRangeInfo_Syncfusion_Windows_Controls_Grid_GridResizeToFitOptions_) method which accepts the following parameters,

* [GridRangeInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridRangeInfo.html) - Specifies the range where `GridControl` auto fits the rows based on the cell content.
* [GridResizeToFitOptions](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridResizeToFitOptions.html) - Specifies the auto fit settings to customize the auto fit behavior.

{% tabs %}
{% highlight c# %}

//To auto fit single row 2,
grid.Model.ResizeRowsToFit(GridRangeInfo.Row(2), GridResizeToFitOptions.NoShrinkSize);

//To auto fit range of rows from 3 to 6,
grid.Model.ResizeRowsToFit(GridRangeInfo.Rows(3,6), GridResizeToFitOptions.NoShrinkSize);

//To auto fit range of cell's(including Covered cells) row height,
this.grid.Model.ResizeRowsToFit(GridRangeInfo.Cells(1, 1, 2, 2),GridResizeToFitOptions.IncludeCellsWithinCoveredRange);

//To auto fit entire grid's row height,
this.grid.Model.ResizeRowsToFit(GridRangeInfo.Table(), GridResizeToFitOptions.None);

{% endhighlight %}
{% endtabs %}

N> [View sample in GitHub](https://github.com/SyncfusionExamples/fit-the-column-width-and-row-height-based-on-content-size)

## Autofit column width

GridControl provides the support to auto fit the column width based on content of the cells using [ResizeColumnsToFit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridModel.html#Syncfusion_Windows_Controls_Grid_GridModel_ResizeColumnsToFit_Syncfusion_Windows_Controls_Grid_GridRangeInfo_Syncfusion_Windows_Controls_Grid_GridResizeToFitOptions_) method which accepts the following parameters,

* [GridRangeInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridRangeInfo.html) - Specifies the range where `GridControl` auto fits the columns based on the cell content.
* [GridResizeToFitOptions](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridResizeToFitOptions.html) - Specifies the auto fit settings to customize the auto fit behavior.

{% tabs %}
{% highlight c# %}

//To auto fit single column 2,
grid.Model.ResizeColumnsToFit(GridRangeInfo.Col(2), GridResizeToFitOptions.NoShrinkSize);

//To auto fit range of Columns from 3 to 6,
grid.Model.ResizeColumnsToFit(GridRangeInfo.Cols(3,6), GridResizeToFitOptions.NoShrinkSize);

//To auto fit range of cell's(including Covered cells) column width,
this.grid.Model.ResizeColumnsToFit(GridRangeInfo.Cells(1, 1, 2, 2),GridResizeToFitOptions.IncludeCellsWithinCoveredRange);

//To auto fit entire grid's column width,
this.grid.Model.ResizeColumnsToFit(GridRangeInfo.Table(), GridResizeToFitOptions.None);

{% endhighlight %}
{% endtabs %}

N> [View sample in GitHub](https://github.com/SyncfusionExamples/fit-the-column-width-and-row-height-based-on-content-size)

## Autofit Options

The auto fitting of rows and columns can be customized by using [GridResizeToFitOptions](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridResizeToFitOptions.html) enum. This enum provides the following options to control the autofit behavior of cells.

<table>
<tr>
<th>
Options</th><th>
Description</th></tr>
<tr>
<td>
None</td><td>
Default option to autofit the cells. Also, this option while auto fitting, shrinks the size and does not include covered cells, header cells.</td></tr>
<tr>
<td>
ResizeCoveredCells</td><td>
This option includes covered cells while auto fitting the cells. When using this option, only the last row or column 
of a covered range is resized. </td></tr>
<tr>
<td>
NoShrinkSize</td><td>
This option autofit the cells without shrinking the original size.For example, while auto fitting the cells, if the size is reduced than the normal size of the cell due to the content, you can use this option to retain the original size without shrinking. </td></tr>
<tr>
<td>
IncludeHeaders</td><td>
This option includes row/column header while auto fitting the cells.</td></tr>
<tr>
<td>
IncludeCellsWithinCoveredRange</td><td>
`ResizeCoveredCells` option only autofit the last row or column of a covered range. But this option
autofit the columns or rows before the last one also.</td></tr>
<tr>
<td>
IncludeHiddenCells</td><td>
This option includes the hidden cells while auto fitting the cells. By default, visible cells only will be auto fitted and if you want to autofit all the cells including hidden cells in `GridControl`, then need to use this option.</td></tr>
</table>

## Autofit Cells based on Wrap Text

To autofit the cell's height based on the applied wrap text, need to use [ResizeRowsToFit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridModel.html#Syncfusion_Windows_Controls_Grid_GridModel_ResizeRowsToFit_Syncfusion_Windows_Controls_Grid_GridRangeInfo_Syncfusion_Windows_Controls_Grid_GridResizeToFitOptions_) method.

{% tabs %}
{% highlight c# %}

this.grid.Model[2, 2].TextWrapping = TextWrapping.Wrap;
this.grid.Model.ResizeRowsToFit(GridRangeInfo.Cell(2, 2),GridResizeToFitOptions.NoShrinkSize);

{% endhighlight %}
{% endtabs %}

N> [View sample in GitHub](https://github.com/SyncfusionExamples/fit-the-column-width-and-row-height-based-on-content-size)

## How to avoid rendering issues due to fractions when auto fit the cells

When you autofit the cells, you may face scrolling and rendering issues in GridControl. You can set [GridColumnAutoSizer.CanRoundCalculation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridColumnAutoSizer.html#Syncfusion_Windows_Controls_Grid_GridColumnAutoSizer_CanRoundCalculation) to `true` to avoid rendering issues if needed.

{% tabs %}
{% highlight c# %}

GridColumnAutoSizer.CanRoundCalculation = true;

{% endhighlight %}
{% endtabs %}

## Change the size of row height and column width to fit all cells in View

 When GridControl is placed inside custom control and if you want to auto fit the row/column size of GridControl based on custom control resized position, then you can invoke [SizeChanged](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.control.sizechanged?view=netframework-4.8) event of GridControl and set the [RowHeights](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridModel.html#Syncfusion_Windows_Controls_Grid_GridModel_RowHeights) and [ColumnWidths](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridModel.html#Syncfusion_Windows_Controls_Grid_GridModel_ColumnWidths) property of [GridModel](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridModel.html) to the resized height/width.

{% tabs %}
{% highlight c# %}

grid.SizeChanged += grid_SizeChanged;

//To autofit the cells based on custom control resizing,

void grid_SizeChanged(object sender, SizeChangedEventArgs e)
{
           
     double width = (e.NewSize.Width - grid.Model.ColumnWidths.DefaultLineSize - 1) / (grid.Model.ColumnCount - 1);
     double height = (e.NewSize.Height - grid.Model.RowHeights.DefaultLineSize - 1) / (grid.Model.RowCount - 1);
     for (int i = 1; i < grid.Model.ColumnCount; ++i)
        grid.Model.ColumnWidths[i] = width;
     for (int j = 1; j < grid.Model.RowCount; ++j)
        grid.Model.RowHeights[j] = height;
            
}

{% endhighlight %}
{% endtabs %}

N> [View sample in GitHub](https://github.com/SyncfusionExamples/fit-the-columns-and-rows-size-based-on-custom-control-size)


## See also

[How to auto fit all the columns in a GridControl based on the Window size](https://www.syncfusion.com/kb/7810)
