---
layout: post
title: Import from Excel in WPF GridControl | Syncfusion
description: Learn about Import from Excel support in Syncfusion Essential Studio WPF GridControl, its elements and more details.
platform: wpf
control: GridControl
documentation: ug
---

# Import from Excel in WPF GridControl

Essential Grid WPF provides an in-built support for Excel Importing. This feature allows you to import the Excel Workbook into a GridControl, while preserving styles, formulas, named ranges, conditional formatting, freezing pane and bookmarks.

* Importing Styles—Imports the font family, font size, font style, font weight, cell backgrounds and cell foreground.
* Importing Formulas—Imports all the formulas from the excel sheet to the GridControl. GridControl also supports the cross reference formulas as in the excel.
* Importing Conditional formatting—imports the conditional formatting (Highlight Selection Rules – Greater then, Less than, Between, Equal to, Greater than or equal to, Less than or Equal to) from the Excel workbook to grid control.
* Import the freeze pane—imports the frozen row and frozen columns to GridControl.
* Imports the Hyperlink—imports the hyperlinks (Url and the worksheet navigation) to GridControl.
* Improving Performance—Excel Importing feature supports the virtualization. By using this you can optimize the performance.
* Run-time Features—Imports the comments from the excel worksheet to GridControl.

The following assemblies are needs to be added for importing the Excel to GridControl.

* Syncfusion.GridConverter.WPF
* Syncfusion.XlsIO.Base


You can get the [GridModelImportExtensions](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.Converter.GridModelImportExtensions.html) class and it's importing methods under the namespace [Syncfusion.Windows.Controls.Grid.Converter](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.Converter.html).

## Use Case Scenarios

This feature can be used to view the Excel workbook into applications with the same set of styles and to edit the data in run time. You can also view the Excel workbook into web application with the same set of styles and borders.

