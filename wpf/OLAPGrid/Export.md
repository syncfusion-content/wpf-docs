---
layout: post
title: Export| OLAP Grid | Wpf | Syncfusion
description: export
platform: wpf
control: OLAP Grid
documentation: ug
---

# Export

The OlapGrid Data can be exported to Excel, Word and PDF file formats. The OlapGrid data can be exported using the following methods of OlapGrid.

## Excel Export

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


![Excel Export](Export_images/Export_img1.png)




## Word Export

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





![Word Export](Export_images/Export_img2.png)


## Pdf Export

{% tabs %}
  {% highlight c# %}

    



// Export OlapGrid Data to Pdf

this.OlapGrid1.ExportToPdf("fileName");

    {% endhighlight %}





  {% highlight vbnet %}

    



' Export OlapGrid Data to Pdf 

Me.OlapGrid1.ExportToPdf("fileName")

    {% endhighlight %}


{% endtabs %}




![](Export_images/Export_img3.png)


The Format state of Grid is maintained on exported documents. 



### Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Exporting\Exporting Grid Demo

## CSV Export

OLAP Grid for WPF provides support to export itself to CSV file format. 

## Adding CSV Export for OLAP Grid in an application

The GridCsvExport class provides you support for exporting data from OLAP Grid to a CSV file format. Add the following dll along with the default dll’s in the reference folder: 

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



![](Export_images/Export_img4.png)


### Sample Link

{Installation Drive}:\Users\<user name>\AppData\Local\Syncfusion\EssentialStudio\<version    number>\BI\WPF\OlapGrid.Wpf\Samples\Exporting\Exporting Demo

