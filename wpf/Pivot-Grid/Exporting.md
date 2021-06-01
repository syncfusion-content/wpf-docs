---
layout: post
title: Exporting in WPF Pivot Grid control | Syncfusion
description: Learn about Exporting support in Syncfusion Essential Studio WPF Pivot Grid control, its elements and more.
platform: wpf
control: Pivot grid
 documentation: ug
---

# Exporting in WPF Pivot Grid

The pivot grid provides an option to export its content to various formats. It provides the following exporting options.

* Microsoft Excel format - Cell and pivot table mode
* Microsoft Word format
* PDF format
* CSV format

## Export to Excel

The pivot grid can be exported to an Excel document using Syncfusion XlsIO libraries. It consists of two exporting modes, and you can switch from one mode to another mode using the `ExportMode` property.

* **Pivot Table**: Exports the pivot grid directly as a pivot table like in Microsoft Excel.
* **Cell**: Exports the pivot grid as individual cell values.

To export the pivot grid contents to Excel, add **Syncfusion.PivotGridConverter.Wpf.dll** and **Syncfusion.XlsIO.Base** assemblies to your application and include the namespace **Syncfusion.Windows.Controls.PivotGrid.Converter** to access the `GridExcelExport` class.

Now, define the pivot grid control and bind the data source along with pivot rows, pivot columns, and pivot calculations. Create an instance of `GridExcelExport` class and then invoke the `Export` method in it. `OpenFileDialog` and `SaveFileDialog` options are used to save the exported file in the preferred location.

Refer to the following code sample.

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

![Excel Export in PivotTable Mode](Exporting-Images/Export to excel in PivotTable mode.png)

Excel Export in PivotTable Mode
{:.caption}

![Excel Export in Cell Mode](Exporting-Images/Export to excel in Cell mode.png)

Excel Export in Cell Mode
{:.caption}

## Export to Word

To export the pivot grid contents to Word, add the **Syncfusion.PivotGridConverter.Wpf.dll** assembly to your application and include the namespace **Syncfusion.Windows.Controls.PivotGrid.Converter** to access the `GridWordExport` class.

Now, define the pivot grid control and bind the data source along with pivot rows, pivot columns, and pivot calculations. Create an instance for `GridWordExport` class and then invoke the `Export` method in it. `OpenFileDialog` and `SaveFileDialog` options are used to save the exported file in the preferred location.

Refer to the following code sample.

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

![Exports the PivotGrid into word document](Exporting-Images/Export to word.png)

## Export to PDF

To export the pivot grid contents to PDF, add **Syncfusion.PivotGridConverter.Wpf.dll** assembly to your application and include the namespace **Syncfusion.Windows.Controls.PivotGrid.Converter** to access the `GridPdfExport` class.

Now, define the pivot grid control and bind the data source along with pivot rows, pivot columns, and pivot calculations. Create an instance for `GridPdfExport` class and then, invoke the `Export` method in it. `OpenFileDialog` and `SaveFileDialog` options are used to save the exported file in the preferred location.

Refer to the following code sample.

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

![Exports the PivotGrid into PDF document](Exporting-Images/Export to pdf.png)

## Export to CSV

To export the pivot grid contents to CSV, add the **Syncfusion.PivotGridConverter.Wpf.dll** assembly to your application and include the namespace **Syncfusion.Windows.Controls.PivotGrid.Converter** to access the `GridCsvExport` class.

Now, define the pivot grid control and bind the data source along with pivot rows, pivot columns, and pivot calculations. Create an instance of `GridCsvExport` class and then invoke the `Export` method in it. `OpenFileDialog` and `SaveFileDialog` options are used to save the exported file in the preferred location.

Refer to the following code sample.

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

![Exports the PivotGrid into CSV document](Exporting-Images/Export to csv.png)

## Threshold limitations

The following table represents the number of rows and columns to be taken in account while exporting the pivot grid control without affecting its performance.

    <table>
        <tr>
            <th>
                Functionality</th>
            <th>
                Row Count</th>
            <th>
                Column Count</th>
        </tr>
        <tr>
            <td>
                Exporting PivotGrid contents to Excel document in Cell mode</td>
            <td>
                300</td>
            <td>
                70</td>
        </tr>
        <tr>
            <td>
                Exporting PivotGrid contents to Excel document in PivotTable mode</td>
            <td>
                No threshold limit</td>
            <td>
                No threshold limit</td>
        </tr>
        <tr>
            <td>
                Exporting PivotGrid contents to Word document</td>
            <td>
                1800</td>
            <td>
                70</td>
        </tr>
        <tr>
            <td>
                Exporting PivotGrid contents to PDF document</td>
            <td>
                800</td>
            <td>
                70</td>
        </tr>
        <tr>
            <td>
                Exporting PivotGrid contents to CSV document</td>
            <td>
                No threshold limit</td>
            <td>
                No threshold limit</td>
        </tr>
    </table>
