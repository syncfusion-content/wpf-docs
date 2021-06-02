---
layout: post
title: SSRS shared embedded datasource in WPF ReportViewer | Syncfusion
description: Why do you have to provide ssrs shared/embedded data source credential information in code behind for Syncfusion WPF ReportViewer control, its elements and more.
platform: wpf
control: ReportViewer
documentation: ug
---

# SSRS shared/embedded datasource credential information in ReportViewer

RDL reports have limitations for retrieving a password from the SQL Reporting Service (SSRS) for security reasons. Therefore, the credential information is provided when the data source credential is saved in the Reporting Server for shared or embedded data sources. 

The following code provides SSRS shared/embedded data source credential information.

{% highlight C# %}
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