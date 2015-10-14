---
layout: post
title: Saving as a PDF Document | ReportWriter | WPF | Syncfusion
description: saving as a pdf document 
platform: wpf
control: ReportWriter
documentation: ug
---

# Saving as a PDF Document 

The RDL report generated using the Report Designer can be exported as a PDF document using the following code.

{% tabs %}

{% highlight C# %}
//Instantiate the report writer with the parameter "ReportPath" and 

“ReportDataSource” Collection

ReportWriter reportWriter = new ReportWriter(reportpath, dataSources);

reportWriter.Save("Sample.pdf", WriterFormat.PDF);
{% endhighlight %}

{% highlight vbnet %}
'Instantiate the report writer with the parameter "ReportPath" and 

ReportDataSource Collection

Dim reportWriter As New ReportWriter (reportpath, dataSources)

reportWriter.Save("Sample.pdf", WriterFormat.PDF);
{% endhighlight %}

{% endtabs %}
