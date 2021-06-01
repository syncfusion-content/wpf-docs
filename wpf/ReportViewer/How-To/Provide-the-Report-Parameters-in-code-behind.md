---
layout: post
title: Provide the Report Parameters in code behind | ReportViewer | WPF | Syncfusion
description: provide the report parameters in code behind
platform: wpf
control: ReportViewer
 documentation: ug
---

# Provide the Report Parameters in code behind

Use the SetParameters method in the Report Viewer to provide the parameter values for rendering reports. Note that this method can also be used in a ReportLoaded event to avoid unexpected issues.

{% highlight C# %}
this.reportViewerControl.ReportLoaded += new Syncfusion.Windows.Reports.ReportLoadedEventHandler(reportViewerControl_ReportLoaded);
void reportViewerControl_ReportLoaded(object sender, EventArgs e)
{
    //this.reportViewerControl.SetParameters
}
{% endhighlight %}