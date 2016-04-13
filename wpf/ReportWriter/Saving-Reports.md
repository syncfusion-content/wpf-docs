---
layout: post
title: Saving Reports | ReportWriter | WPF | Syncfusion
description: saving reports
platform: wpf
control: ReportWriter
documentation: ug
---

# Saving Reports

Essential Report Writer provides support for saving a report as a PDF, Word, Excel and Html documents with the help of the class ReportWriter. The report elements such as Tablix, matrices, charts, gauges, shapes, and text boxes are supported in this feature. 

## Saving Report as PDF 

The report generated using the Report Designer can be exported as a PDF document using the following code.

{% tabs %}
{% highlight C# %}
//Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
ReportWriter reportWriter = new ReportWriter(reportpath, dataSources);
reportWriter.Save("Sample.pdf", WriterFormat.PDF);
{% endhighlight %}
{% highlight vbnet %}
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
Dim reportWriter As New ReportWriter (reportpath, dataSources)
reportWriter.Save("Sample.pdf", WriterFormat.PDF)
{% endhighlight %}
{% endtabs %}

![](Saving-Reports_images/Saving-Reports_img1.png) 

## Saving Report as Excel 

The report generated using the Report Designer can be exported as an Excel document using the following code example. 

{% tabs %}
{% highlight C# %}
//Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
reportWriter.Save("Sample.xls", WriterFormat.Excel);
{% endhighlight %}
{% highlight vbnet %}
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
Dim reportWriter As New ReportWriter (reportPath, dataSources)
reportWriter.Save("Sample.xls", WriterFormat.Excel)
{% endhighlight %}
{% endtabs %}

![](Saving-Reports_images/Saving-Reports_img2.png) 

## Saving Report as Word 

The report generated using the Report Designer can also be exported as a Word document using the following code example.

{% tabs %}
{% highlight C# %}
// Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
reportWriter.Save("Sample.doc", WriterFormat.WORD);
{% endhighlight %}
{% highlight vbnet %}
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
Dim reportWriter As New ReportWriter (reportPath, dataSources)
reportWriter.Save("Sample.doc", WriterFormat.WORD)
{% endhighlight %}
{% endtabs %}

![](Saving-Reports_images/Saving-Reports_img3.png) 

## Saving Report as an HTML 

The report generated using the Report Designer can be exported as an HTML document using the following code example. 

{% tabs %}
{% highlight C# %}
//Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
reportWriter.Save("Sample.html", WriterFormat.HTML);
{% endhighlight %}
{% highlight vbnet %}
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
Dim reportWriter As New ReportWriter (reportPath, dataSources)
reportWriter.Save("Sample.html", WriterFormat.HTML)
{% endhighlight %}
{% endtabs %}

![](Saving-Reports_images/Saving-Reports_img4.png) 