---
layout: post
title: About WPF Exporting OLAP Client Control | Syncfusion
description: Learn here all about introduction of Syncfusion Essential Studio WPF Exporting OLAP Client control, its features, and more.
platform: wpf
control: OLAP Client
documentation: ug
---

# Exporting OLAP Chart and OLAP Grid to various forms

When creating an OLAP report in the OLAP client, the report will be visualized in the OLAP chart and OLAP grid. The OLAP client has an option to export the current view of the OLAP chart and OLAP grid to various forms.

## Exporting OLAP chart

The current view of the OLAP chart can be exported to Microsoft Word, PDF, and image and printed as well.

You can perform these exports in two ways:

* Through OLAP chart toolbar.
* Through API's.

### Through OLAP chart toolbar menu

By clicking the respective icons in the OLAP chart toolbar, You can export the OLAP chart to the corresponding mode.

![WPF OLAP Client Exporting Image1](Exporting_images/Exporting_img1.png)

<table>
<tr>
<th>
Icon</th><th>
Name</th><th>
Description</th></tr>
<tr>
<td> 
{{ '![WPF OLAP Client Exporting Image2](Exporting_images/Exporting_img2.png)' | markdownify }}

</td><td>
Export to Image</td><td>
Export the current view of the OLAP chart as image</td></tr>

<tr>
<td>
{{ '![WPF OLAP Client Exporting Image4](Exporting_images/Exporting_img4.png)' | markdownify }}

</td><td>
Export to Word</td><td>
Export the current view of the OLAP chart to a Word document.</td></tr>
<tr>
<td>
{{ '![WPF OLAP Client Exporting Image5](Exporting_images/Exporting_img5.png)' | markdownify }}

</td><td>
Export to PDF</td><td>
Export the current view of the OLAP chart to PDF.</td></tr>

<tr>
<td>
{{ '![WPF OLAP Client Exporting Image3](Exporting_images/Exporting_img3.png)' | markdownify }}

</td><td>
Print</td><td>
Print the current view of the OLAP chart.</td></tr>
</table> 

### Through API

You can achieve the export feature of OLAP chart by using the following API's. The following code sample illustrates exporting the OLAP chart into corresponding format.

#### Word export

{% tabs %}

