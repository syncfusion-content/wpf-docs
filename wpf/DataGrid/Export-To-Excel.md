---
layout: post
title: Export to Excel in WPF DataGrid control | Syncfusion
description: Learn about exporting datagrid to Excel support in Syncfusion WPF DataGrid (SfDataGrid) control and more details.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Export to Excel in WPF DataGrid (SfDataGrid)

DataGrid provides support to export data to excel. It also provides support for grouping, filtering, sorting, paging, unbound rows, merged cells, stacked headers and Details View while exporting.

The following assemblies needs to be added for exporting to excel.

* Syncfusion.SfGridConverter.WPF
* Syncfusion.XlsIO.Base

For NuGet package, have to install [Syncfusion.DataGridExcelExport.WPF](https://www.nuget.org/packages/Syncfusion.DataGridExcelExport.WPF) package. For more details refer this [UG link](https://help.syncfusion.com/wpf/control-dependencies#exporting-datagrid-to-excel-pdf-and-csv).

You can export SfDataGrid to excel by using the [ExportToExcel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.GridExcelExportExtension.html#Syncfusion_UI_Xaml_Grid_Converter_GridExcelExportExtension_ExportToExcel_Syncfusion_UI_Xaml_Grid_SfDataGrid_Syncfusion_Data_ICollectionViewAdv_Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_) extension method present in the [Syncfusion.UI.Xaml.Grid.Converter](http://help.syncfusion.com/cr/wpf) namespace.

{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid.Converter;
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

N> SfDataGrid exports data to excel by using [XlsIO](http://help.syncfusion.com/file-formats/xlsio/overview). You can refer [XlsIO documentation](http://help.syncfusion.com/file-formats/xlsio/working-with-excel-worksheet) for manipulating exported work sheets. 

## Excel exporting options

Exporting operation can be customized by passing [ExcelExportingOptions](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html) instance as argument to `ExportToExcel` method. 

### Export mode

By default, actual value only will be exported to excel. If you want to export the display text, you need to set [ExportMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ExportMode) property as `Text`. 

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExportMode = ExportMode.Text;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

### Export groups with outlines

By default, all the groups in dataGrid will be exported in expanded state. You can enable outlines in excel based on groups by setting the [AllowOutlining](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_AllowOutlining) property as `true` in [ExcelExportingOptions](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html). 

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.AllowOutlining = true;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

![Exporting to excel with outlines for groups in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img1.png)

### Exclude columns while exporting

By default, all the columns (including hidden columns) in SfDataGrid will be exported to Excel. If you want to exclude some columns while exporting to Excel, you can use [ExcludeColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ExcludeColumns) field in [ExcelExportingOptions](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html).

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcludeColumns.Add("CustomerName");
options.ExcludeColumns.Add("Country");
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

Here, the columns having `CustomerName` and `Country` as MappingName are excluded while exporting.

### Excel version

While exporting to Excel, you can specify the excel version by using [ExcelVersion](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions__ctor_Syncfusion_XlsIO_ExcelVersion_System_Boolean_System_Boolean_Syncfusion_UI_Xaml_Grid_Converter_GridExcelExportingEventhandler_Syncfusion_UI_Xaml_Grid_Converter_GridCellExcelExportingEventHandler_) property.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

### Exporting stacked headers

You can export stacked headers to excel by setting [ExportStackedHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ExportStackedHeaders) property to `true`.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExportStackedHeaders = true;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

### Exporting merged cells

You can export merged cells to excel by setting [ExportMergedCells](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ExportMergedCells) property as `true`.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExportMergedCells = true;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

### Exporting unbound rows

You can export unbound rows to excel by setting [ExportUnBoundRows](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ExportUnBoundRows) property as `true`.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExportUnBoundRows = true;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

### Changing start row and column index while exporting

You can export the data to specified row index and column index in worksheet, by setting [StartRowIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_StartRowIndex) and [StartColumnIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_StartColumnIndex) properties.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.StartColumnIndex = 3;
options.StartRowIndex = 3;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

![Exporting to excel with custom start row index and column index in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img2.png)

## Saving options

### Save directly to file

After exporting to excel, you can save exported workbook directly to file system by using [SaveAs](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorkbook.html#Syncfusion_XlsIO_IWorkbook_SaveAs_System_IO_Stream_) method.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

### Save as stream

After exporting to excel, you can save exported workbook to stream by using [SaveAs](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorkbook.html#Syncfusion_XlsIO_IWorkbook_SaveAs_System_IO_Stream_) method.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
FileStream fileStream = new FileStream("Output.xlsx", FileMode.Create);
workBook.SaveAs(fileStream);
{% endhighlight %}
{% endtabs %}

You can refer [XlsIO documentation](http://help.syncfusion.com/file-formats/xlsio/faq). 

### Save using File dialog

After exporting to excel, you can save exported workbook by opening [FileDialog](https://msdn.microsoft.com/en-us/library/system.windows.forms.filedialog.aspx). 

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];

SaveFileDialog sfd = new SaveFileDialog
{
    FilterIndex = 2,
    Filter = "Excel 97 to 2003 Files(*.xls)|*.xls|Excel 2007 to 2010 Files(*.xlsx)|*.xlsx|Excel 2013 File(*.xlsx)|*.xlsx"
};

if (sfd.ShowDialog() == true)
{
    using (Stream stream = sfd.OpenFile())
    {

        if (sfd.FilterIndex == 1)
            workBook.Version = ExcelVersion.Excel97to2003;

        else if (sfd.FilterIndex == 2)
            workBook.Version = ExcelVersion.Excel2010;

        else
            workBook.Version = ExcelVersion.Excel2013;
        workBook.SaveAs(stream);
    }

    //Message box confirmation to view the created workbook.

    if (MessageBox.Show("Do you want to view the workbook?", "Workbook has been created",
                        MessageBoxButton.YesNo, MessageBoxImage.Information) == MessageBoxResult.Yes)
    {

        //Launching the Excel file using the default Application.[MS Excel Or Free ExcelViewer]
        System.Diagnostics.Process.Start(sfd.FileName);
    }
}
{% endhighlight %}
{% endtabs %}

## Opening exported excel without saving

You can open the exported workbook without saving by using [SfSpreadsheet](http://help.syncfusion.com/wpf/sfspreadsheet) control.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
Window window1 = new Window();
SfSpreadsheet spreadsheet = new SfSpreadsheet();
spreadsheet.Open(workBook);
window1.Content = spreadsheet;
window1.Show();
{% endhighlight %}
{% endtabs %}

![Opening exported excel without saving in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img3.png)

## Export DataGrid pages to Excel

While exporting data to excel, if paging is used, current page only will be exported, by default. If you want to export all pages, you need to set [ExportAllPages](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ExportAllPages) property as `true`.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExportAllPages = true;            
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

By default, all data will be exported to single sheet. If you want to export each page to different sheets, you need to use [ExportPageOptions](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ExportPageOptions) property.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExportAllPages = true;
options.ExportPageOptions = ExportPageOptions.ExportToDifferentSheets;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

## Export DataGrid SelectedItems to Excel

By default, entire grid will be exported to Excel. You can export selected items only by passing `SelectedItems` to 
[ExportToExcel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.GridExcelExportExtension.html#Syncfusion_UI_Xaml_Grid_Converter_GridExcelExportExtension_ExportToExcel_Syncfusion_UI_Xaml_Grid_SfDataGrid_Syncfusion_Data_ICollectionViewAdv_Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_Syncfusion_XlsIO_IWorksheet_) method.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
ExcelEngine excelEngine = new ExcelEngine();
IWorkbook workBook = excelEngine.Excel.Workbooks.Create();
workBook.Worksheets.Create();
dataGrid.ExportToExcel(dataGrid.SelectedItems, options, workBook.Worksheets[0]);
workBook.Version = ExcelVersion.Excel2013;
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

![Exporting the selected items only to excel in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img4.png)

## Export DataGrid to HTML

You can save exported workbook as HTML by using [SaveAsHtml](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorkbook.html#Syncfusion_XlsIO_IWorkbook_SaveAsHtml_System_IO_Stream_) method.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAsHtml("Sample.html", HtmlSaveOptions.Default);
{% endhighlight %}
{% endtabs %}

It is also possible to save worksheet as HTML by using [SaveAsHtml](https://help.syncfusion.com/cr/file-formats/Syncfusion.XlsIO.IWorkbook.html#Syncfusion_XlsIO_IWorkbook_SaveAsHtml_System_IO_Stream_) method. You can refer [XlsIO documentation](http://help.syncfusion.com/file-formats/xlsio/working-with-excel-worksheet#save-worksheet-as-html) for this.

## Export DataGrid to Mail

You can export SfDataGrid to mail by converting it into Excel and save exported worksheet as HTML. Then exported HTML contents is embedded in mail body.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2010;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];

workBook.Worksheets[0].UsedRange.BorderInside(ExcelLineStyle.Thick, ExcelKnownColors.Black);
workBook.Worksheets[0].UsedRange.BorderAround(ExcelLineStyle.Thick, ExcelKnownColors.Black);
workBook.Worksheets[0].SaveAsHtml("test.htm", Syncfusion.XlsIO.Implementation.HtmlSaveOptions.Default);

System.Net.Mail.MailMessage myMessage = new System.Net.Mail.MailMessage();

myMessage.To.Add("Support@syncfusion.com");
myMessage.From = new MailAddress("Support@syncfusion.com");
myMessage.Priority = MailPriority.High;
myMessage.Subject = "Order Details";
myMessage.IsBodyHtml = true;
myMessage.Body = new StreamReader("test.htm").ReadToEnd();

SmtpClient client = new SmtpClient("smtp.office365.com", 587);

client.EnableSsl = true;
client.UseDefaultCredentials = false;
client.Credentials = new NetworkCredential("Support@syncfusion.com", "test");

int count = 0;

while (count < 3)
{

    try
    {
        client.Send(myMessage);
        count = 3;
    }

    catch (Exception ex)
    {
        Console.WriteLine(ex.Message);
        Console.WriteLine(String.Format("Sending Mail Attemp - {0}", count.ToString()));
        Thread.Sleep(60000);
        count++;
    }
}
Console.WriteLine("Mail has been sent...");
{% endhighlight %}
{% endtabs %}

## Export DataGrid to XML

You can save exported workbook as `Xml` file also by using [SaveAsXml](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorkbook.html#Syncfusion_XlsIO_IWorkbook_SaveAsXml_System_IO_Stream_Syncfusion_XlsIO_ExcelXmlSaveType_) methods.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAsXml("Sample.xml", ExcelXmlSaveType.MSExcel);
{% endhighlight %}
{% endtabs %}

## Export DataGrid to CSV

You can save exported workbook as CSV by using `SaveAs` method.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.csv", ",");
{% endhighlight %}
{% endtabs %}

Similarly, you can save exported worksheet also to CSV. You can refer [XlsIO documentation.](http://help.syncfusion.com/file-formats/xlsio/working-with-excel-worksheet#save-worksheet-as-csv) 

## Row Height and Column Width customization 

After exporting data to excel, you can set different row height and column width for the columns based on your requirement. You can refer [here](http://help.syncfusion.com/file-formats/xlsio/worksheet-rows-and-columns-manipulation#adjust-row-height-and-column-width) for more information. 

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.Worksheets[0].SetRowHeight(2, 50);
workBook.Worksheets[0].SetColumnWidth(2, 50);
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

## Styling cells based on CellType in Excel

You can customize the cell styles based on `CellType` by using [ExportingEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ExportingEventHandler).

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExportingEventHandler = ExportingHandler;
options.AllowOutlining = true;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");

private static void ExportingHandler(object sender, GridExcelExportingEventArgs e)
{

      if (e.CellType == ExportCellType.HeaderCell)
      {
          e.CellStyle.BackGroundBrush = new SolidColorBrush(Colors.LightPink);
          e.CellStyle.ForeGroundBrush = new SolidColorBrush(Colors.White);
          e.Handled = true;
      }

      else if (e.CellType == ExportCellType.RecordCell)
      {
          e.CellStyle.BackGroundBrush = new SolidColorBrush(Colors.LightSkyBlue);
          e.Handled = true;
      }

      else if (e.CellType == ExportCellType.GroupCaptionCell)
      {
          e.CellStyle.BackGroundBrush = new SolidColorBrush(Colors.Wheat);
          e.Handled = true;
      }
}
{% endhighlight %}
{% endtabs %}

![Styling cells based on CellType in exported excel for WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img5.png)

## Cell customization in Excel while exporting

You can customize the cells by setting [CellsExportingEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ChildExportingEventHandler) in `ExcelExportingOptions`.

### Customize cell value while exporting

You can customize the call values while exporting to excel by using [CellsExportingEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ChildExportingEventHandler) and `ExcelExportingOptions`.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.CellsExportingEventHandler = CellExportingHandler;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");

private static void CellExportingHandler(object sender, GridCellExcelExportingEventArgs e)
{            

     // Based on the column mapping name and the cell type, we can change the cell 
                                          //values while exporting to excel.
     if (e.CellType == ExportCellType.RecordCell && e.ColumnName == "IsClosed")
     {

         //if the cell value is True, "Y" will be displayed else "N" will be displayed.

         if (e.CellValue.Equals(true))
             e.Range.Cells[0].Value = "Y";

         else
             e.Range.Cells[0].Value = "N";
         e.Handled = true;
      }
}
{% endhighlight %}
{% endtabs %}

![Customization of cell values while exporting to excel in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img6.png)

Here, cell values are changed for `IsClosed` column based on custom condition.

### Changing row style in excel based on data

You can customize the rows based on the record values by using [CellsExportingEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ChildExportingEventHandler).

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.CellsExportingEventHandler = CellExportingHandler;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");

private static void CellExportingHandler(object sender, GridCellExcelExportingEventArgs e)
{           

     if (!(e.NodeEntry is RecordEntry))
        return;
     var record = e.NodeEntry as RecordEntry;

     if ((record.Data as OrderInfo).Country == "Mexico")
     {
         e.Range.CellStyle.ColorIndex = ExcelKnownColors.Green;
         e.Range.CellStyle.Font.Color = ExcelKnownColors.White;
     }
}
{% endhighlight %}
{% endtabs %}

![Row styling based on data while exporting to excel in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img7.png)

Here, records having the `Country` name as `Mexico` are customized.

### Customize the cells based on Column Name

You can customize the cells based on [GridCellExcelExportingEventArgs.ColumnName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.GridCellExcelExportingEventArgs.html#Syncfusion_UI_Xaml_Grid_Converter_GridCellExcelExportingEventArgs_ColumnName) property in the [CellsExportingEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_CellsExportingEventHandler).

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.CellsExportingEventHandler = CellExportingHandler;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");

private static void CellExportingHandler(object sender, GridCellExcelExportingEventArgs e)
{

    if (e.ColumnName != "OrderID")
        return;

    e.Range.CellStyle.Font.Size = 12;
    e.Range.CellStyle.Font.Color = ExcelKnownColors.Pink;
    e.Range.CellStyle.Font.FontName = "Segoe UI";
}
{% endhighlight %}
{% endtabs %}

![Customization of cell values based on column name while exporting to excel in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img8.png)

Here, `OrderID` column cells are customized while exporting.

## Customize exported workbook and worksheet

SfDataGrid exports to excel by using [XlsIO](http://help.syncfusion.com/file-formats/xlsio/overview). You can refer [XlsIO documentation](http://help.syncfusion.com/file-formats/xlsio/working-with-excel-worksheet) for manipulating workbook and sheet after exporting. 

### Workbook
SfDataGrid provides option to return [ExcelEngine](https://help.syncfusion.com/cr/file-formats/Syncfusion.XlsIO.ExcelEngine.html) from that you can get exported workbook. This allows you to protect, encrypt and add worksheet before saving. 

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();         
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

### Worksheet customization

SfDataGrid provides support to export to already existing file or worksheet. 

In the below code snippet, worksheet is created and passed to `ExportToExcel` method. In the same way, you can open already existing excel also using `XlsIO`. 

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
ExcelEngine excelEngine = new ExcelEngine();
IWorkbook workBook = excelEngine.Excel.Workbooks.Create();
dataGrid.ExportToExcel(dataGrid.View, options, workBook.Worksheets[0]);
workBook.Version = ExcelVersion.Excel2013;
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

Before saving workbook, you need to set the specific excel version by using [IWorkbook.Version](https://help.syncfusion.com/cr/wpf/Syncfusion.XlsIO.IWorkbook.html#Syncfusion_XlsIO_IWorkbook_Version) property. Here, you can directly manipulate the data in the worksheet. You can refer [here](http://help.syncfusion.com/file-formats/xlsio/worksheet-rows-and-columns-manipulation) for more information.

#### Setting borders

You can set borders to excel cells by directly accessing worksheet after exporting data.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.Worksheets[0].UsedRange.BorderInside(ExcelLineStyle.Dash_dot, ExcelKnownColors.Black);
workBook.Worksheets[0].UsedRange.BorderAround(ExcelLineStyle.Dash_dot, ExcelKnownColors.Black);
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

![Change the borders in exported excel for WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img9.png)

#### Enabling Filters

You can show filters in exported worksheet by enabling filter for the exported range in the worksheet.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.Worksheets[0].AutoFilters.FilterRange = workBook.Worksheets[0].UsedRange;
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

![Shows enabling filters on exported excel in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img10.png)

While using `stacked headers`, you can specify the `range` based on Stacked headers count.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
options.ExportStackedHeaders = true;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
var range = "A" + (dataGrid.StackedHeaderRows.Count + 1).ToString() + ":" + workBook.Worksheets[0].UsedRange.End.AddressLocal;
excelEngine.Excel.Workbooks[0].Worksheets[0].AutoFilters.FilterRange = workBook.Worksheets[0].Range[range];
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

You can refer [XlsIO documentation](http://help.syncfusion.com/file-formats/xlsio/worksheet-cells-manipulation#data-filtering).

#### Customize the range of cells

You can customize the range of cells after exporting to excel by directly manipulating worksheet.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ExcelVersion = ExcelVersion.Excel2013;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.Worksheets[0].Range["A2:A6"].CellStyle.Color = System.Drawing.Color.LightSlateGray;
workBook.Worksheets[0].Range["A2:A6"].CellStyle.Font.Color = ExcelKnownColors.White;
workBook.SaveAs("Sample.xlsx");
{% endhighlight %}
{% endtabs %}

![Customization of range of cells in exported excel for WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img11.png)

## Exporting DetailsView

By default, [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) will be exported to Excel. You can customize its exporting operation by using [ChildExportingEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ChildExportingEventHandler).

### Excluding DetailsViewDataGrid while exporting

You can exclude particular `DetailsViewDataGrid` while exporting, by using the [ChildExportingEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ChildExportingEventHandler) and [GridChildExportingEventArgs.Cancel](https://msdn.microsoft.com/en-us/library/system.componentmodel.canceleventargs.cancel.aspx) .

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.ChildExportingEventHandler = ChildExportingHandler;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");

private static void ChildExportingHandler(object sender, GridChildExportingEventArgs e)
{
       var recordEntry = e.NodeEntry as RecordEntry;

       if ((recordEntry.Data as OrderInfo).OrderID == 1002)
          e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

![Excluding the particular DetailsView while exporting to excel in WPF DataGrid ](Export-to-Excel_images/Export-to-Excel_img12.png)

Here, `DetailsViewDataGrid` is not exported for the parent record having `OrderID` as 1002.

### Excluding DetailsViewDataGrid columns from exporting

You can exclude [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) columns while exporting, by using [ChildExportingEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ChildExportingEventHandler) and [GridChildExportingEventArgs.ExcludeColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.GridChildExportingEventArgs.html#Syncfusion_UI_Xaml_Grid_Converter_GridChildExportingEventArgs_ExcludeColumns).

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();            
options.ChildExportingEventHandler = ChildExportingHandler;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");

private static void ChildExportingHandler(object sender, GridChildExportingEventArgs e)
{            
      e.ExcludeColumns.Add("OrderID");
}
{% endhighlight %}
{% endtabs %}

![Excluding the columns in DetailsViewDataGrid while exporting to excel in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img13.png)

Here, `OrderID` column is displayed in `DetailsViewDataGrid` and it is excluded while exporting to excel.

### Customizing DetailsViewDataGrid cells

Like parent DataGrid, You can customize the `DetailsViewDataGrid` cells also by using [CellsExportingEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_ChildExportingEventHandler). Based on [GridCellExcelExportingEventArgs.GridViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.GridCellExcelExportingEventArgs.html#Syncfusion_UI_Xaml_Grid_Converter_GridCellExcelExportingEventArgs_GridViewDefinition) property, you can identify the particular `DetailsViewDataGrid` and customize it.

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();
options.CellsExportingEventHandler = CellExportingHandler;
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
var workBook = excelEngine.Excel.Workbooks[0];
workBook.SaveAs("Sample.xlsx");

private static void CellExportingHandler(object sender, GridCellExcelExportingEventArgs e)
{

    if (e.GridViewDefinition == null || e.GridViewDefinition.RelationalColumn != "ProductDetails")
        return;

    if (e.ColumnName == "OrderID")
    {
        e.Range.CellStyle.Font.Size = 12;
        e.Range.CellStyle.Font.Color = ExcelKnownColors.Blue;
        e.Range.CellStyle.Font.FontName = "Segoe UI";
    }
}
{% endhighlight %}
{% endtabs %}

![Customization of DetailsViewDataGrid cells while exporting to excel in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img14.png)


## Performance

Using [ExcelExportingOptions.CellsExportingEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Converter.ExcelExportingOptions.html#Syncfusion_UI_Xaml_Grid_Converter_ExcelExportingOptions_CellsExportingEventHandler) and changing settings for each cell will consume more memory and time consumption. So, avoid using `CellsExportingEventHandler` and instead of you can do the required settings in the exported sheet.
 
### Formatting column without using CellsExportingEventHandler

You can perform cell level customization such as row-level styling, formatting particular column in the exported worksheet. 

In the below code snippet, NumberFormat for `Unit Price` column is changed in the exported sheet after exporting without using `CellsExportingEventHandler`. 

Reference:
[http://help.syncfusion.com/file-formats/xlsio/working-with-cell-or-range-formatting](http://help.syncfusion.com/file-formats/xlsio/working-with-cell-or-range-formatting)

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();                   
options.ExportMode = ExportMode.Value;                 
options.ExcelVersion = ExcelVersion.Excel2013;           
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
IWorkbook workBook = excelEngine.Excel.Workbooks[0];
workBook.ActiveSheet.Columns[4].NumberFormat = "0.0";
{% endhighlight %}
{% endtabs %}


![Formatting the column without CellExportingEventHandler while exporting to excel in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img15.png)

### Alternate row styling without using CellsExportingEventHandler

In the below code snippet, the background color of rows in excel is changed based on row index using conditional formatting for better performance.

Reference:
[http://help.syncfusion.com/file-formats/xlsio/working-with-conditional-formatting](http://help.syncfusion.com/file-formats/xlsio/working-with-conditional-formatting)

{% tabs %}
{% highlight c# %}
var options = new ExcelExportingOptions();                   
options.ExportMode = ExportMode.Value;                 
options.ExcelVersion = ExcelVersion.Excel2013;           
var excelEngine = dataGrid.ExportToExcel(dataGrid.View, options);
IWorkbook workBook = excelEngine.Excel.Workbooks[0];

IConditionalFormats condition = workBook.ActiveSheet.Range[2,1,this.dataGrid.View.Records.Count+1,this.dataGrid.Columns.Count].ConditionalFormats;
IConditionalFormat condition1 = condition.AddCondition();
condition1.FormatType = ExcelCFType.Formula;
condition1.FirstFormula = "MOD(ROW(),2)=0";
condition1.BackColorRGB = System.Drawing.Color.Pink;
IConditionalFormat condition2 = condition.AddCondition();
condition2.FormatType = ExcelCFType.Formula;
condition2.FirstFormula = "MOD(ROW(),2)=1";
condition2.BackColorRGB = System.Drawing.Color.LightGray;
{% endhighlight %}
{% endtabs %}

![Shows the row styling without using CellExportingEventHandler while exporting to excel in WPF DataGrid](Export-to-Excel_images/Export-to-Excel_img16.png)