N> Download demo application from [GitHub](https://github.com/syncfusion/wpf-demos/tree/master/gridcontrol/Import/ExcelImport)



## Tables for Properties, Methods, and Events

### Methods



<table>
<tr>
<th>
Method </th><th>
Description </th><th>
Parameters </th><th>
Type </th><th>
Return Type </th><th>
Reference links </th></tr>
<tr>
<td>
ImportFromExcel</td><td>
this method is used to import the first sheet from the stream.</td><td>
ImportFromExcel(Stream fileStream)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ImportFromExcel</td><td>
this method is used to import the first sheet from the stream. With the importing event handler.</td><td>
ImportFromExcel(Stream fileStream, GridCellImportFromExcelHandler importhandler)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ImportFromExcel</td><td>
this method is used to import the first sheet from the specified Excel file.</td><td>
ImportFromExcel(string filename)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ImportFromExcel</td><td>
this method is used to import the first sheet from the specified Excel file with the importing event handler.</td><td>
ImportFromExcel(string filename, GridCellImportFromExcelHandler importhandler)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ImportFromExcel</td><td>
this method is used to import the particular sheet from the IWorksheet.</td><td>
ImportFromExcel(IWorksheet sheet)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ImportFromExcel</td><td>
this method is used to import the particular sheet from the IWorksheet With the importing event handler.</td><td>
ImportFromExcel(IWorksheet sheet, GridCellImportFromExcelHandler importhandler)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ImportFromExcel</td><td>
this method is used to import the list of particular worksheets into GridModel array. ArrayIndexes contains the list of worksheet indexes to be imported.</td><td>
ImportFromExcel (string filename, int[] arrayIndexes, GridModel[] arrayModel)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ImportFromExcel</td><td>
this method is used to import the list of particular worksheets into GridModel array with the importing event handler.</td><td>
ImportFromExcel (string filename, int[] arrayIndexes, GridModel[] arrayModel, GridCellImportFromExcelHandler importhandler)</td><td>
NA</td><td>
Void</td><td>
NA</td></tr>
<tr>
<td>
ImportFromExcelToVirtualGrid</td><td>
this method imports the entire workbook styles to the virtual GridControl</td><td>
ImportFromExcelToVirtualGrid (IWorkbook book)</td><td>
</td><td>
GridModel[]</td><td>
NA</td></tr>
<tr>
<td>
ImportFromExcelToVirtualGrid</td><td>
this method imports the entire workbook styles to the virtual GridControl With the importing event handler.</td><td>
ImportFromExcelToVirtualGrid (IWorkbook book, GridCellImportFromExcelHandler importhandler)</td><td>
</td><td>
GridModel[]</td><td>
NA</td></tr>
<tr>
<td>
ConvertExcelRangeToVirtualGrid</td><td>
this method imports a particular range of cells to the virtual GridControl</td><td>
ConvertExcelRangeToVirtualGrid(GridStyleInfo cell,IWorksheet sheet,IRange excelRange, GridCellImportFromExcelHandler importhandler)</td><td>
</td><td>
void</td><td>
NA</td></tr>
</table>

### Events



<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th><th>
Reference links </th></tr>
<tr>
<td>
GridCellImportFromExcelHandler</td><td>
For triggering this event you have to pass the event handler method ImportFromExcel or in ConvertExcelRangeToVirtualGrid.this event is triggered while importing the each Excel cell to Grid cells.If the user handles this event for a particular set of ranges by using the e.Handle argument then the grid cell will only have the user defined style.</td><td>
Importhandler(object sender, ImportingCellFromExcelEventArgs e)</td><td>
NA</td><td>
NA</td></tr>
</table>

##  Adding Excel Importing to an Application 

You can Import the entire Excel Spreadsheet to a GridControl. You can also import the Excel97to2003 and Excel2007to2010 formats

In order to import the single sheet to grid control, open the file and pass this file as stream to the ImportFromExcel method as illustrated in the following code snippet:

{% tabs %}
{% highlight c# %}
FileStream fileStream = new FileStream(@"..\..\Data\Sample.xlsx", FileMode.Open);
byte[] file = new byte[fileStream.Length];
fileStream.Read(file, 0, (int)fileStream.Length);
fileStream.Close();
this.gridControl.Model.ImportFromExcel(new MemoryStream(file));
{% endhighlight  %}
{% endtabs %}


### Importing the entire workbook to a GridControl

To import the entire workbook to a GridControl, initially you have to open the workbook by using the XlsIO library as shown in the following code snippet:

{% tabs %}
{% highlight c# %}
FileStream fileStream = new FileStream(@"..\..\Data\Sample.xlsx", FileMode.Open);
byte[] file = new byte[fileStream.Length];
fileStream.Read(file, 0, (int)fileStream.Length);
fileStream.Close();
ExcelEngine excelEngine = new ExcelEngine();
IApplication application = excelEngine.Excel;
IWorkbook workbook = application.Workbooks.Open(new MemoryStream(file), ExcelOpenType.Automatic);
{% endhighlight  %}
{% endtabs %}

### Import the workbook into GridModel

After opening the workbook, you can import the workbook to GridModel by using the ImportFromExcel method. It will return the model collection; you can use it in your application. It will import all the styles, Conditional Formatting, Data Validation and book marks to model. While using this method it will take some time to import all the styles into models. 

For importing the workbook you can use the following code snippet.

{% tabs %}
{% highlight c# %}
GridModel[] modelCollection = GridModelImportExtensions.ImportFromExcel(workBook);
{% endhighlight  %}
{% endtabs %}

### Importing the entire workbook to a virtual GridControl

To import the entire workbook to a virtual GridControl, initially you have to open the workbook by using the XlsIO library as shown in the following code snippet. 

{% tabs %}
{% highlight c# %}
FileStream fileStream = new FileStream(@"..\..\Data\Sample.xlsx", FileMode.Open);
byte[] file = new byte[fileStream.Length];
fileStream.Read(file, 0, (int)fileStream.Length);
fileStream.Close();
ExcelEngine excelEngine = new ExcelEngine();
IApplication application = excelEngine.Excel;
IWorkbook workbook = application.Workbooks.Open(new MemoryStream(file), ExcelOpenType.Automatic);
{% endhighlight  %}
{% endtabs %}

### Import the layout into GridModel

After that you can import the workbook by using the ImportFromExcelToVirtualGrid method it will return the model collection. GridModel have only the layout styles, to import the other styles and data for cells you have to use the ConvertExcelRangeToVirtualGrid method.

{% tabs %}
{% highlight c# %}
GridModel[] modelCollection = GridModelImportExtensions.ImportFromExcelToVirtualGrid(workBook);
{% endhighlight  %}
{% endtabs %}

### Import data into GridModel

To load the data in grid cells, you have to use the ConvertExcelRangeToVirtualGrid method, this will import the formulas, cell value, conditional formats, data validation and the styles from the excel range to grid cells. To import the data into cells you can call the ConvertExcelRangeToVirtualGrid method in QueryCellInfo Event as shown in the following code snippet:

{% tabs %}
{% highlight c# %}
void Model_QueryCellInfo(object sender, GridQueryCellInfoEventArgs e)
{
GridModel gridModel = sender as GridModel;

if (!e.Style.IsChanged)
{
int index = modelCollection.ToList().IndexOf(gridModel);
IWorksheet sheet = workBook.Worksheets[index];

if (sheet != null)
{
IRange range = sheet.Range;

if (e.Cell.RowIndex >= range.Row && e.Cell.ColumnIndex >= range.Column)
{
IRange rangeToConvert = sheet.Range[e.Cell.RowIndex, e.Cell.ColumnIndex];
GridModelImportExtensions.ConvertExcelRangeToVirtualGrid(e.Style, sheet, rangeToConvert, null);
gridModel.Data[e.Cell.RowIndex, e.Cell.ColumnIndex] = e.Style.Store;
}
}
}
}
{% endhighlight  %}
{% endtabs %}

## How To

### Change the CellType while importing the Workbook?

You can also change the cell type and other styles while importing the workbook to GridControl, for that you have to pass the delegate handler in the importing method as shown in the following code snippet.

{% tabs %}
{% highlight c# %}
this.gridControl.Model.ImportFromExcel(new MemoryStream(file), ImportHandler);
{% endhighlight  %}
{% endtabs %}

Then by using the ImportHandler method you can change the particular Cell Type and styles like background and font styles. When this event was handled, it will not import the data from the excel cell only the user specified data will be applied in the Grid. You can change the cell type as shown in the following code snippet 

{% tabs %}
{% highlight c# %}
private void ImoprtHandeler(object sender, ImportingCellFromExcelEventArgs e)
{

if (e.Range.AddressLocal == "C5")
{
e.Cell.CellType = "Static";
e.Cell.CellValue = e.Range.DisplayText;
e.Cell.Background = new SolidColorBrush(Colors.Blue);
e.Cell.Font.FontSize = 15;
e.Cell.Font.FontWeight = FontWeights.Bold;
e.Handled = true;
}
}
{% endhighlight  %}
{% endtabs %}

### Enable the ExcelLikeFrozen Row and Column in a GridControl

To enable the thick borders to indicate the Excel like freeze panes, you have to set the ExcelLikeFreezePane property as true as show in the following code snippet.

{% tabs %}
{% highlight c# %}
grid.Model.Options.ExcelLikeFreezePane = true;
{% endhighlight  %}
{% endtabs %}

### Enable the comment service in GridControl

To enable the comment service you have to set the attached property show comment service as true as shown in the following code snippet.

{% tabs %}
{% highlight c# %}
GridCommentService.SetShowComment(grid, true);
{% endhighlight  %}
{% endtabs %}
