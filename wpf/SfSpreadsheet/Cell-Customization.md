---
layout: post
title: Cell Customization| SfSpreadsheet | WPF | Syncfusion
description: cell customization
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Cell Customization

SfSpreadsheet provides support to customize the cell in [SpreadsheetGrid](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6454.html) with Data template. In order to customize the cell, you need to override the [SpreadsheetVirtualizingCellRendererBase](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6915.html) and [SpreadsheetColumn](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6379.html) classes.

For Example,

Create a ButtonTemplate in Xaml file,

{% highlight xaml %}

<DataTemplate x:Key="ButtonTemplate" >

<Expander x:Name="Button" ExpandDirection="Right" IsExpanded="True" 

                        Expanded="Button_Expanded" Collapsed="Button_Collapsed"/>

</DataTemplate>

{% endhighlight %}

Now create an Extension Class SpreadsheetColumnExt which is derived from [SpreadsheetColumn](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6379.html) to create a cell type with a Content Control by overriding the [OnUpdateColumn](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic1104.html).

{% highlight c# %}

public class SpreadsheetColumnExt : SpreadsheetColumn
{

public SpreadsheetColumnExt(SpreadsheetGrid grid) : base(grid)
{

}

//Gets or sets the Edit DataTemplate for the cell.

public DataTemplate CellEditTemplate
{
  get;
  set;
}

// Gets or sets the Item DataTemplate for the cell

public DataTemplate CellItemTemplate
{

  get;
  set;
}

protected override void OnUpdateColumn(out FrameworkElement oldElement)
{
    if (RowIndex == 3 && ColumnIndex == 6)
    {
       this.CellItemTemplate = Application.Current.MainWindow.Resources["ButtonTemplate"] as DataTemplate;
    }         
    base.OnUpdateColumn(out oldElement);
}
}

{% endhighlight %}

Create a SpreadsheetTemplateCellRenderer class which is derived from SpreadsheetVirtualizingCellRendererBase and overrides the [OnInitializeEditElement](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6936.html) and [OnInitializeDisplayElement](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6935.html) which sets the Content Control template for cell.

{% highlight c# %}
public class SpreadsheetTemplateCellRenderer : SpreadsheetVirtualizingCellRendererBase<ContentControl, ContentControl>
{
  public SpreadsheetTemplateCellRenderer()
  {
    SupportDrawingOptimization = false;
  }

  protected override void OnUpdateCellStyle(RowColumnIndex cellRowColumnIndex, ContentControl uiElement, SpreadsheetColumn column)
  {
    if (uiElement.ContentTemplate == null)  
    {
      uiElement.ContentTemplate = (column as SpreadsheetColumnExt).CellItemTemplate;
    }
    base.OnUpdateCellStyle(cellRowColumnIndex, uiElement, column);
  }

  protected override void OnInitializeEditElement(RowColumnIndex rowColumnIndex, ContentControl uiElement, SpreadsheetColumn column)
  {
    var excelStyle = column.ExcelStyle;
    var columnExt = (column as SpreadsheetColumnExt);
    uiElement.ContentTemplate = columnExt.CellEditTemplate;
  }
  
  protected override void OnInitializeDisplayElement(RowColumnIndex rowColumnIndex, ContentControl uiElement, SpreadsheetColumn column)
  {
    uiElement.ContentTemplate = (column as SpreadsheetColumnExt).CellItemTemplate;
  }
}

{% endhighlight %}

Finally in the MainWindow.Xaml.cs file, invoke the WorkbookLoaded Event of SfSpreadsheet and initialize the SpreadsheetTemplateCellRenderer and add the Data Template to the renderer collection. 

{% highlight c# %}
void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{
  foreach (var item in args.GridCollection)
  {
    var grid = item.Value;

    grid.CreateGridColumn = CreateSpreadsheetColumnExt;

    var renderer = new SpreadsheetTemplateCellRenderer();

    grid.CellRenderers.Add("DataTemplate", renderer);

    grid.QueryRange += grid_QueryRange;
  }
}

void grid_QueryRange(object sender, SpreadsheetQueryRangeEventArgs e)
{
 if (e.Cell.ColumnIndex == 6 && e.Cell.RowIndex == 3)
 {
    e.CellType = "DataTemplate";
    e.CellValue = "template";
    e.Handled = true;
 }
}

//To access the SpreadsheetColumnExt

public GridColumn CreateSpreadsheetColumnExt(SfCellGrid grid)
{
    return new SpreadsheetColumnExt(grid as SpreadsheetGrid);
}

{% endhighlight %}
