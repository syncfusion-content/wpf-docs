---
layout: post
title: Excel-Importing
description: excel importing
platform: wpf
control: Grid Control
documentation: ug
---

# Excel Importing

Essential Grid WPF provides an in-built support for Excel Importing. This feature allows you to import the Excel Workbook into a GridControl, while preserving styles, formulas, named ranges, conditional formatting, freezing pane and bookmarks.

* Importing Styles—Imports the font family, font size, font style, font weight, cell backgrounds and cell foreground.
* Importing Formulas—Imports all the formulas from the excel sheet to the GridControl. GridControl also supports the cross reference formulas as in the excel.
* Importing Conditional formatting—imports the conditional formatting (Highlight Selection Rules – Greater then, Less than, Between, Equal to, Greater than or equal to, Less than or Equal to) from the Excel workbook to grid control.
* Import the freeze pane—imports the frozen row and frozen columns to GridControl.
* Imports the Hyperlink—imports the hyperlinks (Url and the worksheet navigation) to GridControl.
* Improving Performance—Excel Importing feature supports the virtualization. By using this you can optimize the performance.
* Run-time Features—Imports the comments from the excel worksheet to GridControl.

Use Case Scenarios

This feature can be used to view the Excel workbook into applications with the same set of styles and to edit the data in run time. You can also view the Excel workbook into web application with the same set of styles and borders.

Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio XX.X.X.XX -> Dashboard.
2. Select   Run Locally Installed Samples in WPF Button.
3. Now expand the Import item in the Sample Browser.
4. Choose the Excel Import samples to launch. 



## Tables for Properties, Methods, and Events

Methods

_Methods Table_

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
<th>
ImportFromExcel</th><th>
This method is used to import the first sheet from the stream.</th><th>
ImportFromExcel(Stream fileStream)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ImportFromExcel</th><th>
This method is used to import the first sheet from the stream. With the importing event handler.</th><th>
ImportFromExcel(Stream fileStream, GridCellImportFromExcelHandler importHandler)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ImportFromExcel</th><th>
This method is used to import the first sheet from the specified Excel file.</th><th>
ImportFromExcel(string filename)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ImportFromExcel</th><th>
This method is used to import the first sheet from the specified Excel file with the importing event handler.</th><th>
ImportFromExcel(string filename, GridCellImportFromExcelHandler importHandler)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ImportFromExcel</th><th>
This method is used to import the particular sheet from the IWorksheet.</th><th>
ImportFromExcel(IWorksheet sheet)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ImportFromExcel</th><th>
This method is used to import the particular sheet from the IWorksheet With the importing event handler.</th><th>
ImportFromExcel(IWorksheet sheet, GridCellImportFromExcelHandler importHandler)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ImportFromExcel</th><th>
This method is used to import the list of particular worksheets into GridModel array. ArrayIndexes contains the list of worksheet indexes to be imported.</th><th>
ImportFromExcel (string filename, int[] arrayIndexes, GridModel[] arrayModel)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ImportFromExcel</th><th>
This method is used to import the list of particular worksheets into GridModel array with the importing event handler.</th><th>
ImportFromExcel (string filename, int[] arrayIndexes, GridModel[] arrayModel, GridCellImportFromExcelHandler importHandler)</th><th>
NA</th><th>
Void</th><th>
NA</th></tr>
<tr>
<th>
ImportFromExcelToVirtualGrid</th><th>
This method imports the entire workbook styles to the virtual GridControl</th><th>
ImportFromExcelToVirtualGrid (IWorkbook book)</th><th>
</th><th>
GridModel[]</th><th>
NA</th></tr>
<tr>
<th>
ImportFromExcelToVirtualGrid</th><th>
This method imports the entire workbook styles to the virtual GridControl With the importing event handler.</th><th>
ImportFromExcelToVirtualGrid (IWorkbook book, GridCellImportFromExcelHandeler importHandler)</th><th>
</th><th>
GridModel[]</th><th>
NA</th></tr>
<tr>
<th>
ConvertExcelRangeToVirtualGrid</th><th>
This method imports a particular range of cells to the virtual GridControl</th><th>
ConvertExcelRangeToVirtualGrid(GridStyleInfo cell,IWorksheet sheet,IRange excelRange, GridCellImportFromExcelHandler importHandler)</th><th>
</th><th>
void</th><th>
NA</th></tr>
</table>
Events

