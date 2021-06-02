---
layout: post
title: Can you use SharePoint Integrated Mode in WPF ReportViewer| Syncfusion
description: Can you use sharepoint integrated mode report server reports in Syncfusion WPF ReportViewer control, its elements and more.
platform: wpf
control: ReportViewer
documentation: ug
---

# Can you use SharePoint Integrated Mode in ReportViewer?

Yes, Syncfusion Report Viewer supports viewing and exporting SharePoint Integrated Mode Reporting Service reports. 

{% highlight C# %}
this.reportViewer1.ReportLoaded += (sen, arg) =>
{
    IList < DataSourceCredentials > credentials = new List < DataSourceCredentials > ();
    foreach(var datasource in this.reportViewer1.GetDataSources())
    {
        DataSourceCredentials creden = new DataSourceCredentials();
        creden.Name = datasource.Name;
        creden.UserId = "username";
        creden.Password = "password";
        credentials.Add(creden);
    }
    this.reportViewer1.SetDataSourceCredentials(credentials);
};
this.reportViewer1.ReportPath = @" http://ServerName/testreport.rdl";
this.reportViewer1.ReportServerUrl = @"http: //ServerName/ReportServer";
this.reportViewer1.RefreshReport();
{% endhighlight %}