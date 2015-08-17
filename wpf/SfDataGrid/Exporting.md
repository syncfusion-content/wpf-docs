---
layout: post
title: Exporting
description: exporting
platform: wpf
control: SfDataGrid
documentation: ug
---

# Exporting

This section explains you how to Export the SfDatagrid to Excel and PDF file.

### Overview

SfDataGrid control provides support to Export data to Excel and PDF. It also provides support for Grouping, Filtering, Sorting, Paging and Details View when Exporting.

### Export to Excel

SfDataGrid control provides support to Export data to Excel and returns an ExcelEngine that contains the exported workbook.

The following assemblies are added along with the default DLLs.

* Syncfusion.SfGridConverter.WPF
* Syncfusion.XlsIO.Base

You can Export SfDatagrid to Excel by using the following extension methods present in the Syncfusion.UI.Xaml.Grid.Converter namespace.

* ExportCollectionToExcel
* ExportToExcel

#### ExportToExcel


The ExportToExcel method has the following overloads.

_Method Table_

<table>
<tr>
<td>
Method</td><td>
Overload</td><td>
Description</td></tr>
<tr>
<td>
ExportToExcel</td><td>
ExportToExcel(ICollectionViewAdv,excelExportingOptions)</td><td>
Exports data to Excel and returns an ExcelEngine with ExcelExportingOptions{{ '_-_' ' | markdownify }}that is used to set the Exporting options.</td></tr>
<tr>
<td>
ExportToExcel</td><td>
ExportToExcel(ICollectionViewAdv, excelExportingOptions,worksheet)</td><td>
Export data to Excel with ExcelExportingOptions and Worksheet.</td></tr>
</table>


You can Export data to Excel by using the ExportToExcel method by passing ExcelExportingOptions as an argument. The following code example illustrates exporting data to Excel using the ExportToExcel Method.


{% highlight C# %}

[C#]



// Creating an instance for ExcelExportingOptions that is passed as a parameter to the ExportToExcel method.

ExcelExportingOptions exportingOptions = new ExcelExportingOptions();

exportingOptions.ExportingEventHandler = exportingHandler;

exportingOptions.CellsExportingEventHandler = cellsExportingHandler;

exportingOptions.ChildExportingEventHandler = ChildExportingHandler;



// Exports Datagrid to Excel and returns ExcelEngine.

ExcelEngine excelEngine = dataGrid.ExportToExcel(dataGrid.View, exportingOptions);



// Gets the exported workbook from the ExcelEngine.

IWorkbook workBook = excelEngine.Excel.Workbooks[0];



// Saving the workbook.

SaveFileDialog sfd = new SaveFileDialog

{

    FilterIndex = 2,

    Filter = "Excel 97 to 2003 Files(*.xls)|*.xls|Excel 2007 to 2010 Files(*.xlsx)|*.xlsx"

};



if (sfd.ShowDialog() == true)

{

    using (Stream stream = sfd.OpenFile())

    {

        if (sfd.FilterIndex == 1)

            workBook.Version = ExcelVersion.Excel97to2003;

        else

            workBook.Version = ExcelVersion.Excel2010;

        workBook.SaveAs(stream);                        

    }

}

{% endhighlight %}

ExcelExportingOptions has various properties and delegate handlers to customize the exporting behavior as compared to ExportCollectionToExcel.

The following screenshot displays the output for the DataGrid.



![](Features_images/Features_img202.png)


_DataGrid_

The following screenshot displays the exported excel sheet.



![](Features_images/Features_img203.png)



_Exported data in excel sheet_

The ExcelExportingOptions class has the following properties.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td><td>
DefaultValue</td></tr>
<tr>
<td>
AllowOutlining</td><td>
Boolean</td><td>
Specifies whether the groups exports with expand or collapse options or not.Indent space is not maintained when AllowOutlining is set to ‘true’. Default value is ‘{{ '_true_' | markdownify }}’.When the Grid contains the Details View definition, the AllowOutlining is set to ‘true’ internally.</td><td>
 True</td></tr>
<tr>
<td>
Excel Version</td><td>
ExcelVersion</td><td>
Exports data to Excel in the specificed workbook version:<br>ExcelVersion.Excel2007<br>ExcelVersion.Excel2010<br>ExcelVersion.Excel2013<br>ExcelVersion.Excel97to2003</td><td>
Excel2007</td></tr>
<tr>
<td>
ExportAllPages</td><td>
 Boolean</td><td>
A boolean variable that determines whether the method exports all the pages. By default, it exports the first page only.</td><td>
    False</td></tr>
<tr>
<td>
StartRowIndex</td><td>
  Integer</td><td>
Exports data to the specified row index in Excel.</td><td>
    1</td></tr>
<tr>
<td>
StartColumnIndex</td><td>
  Integer</td><td>
Exports data to the specified column index in Excel.</td><td>
    1</td></tr>
<tr>
<td>
ExcludeColumns</td><td>
List&lt;String&gt; </td><td>
Skips the exporting of list of columns whose MappingName is added to the ExcludeColumns list.</td><td>
 Empty</td></tr>
<tr>
<td>
ExportMode</td><td>
 ExportMode</td><td>
Specifies how the data is exported into excel. This is an Enum type.ExportMode.Text   - Exports the FormattedText to ExcelExportMode.Value - Exports the Format into Excel by setting Excel number format. It is the default value.</td><td>
  Value</td></tr>
<tr>
<td>
ExportPageOptions</td><td>
 ExportPageOptions.</td><td>
Specifies how the page collection is exported into excel. This is an Enum type.ExportPageOptions. ExportToSingleSheet        - Export all pages into Single sheet. This is the default value.ExportPageOptions. ExportToDifferentSheets - Export each page into different sheets (For this case, Grouping is considered).</td><td>
  ExportToSingleSheet</td></tr>
<tr>
<td>
ExportingEventHandler</td><td>
 GridExcelExportingEventhandler</td><td>
Delegate handler customizes the styles for Header, Table Summary, Group Summary and Caption Summary rows.</td><td>
   -</td></tr>
<tr>
<td>
CellsExportingEventHandler</td><td>
GridCellExcelExportingEventhandler</td><td>
Delegate handler handles or customizes the exporting of a particular cell in Excel.</td><td>
  -</td></tr>
<tr>
<td>
ChildExportingEventHandler</td><td>
GridChildExportingEventhandler</td><td>
Delegate handler customizes the exporting of Details View.</td><td>
  -</td></tr>
</table>

#### ExportCollectionToExcel

The ExportCollectionToExcel method has the following overloads.

_Method Table_

<table>
<tr>
<td>
Method</td><td>
Overload</td><td>
Description</td></tr>
<tr>
<td>
ExportCollectionToExcel</td><td>
ExportCollectionToExcel(this SfDataGrid grid, ICollectionViewAdv gridCollectionView)</td><td>
<br>Exports data to Excel and returns an ExcelEngine. The default Excel version is Excel2007.</td></tr>
<tr>
<td>
ExportCollectionToExcel</td><td>
ExportCollectionToExcel(this SfDataGrid grid, ICollectionViewAdv gridCollectionView, ExcelVersion excelVersion)</td><td>
Exports data to Excel in the specified workbook version:<br>* ExcelVersion.Excel2007<br>* ExcelVersion.Excel2010<br>* ExcelVersion.Excel2013<br>* ExcelVersion.Excel97to2003<br></td></tr>
<tr>
<td>
ExportCollectionToExcel</td><td>
ExportCollectionToExcel(this SfDataGrid grid, ICollectionViewAdv gridCollectionView, ExcelVersion excelVersion, GridExcelExportingEventhandler exportingHandler, GridCellExcelExportingEventHandler cellsExportingHandler, bool exportAllPages)</td><td>
Exports data to Excel, and provides options to customize Exporting using the following parameters:<br>* GridExcelExportingEventhandler – A delegate type of GridExcelExportingEventhandler.<br>* GridCellExcelExportingEventHandler – A delegate type of GridCellExcelExportingEventHandler.<br>* ExportAllPages – A boolean variable that specifies whether all pages are exported or not. By default, it exports the first page only.<br></td></tr>
</table>


The following code example illustrates how to export data to Excel by using the ExportCollectionToExcel method. The ExportCollectionToExcel method returns the ExcelEngine that contains the exported workbook. You can save the workbook as a stream or file by using SaveFileDialog.


{% highlight C# %}

[C#]



ExcelEngine excelEngine = this.sfGrid.ExportCollectionToExcel(sfGrid.View);



// Gets the exported workbook from the ExcelEngine.

IWorkbook workBook = excelEngine.Excel.Workbooks[0];



// Saving the workbook.

SaveFileDialog sfd = new SaveFileDialog

{

    FilterIndex = 2,

    Filter = "Excel 97 to 2003 Files(*.xls)|*.xls|Excel 2007 to 2010 Files(*.xlsx)|*.xlsx"

};



if (sfd.ShowDialog() == true)

{

    using (Stream stream = sfd.OpenFile())

    {

        if (sfd.FilterIndex == 1)

            workBook.Version = ExcelVersion.Excel97to2003;

        else

            workBook.Version = ExcelVersion.Excel2010;

        workBook.SaveAs(stream);                        

    }

}
{% endhighlight %}

#### Delegate Event Handlers

ExportToExcel and ExportCollectionToExcel provide the following delegate handlers to customize the exporting behavior.

* GridExcelExportingEventHandler
* GridCellExcelExportingEventHandler
* GridChildExportingEventHandler



##### GridExcelExportingHandler

This delegate handler allows you to customize the styles for Headers, Table Summary, Group Summary and Caption Summary rows. It includes the GridExcelExportingEventArgs event data class that contains the following properties.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
CellType(ReadOnly property)</td><td>
 ExportCellType</td><td>
Specifies the cell type by using ExportCellType Enum. You can use this property to check the cell type and apply different cell styles based on the cell type.Cell types are as follows:<br>* ExportCellType.GroupCaptionCell<br>* ExportCellType.GroupSummaryCell* ExportCellType.HeaderCell<br>* ExportCellType.TableSummaryCell<br></td></tr>
<tr>
<td>
CellStyle</td><td>
 ExportCellStyle</td><td>
Customizes the Foreground, Background and Font of Header, Table Summary, Group Summary and Caption Summary rows.<br>* CellStyle.ForeGroundBrush<br>* CellStyle.BackGroundBrush<br>* CellStyle.FontInfo<br></td></tr>
<tr>
<td>
WorkSheet</td><td>
 IWorksheet</td><td>
Sets the Worksheet properties such as sheet protection, gridlines, and so on.</td></tr>
<tr>
<td>
Level</td><td>
  Integer</td><td>
Specifies the level of the currently exporting Grid when exporting Nested DataGrid. It is 0 for ParentGrid, 1 for First Level Nested DataGrid, and so on.</td></tr>
<tr>
<td>
Handled</td><td>
  Boolean</td><td>
Skips exporting of Group Summary, Table Summary and Header. For Caption Summary, it skips exporting the data alone (an empty row is created in Excel).</td></tr>
</table>


The following code example illustrates how to apply cell styles based on the cell type using GridExcelExportingHandler.


{% highlight C# %}

[C#]



ExcelExportingOptions exportingOptions = new ExcelExportingOptions();

exportingOptions.ExportingEventHandler = exportingHandler;

// Exports Datagrid to Excel and returns ExcelEngine.

ExcelEngine excelEngine = dataGrid.ExportToExcel(dataGrid.View, exportingOptions);



public void exportingHandler(object sender, GridExcelExportingEventArgs e)

{

// Checks if the CellType is HeaderCell.

if (e.CellType == ExportCellType.HeaderCell)

{

// Applying Style to the HeaderCell.

if (e.Level == 0)

{

e.CellStyle.BackGroundBrush = new SolidColorBrush(Colors.DarkGray);

e.CellStyle.ForeGroundBrush = new SolidColorBrush(Colors.White);

}

else

e.CellStyle.BackGroundBrush = new SolidColorBrush(Colors.LightGray);                

e.CellStyle.FontInfo.Bold = true; 

}

else if (e.CellType == ExportCellType.GroupCaptionCell)

{

e.CellStyle.BackGroundBrush = new SolidColorBrush(Colors.LightSlateGray);

e.CellStyle.ForeGroundBrush = new SolidColorBrush(Colors.LightYellow);

}

else if (e.CellType == ExportCellType.GroupSummaryCell)      

e.CellStyle.BackGroundBrush = new SolidColorBrush(Colors.LightGray);       

else if (e.CellType == ExportCellType.TableSummaryCell)       

e.CellStyle.BackGroundBrush = new SolidColorBrush(Colors.LightGray);       

}
{% endhighlight %}


The following screenshot displays the output for DataGrid.



![](Features_images/Features_img204.png)



_Applying cell styles based on the cell type using GridExcelExportingHandler._

The following screenshot displays the Exported excel sheet.



![](Features_images/Features_img205.png)



_Exported excel sheet_



##### GridCellExcelExportingHandler

A delegate handler handles or customizes a cell in Excel. It occurs for every exported cell. It includes the GridCellExcelExportingEventArgs event data class that contains the following properties.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
CellType(ReadOnly property)</td><td>
ExportCellType</td><td>
Specifies the cell type by using the ExportCellType enum. You can use this property to check the cell type and apply different cell styles based on the cell type.Cell types are as follows:<br>* ExportCellType.GroupCaptionCell<br>* ExportCellType.GroupSummaryCell<br>* ExportCellType.HeaderCell* ExportCellType.RecordCell<br>* ExportCellType.TableSummaryCell<br></td></tr>
<tr>
<td>
CellValue(ReadOnly property)</td><td>
 Object</td><td>
Contains the actual value that is exported to the Excel. You can use this value to apply formatting in Excel using Range property.</td></tr>
<tr>
<td>
ColumnName(ReadOnly property)</td><td>
 String</td><td>
Specifies the Column Name (MappingName) of the exporting cell. You can apply formatting for a particular column by checking the ColumnName.</td></tr>
<tr>
<td>
Handled</td><td>
 Boolean</td><td>
Determines whether the cell is exported to Excel or not.</td></tr>
<tr>
<td>
NodeEntry(ReadOnly property)</td><td>
 Object</td><td>
Contains the RecordEntry, GroupEntry, or SummaryEntry based on the type of row. You can access the underlying BusinessObject by using this property.</td></tr>
<tr>
<td>
Range</td><td>
 IRange</td><td>
Specifies the Excel range to be exported. It provides full access to the exporting cell in Excel.</td></tr>
<tr>
<td>
GridViewDefinition</td><td>
ViewDefinition</td><td>
For ParentGrid, it is null.You can access the properties of the Nested DataGrid by using this GridViewDefinition.</td></tr>
<tr>
<td>
Level</td><td>
 Integer</td><td>
Specifies the level of the currently exporting Grid when exporting Nested DataGrid. It is 0 for ParentGrid, 1 for First Level Nested DataGrid, and so on.</td></tr>
</table>


The following code example illustrates how to customize the font based on some criteria using GridCellExcelExportingHandler.


{% highlight C# %}

[C#]

ExcelExportingOptions exportingOptions = new ExcelExportingOptions();

exportingOptions.CellsExportingEventHandler = cellsExportingHandler;

// Exports Datagrid to Excel and returns ExcelEngine.

ExcelEngine excelEngine = dataGrid.ExportToExcel(dataGrid.View, exportingOptions);



public void cellsExportingHandler(object sender, GridCellExcelExportingEventArgs e)

{

// Sets the font style as Bold and Italic for the OrderID column of Parent Grid.

if (e.CellType == ExportCellType.RecordCell && e.ColumnName == "OrderID" && e.Level==0)

{

e.Range.CellStyle.Font.Bold = true;

e.Range.CellStyle.Font.Italic = true;

}

}
{% endhighlight %}


The following screenshot displays the output for DataGrid.



![](Features_images/Features_img206.png)



_Customized font using GridCellExcelExportingHandler_

The following screenshot displays the Exported excel sheet,

![](Features_images/Features_img207.png)



_Exported excel sheet_

##### GridChildExportingEventHandler

This handler allows you to skip the exporting of DetailsView Grid columns or the whole DetailsView Grid. It includes the GridChildExportingEventArgs event data class that contains the following properties.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
Relational Column</td><td>
String</td><td>
It is the Relational column of the Nested DataGrid. As this is unique one, you can use this property to identify the Nested DataGrid.</td></tr>
<tr>
<td>
NodeEntry</td><td>
Object</td><td>
It is the RecordEntry of the parent Grid. You can use this property to identify the particular Nested DataGrid in combination with Relational Column.</td></tr>
<tr>
<td>
Level</td><td>
Integer</td><td>
Specifies the level of the currently exporting Nested DataGrid. It is 1 for First level Nested DataGrid, 2 for Second Level child it will be 2, and so on.</td></tr>
<tr>
<td>
Cancel</td><td>
Boolean</td><td>
Skips the exporting of Nested DataGrid to Excel.</td></tr>
<tr>
<td>
ExcludeColumns</td><td>
List&lt;string&gt; </td><td>
Specifies the list of column names (MappingName) to be excluded when exporting to Excel.</td></tr>
</table>


The following code example illustrates how to skip the exporting of Details View Grid using ChildExportingHandler.


{% highlight C# %}

[C#]

ExcelExportingOptions exportingOptions = new ExcelExportingOptions();

exportingOptions.ChildExportingEventHandler = ChildExportingHandler;

// Exports Datagrid to Excel and returns ExcelEngine.

ExcelEngine excelEngine = dataGrid.ExportToExcel(dataGrid.View, exportingOptions);



private static void ChildExportingHandler(object sender, GridChildExportingEventArgs e)

{

// Remove the OrderID column from the Details View Grid while Exporting.

if (e.Level > 1)

e.ExcludeColumns.Add("OrderID");

}

{% endhighlight %}

The following screenshot displays the output for DataGrid.



![](Features_images/Features_img208.png)



_Skipped exporting of Details View Grid using ChildExportingHandler_

The following screenshot displays the exported excel sheet,



![](Features_images/Features_img209.png)



_Exported excel sheet_

### Export to PDF

SfDataGrid control provides support to Export its content into a PDF file. You can export Grouping, Sorting, Filtering, Paging, Summaries and Details view into PDF. 

The following assemblies are added along with default DLL’s.

* Syncfusion.SfGridConverter.WPF
* Syncfusion.Pdf.Base

The following extension methods present in the Syncfusion.UI.Xaml.Grid.converter namespace is used to export the SfDataGrid into PDF_._

_Method Table_

<table>
<tr>
<td>
Method</td><td>
Prototype</td><td>
Description</td></tr>
<tr>
<td>
ExportToPdf</td><td>
ExportToPdf (this SfDataGrid sfgrid)</td><td>
This Method exports the DataGrid into PDF and returns the PdfDocument</td></tr>
<tr>
<td>
ExportToPdf</td><td>
ExportToPdf (this SfDataGrid sfgrid, PdfExportingOptions pdfExportingOptions)</td><td>
This Method exports the DataGrid into PDF based on settings in the PdfExportingOptions and returns the PdfDocument</td></tr>
<tr>
<td>
ExportToPdf</td><td>
ExportToPdf (ICollectionViewAdv gridCollectionView, PdfExportingOptions pdfExportingOptions)</td><td>
This Method exports the specified CollectionView into PDF based on settings in the PdfExportingOptions and returns the PdfDocument</td></tr>
<tr>
<td>
ExportToPdfGrid</td><td>
ExportToPdfGrid (ICollectionViewAdv gridCollectionView, PdfExportingOptions pdfExportingOptions)</td><td>
This Method exports the specified CollectionView into PDF based on settings in the PdfExportingOptions and returns the PdfGrid</td></tr>
</table>


You can customize how the SfDataGrid content is exported into PDF by using various properties and delegate handlers in the PdfExportingOptions.

PdfExportingOptions has the following properties and delegate handlers.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td><td>
Default Value</td></tr>
<tr>
<td>
AutoColumnWidth</td><td>
 Boolean</td><td>
Determines whether the column widths are automatically calculated based on its content or not.</td><td>
 True</td></tr>
<tr>
<td>
AutoRowHeight</td><td>
 Boolean</td><td>
Determines whether the row heights are automatically calculated based on its content or not.</td><td>
 True</td></tr>
<tr>
<td>
ExcludeColumns</td><td>
 List&lt;string&gt;</td><td>
Skips the exporting of list of columns whose MappingName is added to this list.</td><td>
 Empty List</td></tr>
<tr>
<td>
ExportFormat</td><td>
 Boolean</td><td>
Determines whether the values are exported with format or not.</td><td>
 True</td></tr>
<tr>
<td>
ExportAllPages</td><td>
 Boolean</td><td>
Determines whether all the pages are exported or not. This property is applicable only for paged collection.When it is set to ‘false’, then only current page is exported.When it is set to ‘true’, then all pages are exported. For this case, grouping is not considered while exporting.</td><td>
 False</td></tr>
<tr>
<td>
ExportGroups</td><td>
 Boolean</td><td>
Determines whether groups are exported or not</td><td>
 True</td></tr>
<tr>
<td>
ExportGroupSummary</td><td>
 Boolean</td><td>
Determines whether the group summaries are exported or not</td><td>
 True</td></tr>
<tr>
<td>
ExportTableSummary</td><td>
 Boolean</td><td>
Determines whether the table summaries are exported or not</td><td>
 True</td></tr>
<tr>
<td>
ExportStackedHeaders</td><td>
 Boolean</td><td>
Determines whether the stacked headers are exported or not</td><td>
 False</td></tr>
<tr>
<td>
ExportDetailsView</td><td>
 Boolean</td><td>
Determines whether the Details view is exported or not. >{{ '_Note: When it is set to ‘true’, it exports the details view that are expanded._' | markdownify }} > {{ '_Limitation: While exporting Details view, FitAllColumnsInOnePage is set to ‘true’ internally as horizontal pagination is not supported for Nested Grid._' | markdownify }} </td><td>
 False</td></tr>
<tr>
<td>
ExportAllDetails</td><td>
 Boolean</td><td>
Determines whether Details view is exported or not when details view is not expanded.</td><td>
 False</td></tr>
<tr>
<td>
FitAllColumnsInOnePage</td><td>
 Boolean</td><td>
Determines whether all the columns are fit in a page or not</td><td>
 False</td></tr>
<tr>
<td>
RepeatHeaders</td><td>
 Boolean</td><td>
Determines whether the headers are repeated in each page or not</td><td>
 True</td></tr>
<tr>
<td>
ExportingEventHandler</td><td>
Delegate handler</td><td>
Customizes the styles for Header, Record, Table Summary, and Group Summary and Caption Summary rows.</td><td>
 Null</td></tr>
<tr>
<td>
CellsExportingEventHandler</td><td>
Delegate handler</td><td>
Handles or customizes the exporting of each cell.</td><td>
 Null</td></tr>
<tr>
<td>
ChildGridExportingEventHandler</td><td>
Delegate handler</td><td>
Handles or customizes the exporting of Details View.</td><td>
 Null</td></tr>
<tr>
<td>
PageHeaderFooterEventHandler</td><td>
Delegate handler</td><td>
Adds the header and footer of the PDF page.</td><td>
 Null</td></tr>
</table>


The following code example illustrates you how to export SfDataGrid into PDF by using the ExportToPdf method.


{% highlight C# %}

[C#]



var document = dataGrid.ExportToPdf();



SaveFileDialog sfd = new SaveFileDialog

{

    Filter = "PDF Files(*.Pdf)|*.Pdf"

};

if (sfd.ShowDialog() == true)

{

    using (Stream stream = sfd.OpenFile())

    {

        document.Save(stream);

    }



    //Message box confirmation to view the created PDF file.

    if (MessageBox.Show("Do you want to view the PDF file?", "PDF file has been created",

          MessageBoxButton.YesNo, MessageBoxImage.Information) ==        MessageBoxResult.Yes)

    {

        //Launching the PDF file using the default Application.

        System.Diagnostics.Process.Start(sfd.FileName);

    } 

}

{% endhighlight %}



The following screenshot displays the output for DataGrid.



![](Features_images/Features_img210.png)



_Exporting SfDataGrid into PDF using the ExportToPdf method._

The following screenshot displays the exported Pdf file.

![](Features_images/Features_img211.png)


_Exported Pdf file_

#### Delegate and Events

Export to Pdf provides the following delegate handler to customize the exporting behavior.

* GridPdfExportingEventhandler
* GridCellPdfExportingEventhandler
* ChildGridPdfExportingEventhandler
* PdfHeaderFooterEventHandler
##### GridPdfExportingEventhandler


This delegate handler allows you to customize the styles for Header, Records, Table Summary, Group Summary and Caption Summary rows. It is invoked for each row types. It includes the GridPdfExportingEventArgs class that contains the following properties.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
CellType</td><td>
 ExportCellType</td><td>
You can use this property to check the cell type and apply different cell styles based on the cell type.Cell types are as follows:* ExportCellType.GroupCaptionCell* ExportCellType.GroupSummaryCell* ExportCellType.HeaderCell* ExportCellType.RecordCell* ExportCellType.StackedHeaderCell* ExportCellType.TableSummaryCell* ExportCellType.TopTableSummaryCell<br></td></tr>
<tr>
<td>
CellStyle</td><td>
PdfGridCellStyle</td><td>
You can use this property to customize the Style (Foreground, Background, Font, Border etc.,) </td></tr>
<tr>
<td>
PdfGrid</td><td>
 PdfGrid</td><td>
You can use this property to customize the PdfGrid’s properties such as Background, CellPadding, CellSpacing etc.</td></tr>
<tr>
<td>
Level</td><td>
 Integer</td><td>
Specifies the level of the currently exporting Grid when exporting Nested DataGrid. It is 0 for ParentGrid, 1 for First Level Nested DataGrid, and so on.</td></tr>
</table>


The following code example illustrates how to apply cell styles based on the cell type by using GridPdfExportingEventHandler_._


{% highlight C# %}

[C#]



var options = new PdfExportingOptions();

options.ExportingEventHandler = GridPDFExportingEventhandler;

var document = dataGrid.ExportToPDF(options);



static void GridPDFExportingEventhandler(object sender, GridPdfExportingEventArgs e)

{

    if (e.CellType == ExportCellType.HeaderCell)

    {

        e.CellStyle.BackgroundBrush = PdfBrushes.LightSteelBlue;

    }

    else if (e.CellType == ExportCellType.GroupCaptionCell)

    {

        e.CellStyle.BackgroundBrush = PdfBrushes. Purple;

    }

    else if (e.CellType == ExportCellType.GroupSummaryCell)

    {

        e.CellStyle.BackgroundBrush = PdfBrushes.Azure;

    }

   }

{% endhighlight %}

The following screenshot displays the output for DataGrid.



![](Features_images/Features_img212.png)



_Cell styles based on the cell type using GridPdfExportingEventHandler._

The following screenshot displays the exported Pdf file.

![](Features_images/Features_img213.png)



_Exported Pdf file_



##### GridCellPdfExporting Eventhandler

This delegate handler allows you to handle or customize each cell in Pdf. It is invoked while exporting each cell. It includes the GridCellPdfExportingEventArgs class that contains the following properties.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
CellType</td><td>
 ExportCellType</td><td>
You can use this property to check the cell type and apply different cell styles based on the cell type.Cell types are as follows:* ExportCellType.GroupCaptionCell* ExportCellType.GroupSummaryCell* ExportCellType.HeaderCell* ExportCellType.RecordCell* ExportCellType.StackedHeaderCell* ExportCellType.TableSummaryCell* ExportCellType.TopTableSummaryCell<br></td></tr>
<tr>
<td>
CellValue</td><td>
 Object</td><td>
Contains the actual value that is exported to the PDF. You can also customize this value.</td></tr>
<tr>
<td>
ColumnName</td><td>
 String</td><td>
Specifies the Column Name (MappingName) of the exporting cell. You can customize the value for a particular column by checking the ColumnName.</td></tr>
<tr>
<td>
NodeEntry</td><td>
 Object</td><td>
Contains the RecordEntry or GroupEntry or SummaryEntry based on the type of row. You can access the underlying BusinessObject by using this property.</td></tr>
<tr>
<td>
PropertyAccessProvider</td><td>
IPropertyAccessProvider</td><td>
Contains the PropertyAccessProvider of the view. You can use this to get value of a cell using NodeEntry.</td></tr>
<tr>
<td>
GridViewDefinition</td><td>
 ViewDefinition</td><td>
It is the GridViewDefinition of the DataGrid. For ParentGrid, it is null.You can access the properties of the Nested DataGrid by using this GridViewDefinition.</td></tr>
<tr>
<td>
Level</td><td>
 Integer</td><td>
Specifies the level of the currently exporting Grid when exporting Nested DataGrid. It is 0 for ParentGrid, 1 for First Level Nested DataGrid, and so on.</td></tr>
<tr>
<td>
PdfGridCell</td><td>
 PdfGridCell</td><td>
Specifies the PDFGridCell to be exported. You can use this to customize the properties (Background, Foreground, Font, Alignment etc.,) of particular cell</td></tr>
<tr>
<td>
Handled</td><td>
 Boolean</td><td>
Determines whether the cell is exported to PDF or not.</td></tr>
</table>


The following code example illustrates how to customize the particular PDFGridCell based on some criteria by using GridCellPdfExportingEventhandler.


{% highlight C# %}

[C#]

var options = new PdfExportingOptions();

options.CellsExportingEventHandler = GridCellPDFExportingEventhandler;

var document = dataGrid.ExportToPDF(options);



var cellstyle = new PdfGridCellStyle();

cellstyle.StringFormat = new PdfStringFormat() { Alignment = PdfTextAlignment.Right };

var font = new Font("Segoe UI", 9f, System.Drawing.FontStyle.Regular);

cellstyle.Font = new PdfTrueTypeFont(font, true);

cellstyle.Borders.All = new PdfPen(PdfBrushes.DarkGray, 0.2f);



static void GridCellPDFExportingEventhandler(object sender, GridCellPdfExportingEventArgs e)

{

    if (e.CellType == ExportCellType.RecordCell && (e.ColumnName == "OrderID" || e.ColumnName == "EmployeeID"))

    {

        e.PDFGridCell.Style = cellstyle;

    }

}
{% endhighlight %}




The following screenshot displays the output for DataGrid.



![](Features_images/Features_img214.png)



_Customized PDFGridCell using GridCellPdfExportingEventhandler._

The following screenshot displays the exported PDF file.

![](Features_images/Features_img215.png)



_Exported PDF file_

##### ChildGridPdfExportingEventhandler

This handler allows you to skip or customize the exporting of DetailsViewGrid. It is invoked for each details view while exporting. It includes the ChildGridPdfExportingEventArgs that includes the following properties.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
RelationalColumn</td><td>
String</td><td>
It is the Relational column of the Nested DataGrid. You can use this property to identify the Nested DataGrid.</td></tr>
<tr>
<td>
NodeEntry</td><td>
Object</td><td>
It is the RecordEntry of the parent Grid. You can use this property to identify the particular Nested DataGrid in combination with Relational Column.</td></tr>
<tr>
<td>
Level</td><td>
Integer</td><td>
Specifies the level of the currently exporting Nested DataGrid. It is 1 for First level Nested DataGrid, 2 for Second Level child it will be 2, and so on.</td></tr>
<tr>
<td>
PdfExportingOptions</td><td>
PdfExportingOptions</td><td>
You can use this to customize the exporting behavior options for details view separately.</td></tr>
<tr>
<td>
Cancel</td><td>
Boolean</td><td>
Skips the exporting of Nested DataGrid to PDF.</td></tr>
</table>


The following code example illustrates how to skip and customize the exporting of Details View Grid by using ChildGridExportingHandler.


{% highlight C# %}

[C#]

var options = new PdfExportingOptions();

options.ExportDetailsView= true;

options.ChildGridExportingEventHandler = ChildGridPDFExportingEventhandler;

var document = dataGrid.ExportToPDF(options);

static void ChildGridPDFExportingEventhandler(object sender, ChildGridPdfExportingEventArgs e)

{

    //Skips the exporting of details view from second level

    if (e.Level > 1)

        e.Cancel = true;

    else

    {

        //skips the exporting of OrderID column of details view.

        e.PdfExportingOptions.ExcludeColumns = new List<string>() { "OrderID" };

    }

}

{% endhighlight %}

The following screenshot displays the output for DataGrid.

![](Features_images/Features_img216.png)



_Skipped and Customized exporting of Details View Grid using ChildGridExportingHandler._

The following screenshot displays the exported PDF file.



![](Features_images/Features_img217.png)





_Exported PDF file_

##### PdfHeaderFooterEventhandler

This handler allows you to add the Header and Footer to each page of exported PDF file. It is invoked only once while exporting SfDataGrid into PdfDocument using ExportToPdf method and it is not invoked while using ExportToPdfGrid method. It includes the PdfHeaderFooterEventArgs that contains the following properties.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
PdfPage</td><td>
PdfPage</td><td>
Stores the PDF page information (page width, height etc.). From this information, you can customize the Header and Footer template.</td></tr>
<tr>
<td>
PdfDocumentTemplate</td><td>
PdfDocumentTemplate</td><td>
Allows you to add the Header and Footer into the PdfDocument template.</td></tr>
</table>


The following code example illustrates how to add Header and Footer into the PDF document.


{% highlight C# %}

[C#]

var options = new PdfExportingOptions();

options.PageHeaderFooterEventHandler = PDFHeaderFooterEventHandler;

var document = dataGrid.ExportToPdf(options); 



static void PDFHeaderFooterEventHandler(object sender, PdfHeaderFooterEventArgs e)

{

    var width = e.PdfPage.GetClientSize().Width;



    PdfPageTemplateElement header = new PdfPageTemplateElement(width, 38);

    header.Graphics.DrawImage(PDFImage.FromFile(@"..\..\Resources\Header.jpg"), 0, 0, width / 3f, 34);

    e.PdfDocumentTemplate.Top = header;



    PdfPageTemplateElement footer = new PdfPageTemplateElement(width, 30);

    footer.Graphics.DrawImage(PdfImage.FromFile(@"..\..\Resources\Footer.jpg"), 0, 0);

    e.PdfDocumentTemplate.Bottom = footer;

}
{% endhighlight %}


The following screenshot displays you the exported PDF file.



![](Features_images/Features_img218.png)



_Exported PDF file_

#### How To

##### How to embedded fonts in PDF export

This feature provides support to embed your own fonts into exported Pdf file.You can create a new font from the font file and you can set that font into the Pdf by using the delegate handlers.

The following code example illustrates how to create font from the font file and set it into the PdfGridCell.


{% highlight C# %}

[C#]

static void GridPDFExportingEventhandler(object sender, GridPdfExportingEventArgs e)

{

    if(e.CellType == ExportCellType.RecordCell)

    {

        //creates a new font from the font file.

        var filePath = @"..\..\Resources\segoeui.ttf";

        var font = new PdfTrueTypeFont(filePath, 9f, PdfFontStyle.Regular);



        //assign that font to PDFGridCell

        e.CellStyle.Font = font;

    }

}
{% endhighlight %}

##### How to change PDF page orientation

You can change the page orientation of Pdf while exporting. The default page orientation is Portrait.

To change the page orientation, you can get the exported PdfGrid by using ExportToPdfGrid method and then draw that PdfGrid into a PdfDocument by changing the PageSettings.Orientation of PdfDocument.

The following code example illustrates how to change page orientation to Landscape.


{% highlight C# %}

[C#]

var options = new PdfExportingOptions();

var document = new PdfDocument();

document.PageSettings.Orientation = PdfPageOrientation.Landscape;

var page = document.Pages.Add();

var PDFGrid = dataGrid.ExportToPdfGrid(dataGrid.View, options);

var format = new PdfGridLayoutFormat()

{

    Layout = PdfLayoutType.Paginate,

    Break = PdfLayoutBreakType.FitPage

};



PDFGrid.Draw(page, new PointF(), format);



SaveFileDialog sfd = new SaveFileDialog

{

    Filter = "PDF Files(*.Pdf)|*.Pdf"

};



if (sfd.ShowDialog() == true)

{

    using (Stream stream = sfd.OpenFile())

    {

        document.Save(stream);

    }

}

{% endhighlight %}

The following screenshot displays the output for the above code,



![](Features_images/Features_img219.png)



_Changing Page orientation to Landscape_