{% highlight C# %}

SaveFileDialog saveFileDialog = new SaveFileDialog();
saveFileDialog.FileName = "OlapChart Report";
saveFileDialog.AddExtension = true;
saveFileDialog.DefaultExt = "doc";
saveFileDialog.Filter = "Word (.doc)|*.doc";
if (saveFileDialog.ShowDialog() == true)
{
    string fileName = saveFileDialog.FileName;
    OlapChartWordExport olapChartWordExport = new OlapChartWordExport(this.olapChart);
    olapChartWordExport.ExportintoNewDoc(fileName);
}
    
{% endhighlight %}

{% highlight vbnet %}

Dim saveFileDialog As SaveFileDialog()
saveFileDialog.FileName = "OlapChart Report"
saveFileDialog.AddExtension = True
saveFileDialog.DefaultExt = "doc"
saveFileDialog.Filter = "Word (.doc)|*.doc"
If saveFileDialog.ShowDialog() = True Then
    Dim fileName As String = saveFileDialog.FileName
    Dim olapChartWordExport As New OlapChartWordExport(Me.olapChart)
    olapChartWordExport.ExportintoNewDoc(fileName)
End If

{% endhighlight %}

{% endtabs %}

#### PDF export

{% tabs %}

{% highlight C# %}

SaveFileDialog saveFileDialog = new SaveFileDialog();
saveFileDialog.FileName = "OlapChart Report";
saveFileDialog.AddExtension = true;
saveFileDialog.DefaultExt = "pdf";
saveFileDialog.Filter = "PDF (.pdf)|*.pdf";
if (saveFileDialog.ShowDialog() == true)
{
    string fileName = saveFileDialog.FileName;
    OlapChartPdfExport chartPdfExport = new OlapChartPdfExport(this.olapChart);
    chartPdfExport.ExportIntoNewPdf(fileName);
}
    
{% endhighlight %}

{% highlight vbnet %}

Dim saveFileDialog As SaveFileDialog()
saveFileDialog.FileName = "OlapChart Report"
saveFileDialog.AddExtension = True
saveFileDialog.DefaultExt = "pdf"
saveFileDialog.Filter = "PDF (.pdf)|*.pdf"
If saveFileDialog.ShowDialog() = True Then
    Dim fileName As String = saveFileDialog.FileName
    Dim olapChartPdfExport As New OlapChartPdfExport(Me.olapChart)
    olapChartPdfExport.ExportIntoNewPdf(fileName)
End If

{% endhighlight %}

{% endtabs %}

#### Image export

{% tabs %}

{% highlight C# %}

private const string c_imageFilesFilter = "Bitmap(*.bmp)|*.bmp|JPEG(*.jpg,*.jpeg)|*.jpg;*.jpeg|GIF(*.gif)|*.gif|TIFF(*.tiff)|*.tiff|PNG(*.png)|*.png|WDP(*.wdp)|*.wdp|All files (*.*)|*.*";
SaveFileDialog saveFileDialog = new SaveFileDialog();
saveFileDialog.FileName = "OlapChart Report";
saveFileDialog.Filter = c_imageFilesFilter;
if (saveFileDialog.ShowDialog() == true)
{
    string fileName = saveFileDialog.FileName;
    string extension = new FileInfo(fileName).Extension.ToLower(CultureInfo.InvariantCulture);
    if (c_imageFilesFilter.Contains(extension))
    {
        using (Stream stream = File.Create(saveFileDialog.FileName))
        {
            BitmapEncoder encoder = Chart.CreateBitmapEncoderByExtension(extension);
            RenderTargetBitmap bmpSource = new RenderTargetBitmap((int)chart.ActualWidth, (int)chart.ActualHeight, 96, 96, PixelFormats.Default);
            Rectangle backgroundRect = new Rectangle();
            backgroundRect.Fill = Brushes.White;
            backgroundRect.Arrange(new Rect(chart.RenderSize));
            bmpSource.Render(backgroundRect);
            bmpSource.Render(visual);
            encoder.Frames.Add(BitmapFrame.Create(bmpSource));
            encoder.Save(stream);
        }
    }
}
    
{% endhighlight %}

{% highlight vbnet %}

Dim c_imageFilesFilter As String = "Bitmap(*.bmp)|*.bmp|JPEG(*.jpg,*.jpeg)|*.jpg;*.jpeg|GIF(*.gif)|*.gif|TIFF(*.tiff)|*.tiff|PNG(*.png)|*.png|WDP(*.wdp)|*.wdp|All files (*.*)|*.*"
Dim saveFileDialog As SaveFileDialog()
saveFileDialog.FileName = "OlapChart Report"
saveFileDialog.Filter = c_imageFilesFilter;
If saveFileDialog.ShowDialog() = True Then
    Dim extension As String = New FileInfo(fileName).Extension.ToLower(CultureInfo.InvariantCulture);
    Dim fileName As String = saveFileDialog.FileName
    If c_imageFilesFilter.Contains(extension) Then
        Using stream As Stream = File.Create(saveFileDialog.FileName)
            Dim encoder As BitmapEncoder = Chart.CreateBitmapEncoderByExtension(extension)
            Dim bmpSource As New RenderTargetBitmap(CInt(chart.ActualWidth), CInt(chart.ActualHeight), 96, 96, PixelFormats.[Default])
            Dim backgroundRect As New Rectangle()
            backgroundRect.Fill = Brushes.White
            backgroundRect.Arrange(New Rect(chart.RenderSize))
            bmpSource.Render(backgroundRect);
            bmpSource.Render(visual);
            encoder.Frames.Add(BitmapFrame.Create(bmpSource));
            encoder.Save(stream);
        End Using
    End If
End If

{% endhighlight %}

{% endtabs %}

## Exporting OLAP grid

The current view of the OLAP grid can be exported to the following forms:

* Microsoft Word
* PDF
* Microsoft Excel
* CSV

The user can perform these exports in two ways:

1. Through OLAP grid toolbar.
2. Through API's.

### Through OLAP grid toolbar menu

By clicking the respective export buttons in the OLAP grid toolbar, the user can export OLAP grid to the corresponding format.

![WPF OLAP Client Exporting Image6](Exporting_images/Exporting_img6.png)

<table>
<tr>
<th>
Icon</th><th>
Name</th><th>
Description</th></tr>
<tr>
<td> 
{{ '![WPF OLAP Client Exporting Image7](Exporting_images/Exporting_img7.png)' | markdownify }}

</td><td>
Export to Excel</td><td>
Export the OLAP grid to an Excel document.</td></tr>
<tr>
<td>
{{ '![WPF OLAP Client Exporting Image8](Exporting_images/Exporting_img8.png)' | markdownify }}

</td><td>
Export to Word</td><td>
Export the OLAP grid to a Word document.</td></tr>
<tr>
<td> 
{{ '![WPF OLAP Client Exporting Image9](Exporting_images/Exporting_img9.png)' | markdownify }}

</td><td>
Export to PDF</td><td>
Export the OLAP grid to a PDF document.</td></tr>
<tr>
<td>
{{ '![WPF OLAP Client Exporting Image10](Exporting_images/Exporting_img10.png)' | markdownify }}

</td><td>
Export to CSV</td><td>
Export the OLAP grid to a CSV document.</td></tr>
</table> 

### Through API

You can achieve the export feature of OLAP grid by using the following API's. The following code sample illustrates exporting the OLAP grid into corresponding format.

#### Excel export

{% tabs %}

{% highlight C# %}

SaveFileDialog saveFileDialog = new SaveFileDialog();
saveFileDialog.FileName = "OlapGrid Report";
saveFileDialog.AddExtension = true;
saveFileDialog.DefaultExt = "xlsx";
saveFileDialog.Filter = "Excel (.xlsx)|*.xlsx";
if (saveFileDialog.ShowDialog() == true)
{
    string fileName = saveFileDialog.FileName;
    GridExcelExport excelExport = new GridExcelExport(this.olapGrid.InternalGrid.Engine, this.olapGrid.GridStyleInfo, this.olapGrid.InternalGrid.Layout, saveFileDialog.DefaultExt, this.olapGrid.OlapDataManager.ItemSource == null ? false : true);
    excelExport.Export(fileName);
}
    
{% endhighlight %}

{% highlight vbnet %}

Dim saveFileDialog As SaveFileDialog()
saveFileDialog.FileName = "OlapGrid Report"
saveFileDialog.AddExtension = True
saveFileDialog.DefaultExt = "xlsx"
saveFileDialog.Filter = "Excel (.xlsx)|*.xlsx"
If saveFileDialog.ShowDialog() = True Then
    Dim fileName As String = saveFileDialog.FileName
    Dim excelExport As New GridExcelExport(Me.olapGrid.InternalGrid.Engine, Me.olapGrid.GridStyleInfo, Me.olapGrid.InternalGrid.Layout, saveFileDialog.DefaultExt, Me.olapGrid.OlapDataManager.ItemSource == null ? False : True)
    excelExport.Export(fileName)
End If

{% endhighlight %}

{% endtabs %}

#### Word export

{% tabs %}

{% highlight C# %}

SaveFileDialog saveFileDialog = new SaveFileDialog();
saveFileDialog.FileName = "OlapGrid Report";
saveFileDialog.AddExtension = true;
saveFileDialog.DefaultExt = "doc";
saveFileDialog.Filter = "Word (.doc)|*.doc";
if (saveFileDialog.ShowDialog() == true)
{
    string fileName = saveFileDialog.FileName;
    GridWordExport gridWordExport = new GridWordExport(this.olapGrid.InternalGrid.Engine, this.olapGrid.InternalGrid.Layout);
    gridWordExport.Export(fileName, this.olapGrid.GridStyleInfo);
}
    
{% endhighlight %}

{% highlight vbnet %}

Dim saveFileDialog As SaveFileDialog()
saveFileDialog.FileName = "OlapGrid Report"
saveFileDialog.AddExtension = True
saveFileDialog.DefaultExt = "doc"
saveFileDialog.Filter = "Word (.doc)|*.doc"
If saveFileDialog.ShowDialog() = True Then
    Dim fileName As String = saveFileDialog.FileName
    Dim gridWordExport As New GridWordExport(Me.olapGrid.InternalGrid.Engine, Me.olapGrid.InternalGrid.Layout)
    gridWordExport.Export(fileName, Me.olapGrid.GridStyleInfo)
End If

{% endhighlight %}

{% endtabs %}

#### PDF export

{% tabs %}

{% highlight C# %}

SaveFileDialog saveFileDialog = new SaveFileDialog();
saveFileDialog.FileName = "OlapGrid Report";
saveFileDialog.AddExtension = true;
saveFileDialog.DefaultExt = "pdf";
saveFileDialog.Filter = "PDF (.pdf)|*.pdf";
if (saveFileDialog.ShowDialog() == true)
{
    string fileName = saveFileDialog.FileName;
    GridPdfExport gridPdfExport = new GridPdfExport(this.olapGrid.InternalGrid.Engine, this.olapGrid.GridStyleInfo);
    gridPdfExport.Export(fileName);
}
    
{% endhighlight %}

{% highlight vbnet %}

Dim saveFileDialog As SaveFileDialog()
saveFileDialog.FileName = "OlapGrid Report"
saveFileDialog.AddExtension = True
saveFileDialog.DefaultExt = "pdf"
saveFileDialog.Filter = "PDF (.pdf)|*.pdf"
If saveFileDialog.ShowDialog() = True Then
    Dim fileName As String = saveFileDialog.FileName
    Dim gridPdfExport As New GridPdfExport(Me.olapGrid.InternalGrid.Engine, Me.olapGrid.GridStyleInfo)
    gridPdfExport.Export(fileName)
End If

{% endhighlight %}

{% endtabs %}

#### CSV export

{% tabs %}

{% highlight C# %}

SaveFileDialog saveFileDialog = new SaveFileDialog();
saveFileDialog.FileName = "OlapGrid Report";
saveFileDialog.AddExtension = true;
saveFileDialog.DefaultExt = "csv";
saveFileDialog.Filter = "CSV (.csv)|*.csv";
if (saveFileDialog.ShowDialog() == true)
{
    string fileName = saveFileDialog.FileName;
    GridCsvExport gridCsvExport = new GridCsvExport(this.olapGrid.InternalGrid.Engine);
    gridCsvExport.Export(fileName);
}
    
{% endhighlight %}

{% highlight vbnet %}

Dim saveFileDialog As SaveFileDialog()
saveFileDialog.FileName = "OlapGrid Report"
saveFileDialog.AddExtension = True
saveFileDialog.DefaultExt = "csv"
saveFileDialog.Filter = "CSV (.csv)|*.csv"
If saveFileDialog.ShowDialog() = True Then
    Dim fileName As String = saveFileDialog.FileName
    Dim gridCsvExport As New GridCsvExport(Me.olapGrid.InternalGrid.Engine)
    gridCsvExport.Export(fileName)
End If

{% endhighlight %}

{% endtabs %}