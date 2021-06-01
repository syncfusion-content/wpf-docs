---
layout: post
title: Can you use SharePoint Integrated Mode Report Server reports in ReportViewer | ReportViewer | WPF | Syncfusion
description: can you use sharepoint integrated mode report server reports in reportviewer?
platform: wpf
control: ReportViewer
 documentation: ug
---

# Can you use SharePoint Integrated Mode Report Server reports in ReportViewer?

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