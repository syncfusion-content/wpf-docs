---
layout: post
title: Data Source credential information in WPF ReportViewer | Syncfusion
description: Provide the data source credential information in code behind for Syncfusion WPF ReportViewer control, its elements, and more.
platform: wpf
control: ReportViewer
documentation: ug
---

# Provide the Data Source credential information in code behind

Use SetDataSourceCredentials to provide the data source credential for the Report Viewer. Use this method in a ReportLoaded event to avoid unexpected issues.

{% highlight C# %}
this.reportViewerControl.ReportLoaded += new ReportLoadedEventHandler (reportViewerControl_ReportLoaded);
void reportViewerControl_ReportLoaded(object sender, EventArgs e)
{
    var dataSources = this.reportViewerControl.GetDataSources();
    List<DataSourceCredentials> credentials=new List<DataSourceCredentials> ();
    foreach (var dataSource in dataSources)
    {
        DataSourceCredentials credential= new DataSourceCredentials ();
        credential.Name = dataSource.Name; // Sets the credential based on the data source.
        credential.UserId = "userName";
        credential.Password = "password";
        credentials.Add (credential);
    }
    this.reportViewerControl.SetDataSourceCredentials (credentials);
}
{% endhighlight %}