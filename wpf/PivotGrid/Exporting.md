---
layout: post
title: Exporting
description: Exporting
platform: wpf
control: PivotGrid
documentation: ug
---


# Exporting

## PDF Export

PivotGrid for WPF can be exported as a PDF file using Essential PDF. . The user can export the contents of the PivotGrid to the PDF document for future archival, references and analysis purposes.

### Call Export method

The GridPdfExport class provides support for exporting data from a PivotGrid to a PDF document for verification. The following dlls should be added, along with the default dlls in the reference folder: 

  * Syncfusion.PivotGridConverter.Wpf

{% highlight C# %}  



//// Export to PDF.

SaveFileDialog savedialog = new SaveFileDialog();

savedialog.AddExtension = true;

savedialog.FileName = "Sample";

savedialog.DefaultExt = "pdf";

savedialog.Filter = "Pdf file (.pdf)|*.pdf";

if (savedialog.ShowDialog() == true)

{

     fileName = savedialog.FileName;

     GridPdfExport pdfExport = new GridPdfExport(this.pivotGrid1);

     pdfExport.Export(fileName);

}

{% endhighlight %} 

{% highlight vbnet %} 

' Export to PDF.

Dim savedialog As SaveFileDialog = New SaveFileDialog()

savedialog.AddExtension = True

savedialog.FileName = "Sample"

savedialog.DefaultExt = "pdf"

savedialog.Filter = "Pdf file (.pdf)|*.pdf"

If savedialog.ShowDialog() = True Then

    fileName = savedialog.FileName

    Dim pdfExport As GridPdfExport = New GridPdfExport(Me.pivotGrid1)

    pdfExport.Export(fileName)

End If

{% endhighlight %} 


![](Features_images/Features_img15.png)



## Excel Export

PivotGrid for WPF can be exported as an XLS file using Essential XlsIO. The user can export the contents of the PivotGrid to the Excel document for future archival, references and analysis purposes.

### Call Export method

The GridExcelExport class provides support for exporting data from a PivotGrid to an Excel spreadsheet for verification and/or computation. The following dlls should be added, along with the default dlls in the reference folder: 

*  Syncfusion.PivotGridConverter.Wpf

{% highlight C# %}  


//// Export to Excel.

SaveFileDialog savedialog = new SaveFileDialog();

savedialog.AddExtension = true;

savedialog.FileName = "Sample";

savedialog.DefaultExt = "xls";

savedialog.Filter = "Excel file (.xls)|*.xls";

if (savedialog.ShowDialog() == true)

{
     fileName = savedialog.FileName;

     GridExcelExport excelExport = new GridExcelExport(this.pivotGrid1);

     excelExport.Export(fileName);
}

{% endhighlight %} 


{% highlight vbnet %} 


' Export to Excel.

Dim savedialog As SaveFileDialog = New SaveFileDialog()

savedialog.AddExtension = True

savedialog.FileName = "Sample"

savedialog.DefaultExt = "xls"

savedialog.Filter = "Excel file (.xls)|*.xls"

If savedialog.ShowDialog() = True Then

    fileName = savedialog.FileName

    Dim excelExport As GridExcelExport = New GridExcelExport(Me.pivotGrid1)

    excelExport.Export(fileName)

End If

{% endhighlight %} 


![](Features_images/Features_img16.png)



## Word Export

PivotGrid for WPF can be exported as a Word document using Essential DocIO. The user can export the contents of the PivotGrid to the Word document for future archival, references and analysis purposes.

### Call Export method

The GridWordExport class provides support for exporting data from a PivotGrid to a Word document for verification. The following dlls should be added, along with the default dlls in the reference folder: 

 *Syncfusion.PivotGridConverter.Wpf

 
{% highlight C# %}  


//// Export to Word Document.

SaveFileDialog savedialog = new SaveFileDialog();

savedialog.AddExtension = true;

savedialog.FileName = "Sample";

savedialog.DefaultExt = "Doc";

savedialog.Filter = "Word file (.Doc)|*.Doc";

if (savedialog.ShowDialog() == true)

{

     fileName = savedialog.FileName;

     GridWordExport wordExport = new GridWordExport(this.pivotGrid1);

     wordExport.Export(fileName);

}

{% endhighlight %} 


{% highlight vbnet %} 


' Export to Word Document.

Dim savedialog As SaveFileDialog = New SaveFileDialog()

savedialog.AddExtension = True

savedialog.FileName = "Sample"

savedialog.DefaultExt = "Doc"

savedialog.Filter = "Word file (.Doc)|*.Doc"

If savedialog.ShowDialog() = True Then

    fileName = savedialog.FileName

    Dim wordExport As GridWordExport = New GridWordExport(Me.pivotGrid1)

    wordExport.Export(fileName)

End If

{% endhighlight %} 

![](Features_images/Features_img17.png)



## CSV Export

PivotGridControl for WPF provides support to export itself to CSV file format. 

## Use Case Scenarios 

You can export the contents of the PivotGridControl to the CSV file format for future references and analysis purposes.

Methods

<table>
<tr>
<th>
{{ '**Method**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Parameters**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<td>
Export(string filename)</td><td>
Gets the file name to save the CSV file with the specified name.</td><td>
filename as string</td><td>
-</td><td>
void</td></tr>
<tr>
<td>
ExportToCsv(PivotGridControl pivotGridControl, string filename)</td><td>
Gets the PivotGridControl and file name for exporting the content to CSV file format with the specified name. </td><td>
pivotGridControl as PivotGridControl, filename as string</td><td>
-</td><td>
void</td></tr>
</table> 

## Adding CSV Export for PivotGridControl in an application

The GridCsvExport class provides support for exporting data from PivotGridControl to a CSV file format. You are required to add the following dll along with the default dll’s in the reference folder: 

* Syncfusion.PivotGridConverter.Wpf


{% highlight C# %}  


SaveFileDialog saveFileDialog = new SaveFileDialog();

saveFileDialog.AddExtension = true;

saveFileDialog.FileName = "Sample";

saveFileDialog.DefaultExt = "CSV";

saveFileDialog.Filter = "Csv file (.csv)|*.csv";

if (saveFileDialog.ShowDialog() == true)

{

GridCsvExport csvExport = new GridCsvExport(this.Target);                                         
csvExport.Delimiter = ",";                                
csvExport.Export(saveFileDialog.FileName);                               
MessageBox.Show("CSV document exported successfully!");

} 

{% endhighlight %}

![](Features_images/Features_img18.png)

 

### Sample Link

{Installation Drive}:\Users\<user name>\AppData\Local\Syncfusion\EssentialStudio\<version number>\ WPF\PivotAnalysis.WPF\Samples\Exporting\Exporting Demo\

### Sample Link

To access a Exporting Demo sample:

1. Open the Syncfusion Dashboard. 
2. Click Business Intelligence.
3. Click the WPF drop-down list, and select Explore Samples. 
4. Navigate to PivotAnalysis.WPF -> Samples -> Exporting -> Exporting Demo.


