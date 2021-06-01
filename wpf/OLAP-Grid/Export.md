---
layout: post
title: Export| OLAP Grid | Wpf | Syncfusion
description: export
platform: wpf
control: OLAP Grid
 documentation: ug
---

# Export

The OLAP grid data can be exported to Microsoft Excel, Microsoft Word, and PDF file formats. This can be achieved using the following methods of the OLAP grid.

## Excel export

{% tabs %}
  {% highlight c# %}

    



// Export OlapGrid Data to Excel

this.OlapGrid1.ExportToExcel("fileName");

    {% endhighlight %}





  {% highlight vbnet %}

   



' Export OlapGrid Data to Excel 

Me.OlapGrid1.ExportToExcel("fileName")

    {% endhighlight %}


{% endtabs %}


![Exports OlapGrid into excel document](Exporting_images/Export_img1.png)




## Word export

{% tabs %}
  {% highlight c# %}

    



// Export OlapGrid Data to Word

this.OlapGrid1.ExportToWord("fileName");

    {% endhighlight %}





  {% highlight vbnet %}

     



' Export OlapGrid Data to Word 

Me.OlapGrid1.ExportToWord("fileName")

    {% endhighlight %}

{% endtabs %}





![Exports OlapGrid into word document](Exporting_images/Export_img2.png)


## PDF export

{% tabs %}
  {% highlight c# %}

    



// Export OlapGrid Data to PDF

this.OlapGrid1.ExportToPdf("fileName");

    {% endhighlight %}





  {% highlight vbnet %}

    



' Export OlapGrid Data to PDF

Me.OlapGrid1.ExportToPdf("fileName")

    {% endhighlight %}


{% endtabs %}




![Exports OlapGrid into pdf document](Exporting_images/Export_img3.png)


The format state of grid is maintained on exported documents. 



### Sample location

A sample demo is available in the following location.

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Exporting\Exporting Grid Demo

## CSV export

The OLAP grid for WPF supports exporting itself to the CSV file format.


###  Methods



<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Type</th><th>
Return Type</th></tr>
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
Gets the pivot engine and file name for exporting the content to a CSV file format with the specified name. </td><td>
pivotEngine as PivotEngine, filename as string</td><td>
-</td><td>
void</td></tr>
</table>


## Adding CSV export for OLAP grid in an application

The GridCsvExport class supports for exporting data from OLAP grid to a CSV file format. Add the following assembly along with default assemblies in the reference folder:

* Syncfusion.OlapGridConverter.Wpf

{% tabs %}
  {% highlight c# %}

     

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

    {% endhighlight %}



  {% highlight vbnet %}

   

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

    {% endhighlight %}

{% endtabs %}



![Exports OlapGrid into CSV document](Exporting_images/Export_img4.png)


### Sample link

{Installation Drive}:\Users\<user name>\AppData\Local\Syncfusion\EssentialStudio\<version    number>\BI\WPF\OlapGrid.Wpf\Samples\Exporting\Exporting Demo

