---
layout: post
title: Export
description: export
platform: wpf
control: OLAP Client 
documentation: ug
---

# Export

When creating OLAP Report in OLAP Client, the report will be previewed in the OLAP Chart and OLAP Grid. OLAP Client has the option to export the current visual of this Chart and Grid to various forms.

## Export Options in Chart

The current visual of the chart can be exported to the following form:

* Word
* PDF
* Image
* Print

By clicking the Export menus in the Chart toolbar, the user can export the chart to the corresponding mode. 

{{ '![](Export_images/Export_img1.png)' | markdownify }}
{:.image }


_Export Menus in OlapChart Toolbar:_

<table>
<tr>
<th>
Icon</th><th>
Name</th><th>
Description</th></tr>
<tr>
<td>
![](Export_images/Export_img2.png)
{:.image }
</td><td>
Export Chart</td><td>
Export the current visual of the chart as Image</td></tr>
<tr>
<td>
![](Export_images/Export_img3.png)
{:.image }
</td><td>
Print</td><td>
Print the current visual of the chart</td></tr>
<tr>
<td>
![](Export_images/Export_img4.png)
{:.image }
</td><td>
Export to word</td><td>
Export the current visual of the chart to Word</td></tr>
<tr>
<td>
![](Export_images/Export_img5.png)
{:.image }
</td><td>
Export to PDF</td><td>
Export the current visual of the chart to PDF</td></tr>
</table>
## Export Options in Grid

The Grid can be exported to the following form:

* Word
* PDF
* Excel

The user can perform these exports in two ways:

1. Through OlapGrid Tool Bar menu
1. Through APIs

The OlapGridtoolbar provides the menu to perform the export operation. By clicking any one of the Export buttons, the user can export the grid to the corresponding format.

{{ '![](Export_images/Export_img6.png)' | markdownify }}
{:.image }


_Export menus in OlapGrid Toolbar_

<table>
<tr>
<td>
Icon</td><td>
Name</td><td>
Description</td></tr>
<tr>
<td>
![](Export_images/Export_img7.png)
{:.image }
</td><td>
Export to Excel</td><td>
Export the Grid to Excel</td></tr>
<tr>
<td>
![](Export_images/Export_img8.png)
{:.image }
</td><td>
Export to word</td><td>
Export the Grid to Word</td></tr>
<tr>
<td>
![](Export_images/Export_img9.png)
{:.image }
</td><td>
Export to PDF</td><td>
Export the Grid to PDF</td></tr>
</table>
## CSV Export

OLAP Client for WPF provides support to export OLAP Grid to CSV file format. 

Use Case Scenarios 

You can export the contents of the OLAP Grid in OLAP Client to the CSV file format for future references and analysis purposes.

Methods

_Methods_

<table>
<tr>
<td>
Method</td><td>
Description</td><td>
Parameters</td><td>
    Type</td><td>
Return Type</td></tr>
<tr>
<td>
Export(string filename)</td><td>
Gets the file name to save the file with the specified name.</td><td>
filename as string</td><td>
-</td><td>
void</td></tr>
<tr>
<td>
ExportToCsv(PivotEngine pivotEngine, string filename)</td><td>
Gets the Pivot Engine and file name for exporting the content to CSV file format with the specified name. </td><td>
pivotEngine as PivotEngine, filename as string</td><td>
-</td><td>
void</td></tr>
</table>


Adding CSV Export for OLAP Client in an application

The GridCsvExport class provides support for exporting data from OLAP Grid in OLAP Client to a CSV file format. Add the following dll, along with the default dll’s in the reference folder: 

* Syncfusion.OlapGridConverter.Wpf



[C#] 

SaveFileDialog saveFileDialog = new SaveFileDialog();

saveFileDialog.AddExtension = true;

saveFileDialog.FileName = "OlapGrid Report";

saveFileDialog.DefaultExt = "CSV";

saveFileDialog.Filter = "Csv file (.csv)|*.csv";

if (saveFileDialog.ShowDialog() == true)

{

   if (this.olapGrid.InternalGrid != null && this.olapGrid.InternalGrid.Engine != null)

   {

        GridCsvExport gridCsvExport = new GridCsvExport(this.olapGrid.InternalGrid.Engine);

        gridCsvExport.Export(saveFileDialog.FileName);

        MessageBox.Show("CSV document exported successfully!");

   }

} 



[VB]

Dim saveFileDialog As New SaveFileDialog()

saveFileDialog.AddExtension = True

saveFileDialog.FileName = "OlapGrid Report"

saveFileDialog.DefaultExt = "CSV"

saveFileDialog.Filter = "Csv file (.csv)|*.csv"

If saveFileDialog.ShowDialog() = True Then

If Me.olapGrid.InternalGrid IsNot Nothing AndAlso Me.olapGrid.InternalGrid.Engine IsNot Nothing Then

        Dim gridCsvExport As New GridCsvExport(Me.olapGrid.InternalGrid.Engine)

        gridCsvExport.Export(saveFileDialog.FileName)

        MessageBox.Show("CSV document exported successfully!")

End If

End If





{{ '![](Export_images/Export_img10.png)' | markdownify }}
{:.image }


{{ '![](Export_images/Export_img11.png)' | markdownify }}
{:.image }


Sample Link

{Installation Drive}:\Users\<user name>\AppData\Local\Syncfusion\EssentialStudio\<version    number>\BI\WPF\OlapClient.Wpf\Samples\Appearance\OlapClientCustomizationDemo

