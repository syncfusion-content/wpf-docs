---
layout: post
title: Cell Customization in WPF Spreadsheet control | Syncfusion
description: Learn here all about Cell Customization support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Cell Customization in WPF Spreadsheet (SfSpreadsheet)

SfSpreadsheet provides support to customize the cell with Data template. It allows to load any WPF control or custom control into the cell. 

In order to customize the cell, please follow the below steps

* Create a DataTemplate
* Override the  SpreadsheetColumn class
* Create  the Custom Cell Renderer
* Associating the Custom Cell Renderer to SpreadsheetGrid

**Create a DataTemplate**

Create a custom DataTemplate (For ex: Button Template) in the Main window.xaml file,

{% tabs %}
{% highlight xaml %}
<DataTemplate x:Key="ButtonTemplate" >
<Expander x:Name="Button" ExpandDirection="Right" IsExpanded="True" 
   Expanded="Button_Expanded" Collapsed="Button_Collapsed"/>
</DataTemplate>
{% endhighlight %}
{% endtabs %}

**Override the SpreadsheetColumn class**

Create an extension class SpreadsheetColumnExt by overriding the [SpreadsheetColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetColumn.html) Class which holds all the operations related with cells.

Now override the function `OnUpdateColumn` which updates the column properties (cell types, renderer, cell element, etc.) and get the data template which is used for displaying in the particular cell.

{% tabs %}
{% highlight c# %}
public class SpreadsheetColumnExt : SpreadsheetColumn
{

    public SpreadsheetColumnExt(SpreadsheetGrid grid) : base(grid)
    {

    }

// Gets or sets the DataTemplate for the cell

public DataTemplate CellItemTemplate
{
  get;
  set;
}

// Gets or sets the DataTemplate for the cell
public DataTemplate CellEditTemplate
{
  get;
  set;
}

//Update the cell with the defined template

protected override void OnUpdateColumn(out FrameworkElement oldElement)
{

   if (RowIndex == 3 && ColumnIndex == 6)
   {
    this.CellItemTemplate = Application.Current.MainWindow.Resources["ButtonTemplate"] as DataTemplate;
    this.CellEditTemplate = Application.Current.MainWindow.Resources["ButtonTemplate"] as DataTemplate;
   }
base.OnUpdateColumn(out oldElement);
}
}
{% endhighlight %}
{% endtabs %}

**Create the Custom Cell Renderer**

Create a SpreadsheetTemplateCellRenderer class by overriding the [SpreadsheetVirtualizingCellRendererBase](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.CellRenderer.SpreadsheetVirtualizingCellRendererBase%602.html) class to display the defined custom renderer element.

For initializing the display element, set the content template in `OnInitializeDisplayElement` method and for editing, set the content template in `OnInitializeEditElement` method otherwise it will load the default display and edit element in the cells

{% tabs %}
{% highlight c# %}
public class SpreadsheetTemplateCellRenderer : SpreadsheetVirtualizingCellRendererBase<ContentControl, ContentControl>
{

    public SpreadsheetTemplateCellRenderer()
    {
        SupportDrawingOptimization = false;
    }

//Update the cell style for display element

protected override void OnUpdateCellStyle(RowColumnIndex cellRowColumnIndex, ContentControl uiElement, SpreadsheetColumn column)
{
	
    if (uiElement.ContentTemplate == null)
    {
      uiElement.ContentTemplate = (column as SpreadsheetColumnExt).CellItemTemplate;
    }
    base.OnUpdateCellStyle(cellRowColumnIndex, uiElement, column);
}

//Update the cell style for edit element

protected override void OnUpdateEditCellStyle (RowColumnIndex cellRowColumnIndex, ContentControl uiElement, SpreadsheetColumn column)
{

    if (uiElement.ContentTemplate == null)
    {
      uiElement.ContentTemplate = (column as SpreadsheetColumnExt).CellEditTemplate;
    }
    base.OnUpdateEditCellStyle (cellRowColumnIndex, uiElement, column);
}

//To initialize the display element on the cell

protected override void OnInitializeDisplayElement(RowColumnIndex rowColumnIndex, ContentControl uiElement, SpreadsheetColumn column) 
{
    uiElement.ContentTemplate = (column as SpreadsheetColumnExt).CellItemTemplate;
}

//To initialize the edit element on the cell

protected override void OnInitializeEditElement(RowColumnIndex rowColumnIndex, ContentControl uiElement, SpreadsheetColumn column)
{      
    uiElement.ContentTemplate = (column as SpreadsheetColumnExt).CellEditTemplate;
}
}
{% endhighlight %}
{% endtabs %}

N> If you want to load the default edit element, then no need to override the `OnInitializeEditElement` method.

**Associating the Custom Cell Renderer to SpreadsheetGrid**

To associate the custom cell renderer in [SpreadsheetGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html), invoke the [WorkbookLoaded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html) Event of SfSpreadsheet and initialize the SpreadsheetTemplateCellRenderer and add it to the renderer collection. 

Invoke the [QueryRange](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html) Event of `SpreadsheetGrid` and set the CellType of particular range to be “DataTemplate” to load the user defined template.

{% tabs %}
{% highlight c# %}
void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{
   var grid = spreadsheet.ActiveGrid;
   grid.CreateGridColumn = CreateSpreadsheetColumnExt;
   var renderer = new SpreadsheetTemplateCellRenderer();
   grid.CellRenderers.Add("DataTemplate", renderer);
   grid.QueryRange += grid_QueryRange;
}

//To access the SpreadsheetColumnExt

public GridColumn CreateSpreadsheetColumnExt(SfCellGrid grid)
{
   return new SpreadsheetColumnExt(grid as SpreadsheetGrid);
}

//To update the cell type
void grid_QueryRange(object sender, SpreadsheetQueryRangeEventArgs e)
{
 
  if (e.Cell.ColumnIndex == 6)
  {
    e.CellType = "DataTemplate";
    e.CellValue = "0";
    e.Handled = true;
  }
}
{% endhighlight %}
{% endtabs %}

For more reference, please find the [customization](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Cell_Customization-850724053) sample.


N> You can refer to our [WPF Spreadsheet](https://www.syncfusion.com/wpf-controls/spreadsheet) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Spreadsheet example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the spreadsheet.