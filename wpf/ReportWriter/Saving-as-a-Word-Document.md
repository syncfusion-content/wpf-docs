---
layout: post
title: Saving as a Word Document | ReportWriter | WPF | Syncfusion
description: saving as a word document
platform: wpf
control: ReportWriter
documentation: ug
---

# Saving as a Word Document

The RDL report generated using the Report Designer can also be exported as a Word document. The following code example demonstrates how to do this.

{% tabs %}

{% highlight C# %}
// Instantiate the report writer with the parameter "ReportPath" and 

ReportDataSource Collection

ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);

reportWriter.Save("Sample.doc", WriterFormat.WORD);
{% endhighlight %}

{% highlight vbnet %}
'Instantiate the report writer with the parameter "ReportPath" and 

ReportDataSource Collection.

Dim reportWriter As New ReportWriter (reportPath, dataSources)

reportWriter.Save("Sample.doc", WriterFormat.WORD);
{% endhighlight %}

{% endtabs %}