_Event Table_

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th><th>
Reference links </th></tr>
<tr>
<th>
GridCellImportFromExcelHandler</th><th>
For triggering this event you have to pass the event handler method ImportFromExcel or in ConvertExcelRangeToVirtualGrid.This event is triggered while importing the each Excel cell to Grid cells.If the user handles this event for a particular set of ranges by using the e.Handle argument then the grid cell will only have the user defined style.</th><th>
ImportHandler(object sender, ImportingCellFromExcelEventArgs e)</th><th>
NA</th><th>
NA</th></tr>
</table>
##  Adding Excel Importing to an Application 

You can Import the entire Excel Spreadsheet to a GridControl. You can also import the Excel97to2003 and Excel2007to2010 formats

Importing the single sheet to a GridControl

In order to import the single sheet to grid control, open the file and pass this file as stream to the ImportFromExcel method as illustrated in the following code snippet:



[C#]

FileStream fileStream = new FileStream(@"..\..\Data\Sample.xlsx", FileMode.Open);

byte[] file = new byte[fileStream.Length];

fileStream.Read(file, 0, (int)fileStream.Length);

fileStream.Close();

this.gridControl.Model.ImportFromExcel(new MemoryStream(file));





Importing the entire workbook to a GridControl

Open the workbook

To import the entire workbook to a GridControl, initially you have to open the workbook by using the XLSIO library as shown in the following code snippet:



[C#]

FileStream fileStream = new FileStream(@"..\..\Data\Sample.xlsx", FileMode.Open);

byte[] file = new byte[fileStream.Length];

fileStream.Read(file, 0, (int)fileStream.Length);

fileStream.Close();

ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

IWorkbook workbook = application.Workbooks.Open(new MemoryStream(file), ExcelOpenType.Automatic);





Import the workbook into GridModel

After opening the workbook, you can import the workbook to GridModel by using the ImportFromExcel method. It will return the model collection; you can use it in your application. It will import all the styles, Conditional Formatting, Data Validation and book marks to model. While using this method it will take some time to import all the styles into models. 

For importing the workbook you can use the following code snippet.



[C#]

GridModel[] modelCollection = GridModelImportExtensions.ImportFromExcel(workBook);





Importing the entire workbook to a virtual GridControl

Open the workbook

To import the entire workbook to a virtual GridControl, initially you have to open the workbook by using the XLSIO library as shown in the following code snippet. 



[C#]

FileStream fileStream = new FileStream(@"..\..\Data\Sample.xlsx", FileMode.Open);

byte[] file = new byte[fileStream.Length];

fileStream.Read(file, 0, (int)fileStream.Length);

fileStream.Close();

ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

IWorkbook workbook = application.Workbooks.Open(new MemoryStream(file), ExcelOpenType.Automatic);





Import the layout into GridModel

After that you can import the workbook by using the ImportFromExcelToVirtualGrid method it will return the model collection. GridModel have only the layout styles, to import the other styles and data for cells you have to use the ConvertExcelRangeToVirtualGrid method.



[C#]

GridModel[] modelCollection = GridModelImportExtensions.ImportFromExcelToVirtualGrid(workBook);





Import data into GridModel

To load the data in grid cells, you have to use the ConvertExcelRangeToVirtualGrid method, this will import the formulas, cellvalue, conditional formats, data validation and the styles from the excel range to grid cells. To import the data into cells you can call the ConvertExcelRangeToVirtualGrid method in Querycellinfo Event as shown in the following code snippet:



[C#]

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

## How To

### Change the CellType while importing the Workbook?

You can also change the cell type and other styles while importing the workbook to GridControl, for that you have to pass the delegate handler in the importing method as shown in the following code snippet.



[C#]

this.gridControl.Model.ImportFromExcel(new MemoryStream(file), ImportHandler);





Then by using the ImportHandler method you can change the particular Cell Type and styles like background and font styles. When this event was handled, it will not import the data from the excel cell only the user specified data will be applied in the Grid. You can change the cell type as shown in the following code snippet 



[C#]

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



### Enable the ExcelLikeFrozen Row and Column in a GridControl

To enable the thick borders to indicate the Excel like freeze panes, you have to set the ExcelLikeFreezePane property as true as show in the following code snippet.



[C#]

grid.Model.Options.ExcelLikeFreezePane = true;



### Enable the comment service in GridControl

To enable the comment service you have to set the attached property show comment service as true as shown in the following code snippet.



[C#]

GridCommentService.SetShowComment(grid, true);





