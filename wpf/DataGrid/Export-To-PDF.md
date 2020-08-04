---
layout: post
title: Export to PDF in WPF DataGrid control | Syncfusion
description: Learn about exporting datagrid to PDF support in Syncfusion WPF DataGrid (SfDataGrid) control and more details.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Export to PDF in WPF DataGrid (SfDataGrid)

DataGrid provides support to export data to PDF file. It also provides support for grouping, filtering, sorting, paging, unbound rows, merged cells, stacked headers and details View while exporting.

The following assemblies needs to be added for exporting to PDF file. 

* Syncfusion.SfGridConverter.WPF
* Syncfusion.Pdf.Base

For NuGet package, have to install [Syncfusion.DataGridExcelExport.WPF](https://www.nuget.org/packages/Syncfusion.DataGridExcelExport.WPF) package. For more details refer this [UG link](https://help.syncfusion.com/wpf/control-dependencies#exporting-datagrid-to-excel-pdf-and-csv).

You can export SfDataGrid to PDF by using the following extension methods present in the [Syncfusion.UI.Xaml.Grid.Converter](http://help.syncfusion.com/cr/cref_files/wpf/webtoc.html) namespace.

* [ExportToPdf](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.GridPdfExportExtension~ExportToPdf.html)
* [ExportToPdfGrid](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.GridPdfExportExtension~ExportToPdfGrid.html)

{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid.Converter;
var document = dataGrid.ExportToPdf();
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

N> SfDataGrid exports data to PDF file by using [Essential PDF](http://help.syncfusion.com/file-formats/pdf/overview). You can refer [PDF documentation](http://help.syncfusion.com/file-formats/pdf/working-with-document) for manipulating.

## PDF exporting options

Exporting operation can be customized by passing [PdfExportingOptions](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions.html) instance as argument to `ExportToPdf` and `ExportToPdfGrid` method. 

### Auto size column widths in PDF

You can export SfDataGrid to PDF by fitting column widths based on its content by setting [AutoColumnWidth](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~AutoColumnWidth.html) property as `true`. 

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.AutoColumnWidth = true;
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Auto size row heights in PDF

You can export SfDataGrid to PDF by fitting row heights based on its content by setting [AutoRowHeight](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~AutoRowHeight.html) property as `true`. 

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.AutoRowHeight = true;
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Exclude columns while exporting

By default, all the columns (including hidden columns) in SfDataGrid will be exported to PDF. If you want to exclude some columns while exporting to PDF, you can use [ExcludeColumns](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExcludeColumns.html) property in [PdfExportingOptions](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions.html).

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExcludeColumns.Add("CustomerName");
options.ExcludeColumns.Add("Country");
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

Here, the columns having `CustomerName` and `Country` as MappingName are excluded while exporting.

### Export Format

By default, display text only will be exported to PDF. If you want to export the actual value, you need to set [ExportFormat](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportFormat.html) property as `false`. 

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportFormat = false;
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Column header on each page

Column headers can be exported on each page by setting [RepeatHeaders](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~RepeatHeaders.html) property.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.RepeatHeaders = true;
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Export all columns in one page

While exporting to PDF, you can fit all columns on one page by setting [FitAllColumnsInOnePage](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~FitAllColumnsInOnePage.html) property as `true`.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.FitAllColumnsInOnePage = true;
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Export paging

While exporting data to PDF, if paging is used, current page only will be exported, by default. If you want to export all pages, you need to set [ExportAllPages](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportAllPages.html) property as `true`.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportAllPages = true;            
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Exclude groups while exporting

By default, all the groups in dataGrid will be exported to PDF. If you want to export without Groups, you need to set [ExportGroups](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportGroups.html) property as `false`.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportGroups = false;
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Exclude group Summaries while exporting

By default, group summaries in dataGrid will be exported to PDF. If you want to export without group summaries, you need to set [ExportGroupSummary](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportGroupSummary.html) property as `false`.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportGroupSummary = false;
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Exclude table Summaries while exporting

By default, table summaries in dataGrid will be exported to PDF. If you want to export without table summaries, you need to set [ExportTableSummary](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportTableSummary.html) property as `false`.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportTableSummary = false;
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Exporting unbound rows

You can export unbound rows to PDF by setting [ExportUnBoundRows](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportUnBoundRows.html) property as `true`.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportUnBoundRows = true;
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Exporting stacked headers

You can export stacked headers to PDF by setting [ExportStackedHeaders](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportStackedHeaders.html) property to `true`.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportStackedHeaders = true;
var document = dataGrid.ExportToPdf(options);            
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

### Exporting merged cells

You can export merged cells to PDF by setting [ExportMergedCells](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportMergedCells.html) property as `true`.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportMergedCells = true;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

## Setting Header and Footer

SfDataGrid provides a way to display additional content at the top (Header) or bottom (Footer) of the page while exporting to PDF. This can be achieved by setting [PageHeaderFooterEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~PageHeaderFooterEventHandler.html) in [PdfExportingOptions](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions.html).

You can insert string, image or any drawing in header and footer in `PdfHeaderFooterEventHandler`. Setting [PdfPageTemplateElement](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.PdfPageTemplateElement.html) to [PdfHeaderFooterEventArgs.PdfDocumentTemplate.Top](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.PdfDocumentTemplate~Top.html) loads the content at top of the page and setting the `PdfPageTemplateElement` to [PdfHeaderFooterEventArgs.PdfDocumentTemplate.Bottom](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.PdfDocumentTemplate~Bottom.html) loads the content at bottom of the page.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.PageHeaderFooterEventHandler = PdfHeaderFooterEventHandler;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");

static void PdfHeaderFooterEventHandler(object sender, PdfHeaderFooterEventArgs e)
{
    PdfFont font = new PdfStandardFont(PdfFontFamily.TimesRoman, 20f,  PdfFontStyle.Bold);                 
    var width = e.PdfPage.GetClientSize().Width;
    PdfPageTemplateElement header = new PdfPageTemplateElement(width, 38);
    header.Graphics.DrawString("Order Details", font, PdfPens.Black, 70, 3);
    e.PdfDocumentTemplate.Top = header;
}
{% endhighlight %}
{% endtabs %}

![WPF DataGrid exported to PDF with Header and Footer](Export-To-PDF_images/Export-To-PDF_img1.png)

Here, `string` is inserted in the header of exported PDF file using [DrawString](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.Graphics.PdfGraphics~DrawString.html) method. Similarly, you can insert image, line,etc. using [DrawImage](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.Graphics.PdfGraphics~DrawImage.html), [DrawLine](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.Graphics.PdfGraphics~DrawLine.html) methods respectively. 

## Change PDF page orientation

You can change the page orientation of PDF while exporting. The default page orientation is Portrait.

To change the page orientation, you need to get the exported [PdfGrid](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.Grid.PdfGrid.html) by using [ExportToPdfGrid](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.GridPdfExportExtension~ExportToPdfGrid.html) method and then draw that `PdfGrid` into a [PdfDocument](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.PdfDocument.html) by changing the [PageSettings.Orientation](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.PdfPageSettings~Orientation.html) property of `PdfDocument`.

{% tabs %}
{% highlight c# %}
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
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

## Export DataGrid SelectedItems to PDF

By default, entire grid will be exported to PDF. You can export selected items only by passing `SelectedItems` to [ExportToPdf](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.GridPdfExportExtension~ExportToPdf.html) and [ExportToPdfGrid](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.GridPdfExportExtension~ExportToPdfGrid.html) methods.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.AutoColumnWidth = true;
var document = dataGrid.ExportToPdf(dataGrid.SelectedItems, options);
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

![WPF DataGrid SelectedItems exported to PDF](Export-To-PDF_images/Export-To-PDF_img2.png)

## Saving options

### Save directly to file

After exporting to PDF, you can save exported PDF file directly to file system by using [Save](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.PdfDocumentBase~Save.html) method.

{% tabs %}
{% highlight c# %}
var document = dataGrid.ExportToPdf();
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

You can refer [PDF documentation](http://help.syncfusion.com/file-formats/pdf/loading-and-saving-document#saving-a-pdf-document-to-file-system). 

### Save as stream

After exporting to PDF, you can save exported PDF file to stream by using [Save](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.PdfDocumentBase~Save.html) method.

{% tabs %}
{% highlight c# %}
FileStream fileStream = new FileStream("Sample.pdf", FileMode.Create);          
var document = dataGrid.ExportToPdf();
document.Save(fileStream);
fileStream.Close();
{% endhighlight %}
{% endtabs %}

You can refer [PDF documentation](http://help.syncfusion.com/file-formats/pdf/loading-and-saving-document#saving-a-pdf-document-to-stream). 

### Save using File dialog

After exporting to PDF, you can save exported PDF file by opening [FileDialog](https://msdn.microsoft.com/en-us/library/system.windows.forms.filedialog.aspx). 

{% tabs %}
{% highlight c# %}
var document = dataGrid.ExportToPdf();
SaveFileDialog sfd = new SaveFileDialog
{
    Filter = "PDF Files(*.pdf)|*.pdf"
};

if (sfd.ShowDialog() == true)
{
    using (Stream stream = sfd.OpenFile())
    {
        document.Save(stream);
    }

    //Message box confirmation to view the created Pdf file.

    if (MessageBox.Show("Do you want to view the Pdf file?", "Pdf file has been created",
                        MessageBoxButton.YesNo, MessageBoxImage.Information) == MessageBoxResult.Yes)
    {
 
        //Launching the Pdf file using the default Application.
        System.Diagnostics.Process.Start(sfd.FileName);
    }
}         
{% endhighlight %}
{% endtabs %}

## Opening exported PDF without saving

You can view exported PDF document without saving by using [PDFViewerControl](http://help.syncfusion.com/wpf/pdfviewer/overview).

{% tabs %}
{% highlight c# %}
var document = this.dataGrid.ExportToPdf();
MemoryStream stream = new MemoryStream();
document.Save(stream);
PdfViewerControl pdfViewer = new PdfViewerControl();
pdfViewer.Load(stream);
Window window = new Window();
window.Content = pdfViewer;
window.Show();
{% endhighlight %}
{% endtabs %}

![WPF DataGrid exported to WPF PDF Viewer](Export-To-PDF_images/Export-To-PDF_img3.png)

## Exporting Customization

### Styling cells based on CellType in PDF

You can customize the cell styles based on `CellType` by using [ExportingEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportingEventHandler.html).

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportingEventHandler = GridPdfExportingEventHandler;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");

void GridPdfExportingEventHandler(object sender, GridPdfExportingEventArgs e)
{

    if (e.CellType == ExportCellType.HeaderCell)
        e.CellStyle.BackgroundBrush = PdfBrushes.LightSteelBlue;

    else if (e.CellType == ExportCellType.GroupCaptionCell)
        e.CellStyle.BackgroundBrush = PdfBrushes.LightGray;

    else if (e.CellType == ExportCellType.RecordCell)
        e.CellStyle.BackgroundBrush = PdfBrushes.Wheat;
}
{% endhighlight %}
{% endtabs %}

![WPF DataGrid exported PDF file](Export-To-PDF_images/Export-To-PDF_img4.png)

### Embedding fonts in PDF file

By default, some fonts (such as Unicode font) are not supported in PDF. In this case, it is possible to embed the font in PDF document with the help of [PdfTrueTypeFont](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.Graphics.PdfTrueTypeFont.html). 

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportingEventHandler = GridPdfExportingEventHandler;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");

void GridPdfExportingEventHandler(object sender, GridPdfExportingEventArgs e)
{    

    if (e.CellType != ExportCellType.RecordCell)
        return;

    //creates a new font from the font file.                
    var font = new PdfTrueTypeFont(@"..\..\Resources\segoeui.ttf", 9f, PdfFontStyle.Regular);
    e.CellStyle.Font = font;
}
{% endhighlight %}
{% endtabs %}

Here, new font is created from font file and it is assigned to the `Font` of [PdfGridCell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.Grid.PdfGridCell.html).

## Cell customization in PDF while exporting

You can customize the cells in the PDF document by setting [CellsExportingEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~CellsExportingEventHandler.html) in [PdfExportingOptions](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions.html).

### Customize cell values while exporting

You can customize the call values while exporting to PDF by using [CellsExportingEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~CellsExportingEventHandler.html) and [PdfExportingOptions](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions.html).

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.CellsExportingEventHandler = CellsExportingEventHandler;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");

private void CellsExportingEventHandler(object sender, GridCellPdfExportingEventArgs e)
{

    // Based on the column mapping name and the cell type, you can change the cell values while exporting to PDF.

    if (e.CellType == ExportCellType.RecordCell && e.ColumnName == "IsClosed")
    {

        //if the cell value is True, "Y" will be displayed else "N" will be displayed.

        if (e.CellValue.Equals("True"))
            e.CellValue = "Y";

        else
            e.CellValue = "N";
    }
}
{% endhighlight %}
{% endtabs %}

![WPF DataGrid exported PDF File](Export-To-PDF_images/Export-To-PDF_img5.png)

Here, cell values are changed for `IsClosed` column based on custom condition.

### Changing row style in PDF based on data

You can customize the rows based on the record values by using [CellsExportingEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~CellsExportingEventHandler.html).

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.CellsExportingEventHandler = CellsExportingEventHandler;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");

private void CellsExportingEventHandler(object sender, GridCellPdfExportingEventArgs e)
{

    if (!(e.NodeEntry is OrderInfo))
        return;

    if ((e.NodeEntry as OrderInfo).Country == "Mexico")
    {
        var cellStyle = new PdfGridCellStyle();
        cellStyle.BackgroundBrush = PdfBrushes.LightPink;             
        cellStyle.Borders.All = new PdfPen(PdfBrushes.DarkGray, 0.2f);
        e.PdfGridCell.Style = cellStyle;
    }
}
{% endhighlight %}
{% endtabs %}

![PDF Grid row styling when exporting from WPF DataGrid](Export-To-PDF_images/Export-To-PDF_img6.png)

### Exporting Middle Eastern Languages (Arabic, Hebrew) from SfDataGrid to PDF

By default, [Middle Eastern languages ](http://en.wikipedia.org/wiki/Middle_East)(Arabic, Hebrew) in SfDataGrid are exported as left to right in PDF. You can export them as displayed in SfDataGrid (export from Right to Left) by enabling [RightToLeft](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.Graphics.PdfStringFormat~RightToLeft.html) property in [PdfStringFormat](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.Graphics.PdfStringFormat.html) class and apply the format to the [PdfGridCell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.Grid.PdfGridCell.html) by using [CellsExportingEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~CellsExportingEventHandler.html).

{% tabs %}
{% highlight c# %}
 PdfExportingOptions options = new PdfExportingOptions();
options.CellsExportingEventHandler = CellsExportingEventHandler;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");

private void CellsExportingEventHandler(object sender, GridCellPdfExportingEventArgs e)
{    

    if (e.CellType != ExportCellType.RecordCell)
        return;

    PdfStringFormat format = new PdfStringFormat();

    //format the string from right to left.
    format.RightToLeft = true;
    e.PdfGridCell.StringFormat = format;
}
{% endhighlight %}
{% endtabs %}

![Exporting of middle eastern languages from WPF DataGrid to PDF File](Export-To-PDF_images/Export-To-PDF_img7.png)

### Exporting images to PDF document

By default, images which is loaded in the [GridTemplateColumn](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridTemplateColumn.html) will not be exported to PDF. You can export it by using [CellsExportingEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~CellsExportingEventHandler.html) in `PdfExportingOptions`. In `CellsExportingEventHandler`, image is loaded in [PdfGridCell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Pdf.Base~Syncfusion.Pdf.Grid.PdfGridCell.html).

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.CellsExportingEventHandler = CellsExportingEventHandler;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");

private void CellsExportingEventHandler(object sender, GridCellPdfExportingEventArgs e)
{  
 
    if (e.CellType == ExportCellType.RecordCell && e.ColumnName == "IsClosed")
    {
        var style = new PdfGridCellStyle();
        PdfPen normalBorder = new PdfPen(PdfBrushes.DarkGray, 0.2f);
        System.Drawing.Image image = null;
 
        //Images are exported based on the CellValue 
 
        if (e.CellValue.Equals("True"))
        {
 
            //Access the image from the specified path 
            image = System.Drawing.Image.FromFile(@"..\..\Images\True.png");
        }
 
        else
            image = System.Drawing.Image.FromFile(@"..\..\Images\False.png");

        //Create the PDFImage for the specified image and assigned to BackgroundImage of the PdfGridCellStyle
        style.BackgroundImage = PDFImage.FromImage(image);
        e.PdfGridCell.ImagePosition = PdfGridImagePosition.Fit;
        e.PdfGridCell.Style = style;

        //customize the Border color of PdfGridCell
        e.PdfGridCell.Style.Borders.All = normalBorder;
        e.CellValue = null;
    }
}
{% endhighlight %}
{% endtabs %}

![WPF DataGrid exported to PDF file](Export-To-PDF_images/Export-To-PDF_img8.png)

## Exporting DetailsView

By default, [DetailsViewDataGrid](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) will not be exported to PDF. You can export `DetailsViewDataGrid` by setting [ExportDetailsView](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportDetailsView.html) property as `true`.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportDetailsView = true;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

![WPF DataGrid nested grid exported to PDF file](Export-To-PDF_images/Export-To-PDF_img9.png)

By default, only expanded DetailsViewDataGrids only will be exported to PDF document. If you want to export all the DetailsViewDataGrids, you need to set [ExportAllDetails](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExportAllDetails.html) as `true`.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportDetailsView = true;
options.ExportAllDetails = true;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");
{% endhighlight %}
{% endtabs %}

![WPF Nested DataGrid exported to PDF file](Export-To-PDF_images/Export-To-PDF_img10.png)

Here, first record only expanded in SfDataGrid. But all the DetailsViewDataGrid’s are shown in exported PDF document.

You can customize its exporting operation by using [ChildGridExportingEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ChildGridExportingEventHandler.html).

N> While exporting `DetailsViewDataGrid`, [FitAllColumnsInOnePage](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~FitAllColumnsInOnePage.html) is set to `true` internally as horizontal pagination is not supported for `DetailsViewDataGrid`.

### Excluding DetailsViewDataGrid while exporting

You can exclude particular `DetailsViewDataGrid` while exporting, by using the [ChildGridExportingEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ChildGridExportingEventHandler.html) and [ChildGridPdfExportingEventArgs.Cancel](https://msdn.microsoft.com/en-us/library/e1bcat2e.aspx).

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportDetailsView = true;
options.ChildGridExportingEventHandler = ChildGridExportingEventHandler;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");

void ChildGridExportingEventHandler(object sender, ChildGridPdfExportingEventArgs e)
{
    var recordEntry = e.NodeEntry as RecordEntry;

    if ((recordEntry.Data as OrderInfo).OrderID == 1002)
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

![WPF Master-details view DataGrid exported to PDF file](Export-To-PDF_images/Export-To-PDF_img11.png)

Here, `DetailsViewDataGrid` is not exported for the parent record having `OrderID` as 1002.

### Excluding DetailsViewDataGrid columns from exporting

You can exclude [DetailsViewDataGrid](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) columns while exporting, by using [ChildGridExportingEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ChildGridExportingEventHandler.html) and  [ChildGridPdfExportingEventArgs.PdfExportingOptions.ExcludeColumns](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~ExcludeColumns.html).

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportDetailsView = true;
options.ChildGridExportingEventHandler = ChildGridExportingEventHandler;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");

void ChildGridExportingEventHandler(object sender, ChildGridPdfExportingEventArgs e)
{ 
    e.PdfExportingOptions.ExcludeColumns = new List&lt;string&gt;() { "OrderID" };
}
{% endhighlight %}
{% endtabs %}

![WPF DataGrid exported to PDF file](Export-To-PDF_images/Export-To-PDF_img12.png)

Here, `OrderID` column is displayed in `DetailsViewDataGrid` and it is excluded while exporting to PDF.

### Customizing DetailsViewDataGrid cells

Like parent DataGrid, You can customize the `DetailsViewDataGrid` cells also by using [CellsExportingEventHandler](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.PdfExportingOptions~CellsExportingEventHandler.html). Based on [GridCellPdfExportingEventArgs.GridViewDefinition](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGridConverter.WPF~Syncfusion.UI.Xaml.Grid.Converter.GridCellPdfExportingEventArgs~GridViewDefinition.html) property, you can identify the particular `DetailsViewDataGrid` and customize it.

{% tabs %}
{% highlight c# %}
PdfExportingOptions options = new PdfExportingOptions();
options.ExportDetailsView = true;
options.CellsExportingEventHandler = CellsExportingEventHandler;
var document = dataGrid.ExportToPdf(options);
document.Save("Sample.pdf");

private void CellsExportingEventHandler(object sender, GridCellPdfExportingEventArgs e)
{
 
    if (e.GridViewDefinition == null || e.GridViewDefinition.RelationalColumn != "ProductDetails")                                     
        return;
 
    if (e.ColumnName == "OrderID")
    {
        var cellStyle = new PdfGridCellStyle();
        cellStyle.BackgroundBrush = PdfBrushes.Wheat;
        cellStyle.Borders.All = new PdfPen(PdfBrushes.DarkGray, 0.2f);
        e.PdfGridCell.Style = cellStyle;
    }
}
{% endhighlight %}
{% endtabs %}

![WPF DataGrid exported to PDF file](Export-To-PDF_images/Export-To-PDF_img13.png)


