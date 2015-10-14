---
layout: post
title: Saving as an Excel Document | ReportWriter | WPF | Syncfusion
description: saving as an excel document
platform: wpf
control: ReportWriter
documentation: ug
---

# Saving as an Excel Document

The RDL report generated using the Report Designer can be exported as an Excel document using the following code example. 

{% tabs %}

{% highlight C# %}

//Instantiate the report writer with the parameter "ReportPath" and 

ReportDataSource Collection

ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);

reportWriter.Save("Sample.xls", WriterFormat.Excel);
{% endhighlight %}

{% highlight vbnet %}

'Instantiate the report writer with the parameter "ReportPath" and 

ReportDataSource Collection

Dim reportWriter As New ReportWriter (reportPath, dataSources)

reportWriter.Save("Sample.xls", WriterFormat.Excel);

{% endhighlight %}

{% endtabs %}