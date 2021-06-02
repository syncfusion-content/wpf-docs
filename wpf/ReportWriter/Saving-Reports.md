---
layout: post
title: Saving Reports | ReportWriter | WPF | Syncfusion
description: Saving reports in Syncfusion Essential Studio WPF ReportWriter control, its elements, features, and more.
platform: wpf
control: ReportWriter
documentation: ug
---

# Saving reports in WPF ReportWriter Control

Essential ReportWriter provides support for saving a report as a PDF, Word, Excel and HTML documents with the help of the class ReportWriter. The report elements such as Tablix, matrices, charts, gauges, shapes, and text boxes are supported in this feature. 

## Saving report as PDF 

The report generated using the ReportDesigner can be exported as a PDF document using the following code.

{% tabs %}
{% highlight C# %}
//Instantiate the report writer with the parameter "ReportPath" and "ReportDataSourceCollection".
ReportWriter reportWriter = new ReportWriter(reportpath, dataSources);
reportWriter.Save("Sample.pdf", WriterFormat.PDF);
{% endhighlight %}
{% highlight vbnet %}
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSourceCollection".
Dim reportWriter As New ReportWriter (reportpath, dataSources)
reportWriter.Save("Sample.pdf", WriterFormat.PDF)
{% endhighlight %}
{% endtabs %}

![Saving-Reports_images1](Saving-Reports_images/Saving-Reports_img1.png) 

## Saving report as Excel 

The report generated using the ReportDesigner can be exported as an Excel document using the following code example. 

{% tabs %}
{% highlight C# %}
//Instantiate the report writer with the parameter "ReportPath" and "ReportDataSourceCollection".
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
reportWriter.Save("Sample.xls", WriterFormat.Excel);
{% endhighlight %}
{% highlight vbnet %}
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSourceCollection".
Dim reportWriter As New ReportWriter (reportPath, dataSources)
reportWriter.Save("Sample.xls", WriterFormat.Excel)
{% endhighlight %}
{% endtabs %}

![Saving-Reports_images2](Saving-Reports_images/Saving-Reports_img2.png) 

## Saving report as Word 

The report generated using the ReportDesigner can also be exported as a Word document using the following code example.

{% tabs %}
{% highlight C# %}
// Instantiate the report writer with the parameter "ReportPath" and "ReportDataSourceCollection".
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
reportWriter.Save("Sample.doc", WriterFormat.WORD);
{% endhighlight %}
{% highlight vbnet %}
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSourceCollection".
Dim reportWriter As New ReportWriter (reportPath, dataSources)
reportWriter.Save("Sample.doc", WriterFormat.WORD)
{% endhighlight %}
{% endtabs %}

![Saving-Reports_images3](Saving-Reports_images/Saving-Reports_img3.png) 

## Saving report as an HTML 

The report generated using the ReportDesigner can be exported as an HTML document using the following code example. 

{% tabs %}
{% highlight C# %}
//Instantiate the report writer with the parameter "ReportPath" and "ReportDataSourceCollection".
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
reportWriter.Save("Sample.html", WriterFormat.HTML);
{% endhighlight %}
{% highlight vbnet %}
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSourceCollection".
Dim reportWriter As New ReportWriter (reportPath, dataSources)
reportWriter.Save("Sample.html", WriterFormat.HTML)
{% endhighlight %}
{% endtabs %}

![Saving-Reports_images4](Saving-Reports_images/Saving-Reports_img4.png) 