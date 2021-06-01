---
layout: post
title: Save a report as stream | ReportWriter | WPF | Syncfusion
description: save a report to stream
platform: wpf
control: ReportWriter
 documentation: ug
---

# Save a report as stream

You can save a report to stream using Save(Stream, WriterFormat) (overloaded method). This method is useful when generating the report on the server side and sending it to a client-side application. The following code explains how to save a report as a stream.

{% tabs %}
{% highlight C# %}
//Step 1: create the report data source
ReportDataSourceCollection dataSources = new ReportDataSourceCollection();
dataSources.Add(new ReportDataSource() { Name = "Sales", Value = GetDataSource() });

//Step 2: Instantiate the report writer with the parameter "ReportPath" and "ReportDataSourceCollection"
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
MemoryStream stream = new MemoryStream();

//Step 3: Save the report as PDF, Word or Excel document in the form of stream contents
reportWriter.Save(stream, WriterFormat.PDF);
{% endhighlight %}
{% highlight vbnet %}
'Step 1: Create the report data source
Dim dataSources As New ReportDataSourceCollection()
dataSources.Add(New ReportDataSource() With {.Name = "Sales", .Value = GetDataSource()})

'Step 2: Instantiate the report writer with the parameter "ReportPath" and "ReportDataSourceCollection"
Dim reportWriter As New ReportWriter(reportPath, dataSources)
Dim stream As New MemoryStream()

'Step 3: Save the report as PDF, Word or Excel document in the form of stream contents
reportWriter.Save(stream WriterFormat.PDF)
{% endhighlight %}
{% endtabs %}

