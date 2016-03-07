---
layout: post
title: 13418-Exporting
description: Exporting
platform: wpf
control: PivotGridControl
documentation: ug
---

# Exporting

PivotGrid provides an option to export its content to various formats. It provides the following exporting options.

   * Excel format - Cell and PivotTable mode
   * Word format
   * PDF format
   * CSV format
   
## Export to Excel

PivotGrid can be exported to an excel document using Syncfusion XlsIO libraries. It consist of two exporting modes listed below and it is possible to switch the exporting modes using the `ExportMode` property.

* **Pivot Table** - It exports the PivotGrid directly as a PivotTable like in MS Excel.
* **Cell** - It exports the PivotGrid as an individual cell values.

To export the PivotGrid contents to Excel, add **Syncfusion.PivotGridConverter.Wpf.dll** and **Syncfusion.XlsIO.Base** assemblies to your application and include the namespace **Syncfusion.Windows.Controls.PivotGrid.Converter** in-order to access the `GridExcelExport` class.

Now define the PivotGrid control and bind the data source along with PivotRows, PivotColumns and PivotCalculations. Create an instance of `GridExcelExport` class and then invoke the `Export` method in it. `OpenFileDialog` and `SaveFileDialog` options are used to save the exported file in the preferred location.

Please refer the below code sample.

{% highlight C# %}

private void Button_Export(object sender, RoutedEventArgs e)) {
    ////Export to Excel document
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

![](Exporting-Images/Export to excel in PivotTable mode.png)

_Excel Export in PivotTable Mode_

![](Exporting-Images/Export to excel in Cell mode.png)

_Excel Export in Cell Mode_

## Export to Word

To export the PivotGrid contents to Word, add the **Syncfusion.PivotGridConverter.Wpf.dll** assembly to your application and include the namespace **Syncfusion.Windows.Controls.PivotGrid.Converter** in-order to access the `GridWordExport` class.

Now define the PivotGrid control and bind the data source along with PivotRows, PivotColumns and PivotCalculations. Create an instance for `GridWordExport` class and then invoke the `Export` method in it. `OpenFileDialog` and `SaveFileDialog` options are used to save the exported file in the preferred location.

Please refer the below code sample. 

{% highlight C# %}

private void Button_Export(object sender, RoutedEventArgs e)) {
    //// Export to Word document
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

![](Exporting-Images/Export to word.png)

## Export to PDF

To export the PivotGrid contents to PDF, add **Syncfusion.PivotGridConverter.Wpf.dll** assembly to your application and include the namespace **Syncfusion.Windows.Controls.PivotGrid.Converter** in-order to access the `GridPdfExport` class.

Now define the PivotGrid control and bind the data source along with PivotRows, PivotColumns and PivotCalculations. Create an instance for `GridPdfExport` class and then invoke the `Export` method in it. `OpenFileDialog` and `SaveFileDialog` options are used to save the exported file in the preferred location.

Please refer the below code sample.

{% highlight C# %}

private void Button_Export(object sender, RoutedEventArgs e)) {
    ////Export to PDF document
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

![](Exporting-Images/Export to pdf.png)

## Export to CSV

To export the PivotGrid contents to CSV, add the **Syncfusion.PivotGridConverter.Wpf.dll** assembly to your application and include the namespace **Syncfusion.Windows.Controls.PivotGrid.Converter** in order to access the `GridCsvExport` class.

Now define the PivotGrid control and bind the data source along with PivotRows, PivotColumns and PivotCalculations. Create an instance of `GridCsvExport` class and then invoke the `Export` method in it. `OpenFileDialog` and `SaveFileDialog` options are used to save the exported file in the preferred location.

Please refer the below code sample. 

{% highlight C# %}

private void Button_Export(object sender, RoutedEventArgs e)) {
    ////Export to CSV document
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

![](Exporting-Images/Export to csv.png)
