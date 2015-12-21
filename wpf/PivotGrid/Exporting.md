---
layout: post
title: 13418-Exporting
description: Exporting
platform: wpf
control: PivotGridControl
documentation: ug
---

# Exporting

PivotGrid provides an option to export the grid to various formats. It provides the following exporting options.

   * Excel format - Cell and PivotTable mode
   * Word format
   * Pdf format
   * CSV format
   
**Use Case Scenario**

User could export the contents of the PivotGrid to any of the mentioned formats for future archival, references and analysis purposes.

                                                             Methods Table

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Return Type</th></tr>
<tr>
<td>
Export(string filename)</td><td>
Gets the file name to save the file with the specified name and format.</td><td>
string filename</td><td>
void</td></tr>
</table>

## Export to Excel

PivotGrid can be exported to an excel document using the Essential XlsIO. It consist of two exporting mode options listed below and it is possible to switch the exporting mode options by using **ExportMode** property.

* Pivot Table - It is used to export the PivotGrid directly as a pivot table to view in excel.
* Cell - It exports the PivotGrid as an individual cell values.

                                                          Property Table
<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Value It Accepts</th><th>
Reference Link</th></tr>
<tr>
<td>
ExportMode</td><td>
Used to set the exporting mode for the PivotGrid.</td><td>
ExportMode</td><td>
Cell, PivotTable</td><td>
-</td></tr>
</table>

**Adding the Export method to PivotGrid**

The **GridExcelExport** class provides support for exporting data from a PivotGrid to an Excel spreadsheet for verification and/or computation.

Add the **Syncfusion.PivotGridConverter.Wpf.dll**, **Syncfusion.XlsIO.Base** assemblies to your application and include the namespace ** Syncfusion.Windows.Controls.PivotGrid.Converter** in order to access the GridExcelExport class.
 
Then, define the PivotGrid control and bind the data source, PivotRows, PivotColumns and PivotCalculations. Create the instance for GridExcelExport class and call the Export() method in it. OpenFileDialog and SaveFileDialog options are used to save your exported file in your preferred location.

Please refer the below code snippet.

{% highlight C# %}

private void Button_Export(object sender, RoutedEventArgs e)) {
    //// Export to Excel.
    SaveFileDialog savedialog = new SaveFileDialog();
    savedialog.AddExtension = true;
    savedialog.FileName = "Sample";
    savedialog.DefaultExt = "xlsx";
    savedialog.Filter = "Excel file (.xlsx)|*.xlsx";
    if (savedialog.ShowDialog() == true) {
        fileName = savedialog.FileName;
        GridExcelExport excelExport = new GridExcelExport(pivotGrid, Syncfusion.XlsIO.ExcelVersion.Excel2007);
        excelExport.ExportMode = ExportModes.PivotTable;
        excelExport.Export(fileName);
    }
}

{% endhighlight %}

![](Exporting Images/Export to excel in PivotTable mode.png)

_Export to excel in PivotTable mode_

![](Exporting Images/Export to excel in Cell mode.png)

_Export to excel in Cell mode_

### Export to Word

The **GridWordExport** class provides support for exporting data from a PivotGrid to an Word document for verification.

Add the **Syncfusion.PivotGridConverter.Wpf.dll** assembly to your application and include the namespace ** Syncfusion.Windows.Controls.PivotGrid.Converter** in order to access the GridWordExport class.
 
Then, define the PivotGrid control and bind the data source, PivotRows, PivotColumns and PivotCalculations. Create the instance for GridWordExport class and call the Export() method in it. OpenFileDialog and SaveFileDialog options are used to save your exported file in your preferred location.

Please refer the below code snippet.

{% highlight C# %}

private void Button_Export(object sender, RoutedEventArgs e)) {
    //// Export to Word Document.
    SaveFileDialog savedialog = new SaveFileDialog();
    savedialog.AddExtension = true;
    savedialog.FileName = "Sample";
    savedialog.DefaultExt = "Doc";
    savedialog.Filter = "Word file (.Doc)|*.Doc";
    if (savedialog.ShowDialog() == true) {
        fileName = savedialog.FileName;
        GridWordExport wordExport = new GridWordExport(pivotGrid);
        wordExport.Export(fileName);
    }
}

{% endhighlight %}

![](Exporting Images/Export to word.png)

### Export to Pdf

The **GridPdfExport** class provides support for exporting data from a PivotGrid to an Pdf document for verification.

Add the **Syncfusion.PivotGridConverter.Wpf.dll** assembly to your application and include the namespace ** Syncfusion.Windows.Controls.PivotGrid.Converter** in order to access the GridPdfExport class.
 
Then, define the PivotGrid control and bind the data source, PivotRows, PivotColumns and PivotCalculations. Create the instance for GridPdfExport class and call the Export() method in it. OpenFileDialog and SaveFileDialog options are used to save your exported file in your preferred location.

Please refer the below code snippet.

{% highlight C# %}

private void Button_Export(object sender, RoutedEventArgs e)) {
    //// Export to PDF Document.
    SaveFileDialog savedialog = new SaveFileDialog();
    savedialog.AddExtension = true;
    savedialog.FileName = "Sample";
    savedialog.DefaultExt = "pdf";
    savedialog.Filter = "Pdf file (.pdf)|*.pdf";
    if (savedialog.ShowDialog() == true) {
        fileName = savedialog.FileName;
        GridPdfExport pdfExport = new GridPdfExport(pivotGrid);
        pdfExport.Export(fileName);
    }
}

{% endhighlight %}

![](Exporting Images/Export to pdf.png)

### Export to CSV

The **GridCsvExport** class provides support for exporting data from a PivotGrid to an Word document for verification.

Add the **Syncfusion.PivotGridConverter.Wpf.dll** assembly to your application and include the namespace **Syncfusion.Windows.Controls.PivotGrid.Converter** in order to access the GridCsvExport class.
 
Then, define the PivotGrid control and bind the data source, PivotRows, PivotColumns and PivotCalculations. Create the instance for GridCsvExport class and call the Export() method in it. OpenFileDialog and SaveFileDialog options are used to save your exported file in your preferred location.

Please refer the below code snippet.

{% highlight C# %}

private void Button_Export(object sender, RoutedEventArgs e)) {
    //// Export to CSV Document.
    SaveFileDialog savedialog = new SaveFileDialog();
    savedialog.AddExtension = true;
    savedialog.FileName = "Sample";
    savedialog.DefaultExt = "CSV";
    savedialog.Filter = "CSV file (.csv)|*.csv";
    if (savedialog.ShowDialog() == true) {
        fileName = savedialog.FileName;
        GridCsvExport csvExport = new GridCsvExport(pivotGrid);
        csvExport.Delimiter = ",";
        csvExport.Export(fileName);
    }
}

{% endhighlight %}

![](Exporting Images/Export to csv.png)
