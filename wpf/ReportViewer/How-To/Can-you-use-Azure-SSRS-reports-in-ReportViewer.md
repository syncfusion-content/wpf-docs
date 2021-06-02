---
layout: post
title: Can you use Azure SSRS reports in WPF ReportViewer | Syncfusion
description: Can you use azure ssrs reports in Syncfusion Essential Studio WPF ReportViewer control, its elements, and more.
platform: wpf
control: ReportViewer
documentation: ug
---

# Can you use Azure SSRS reports in ReportViewer?

Yes, Syncfusion Report Viewer supports viewing and exporting Azure hosted reports.  By default, Azure Reporting Service works with a Forms credential. So, provide your Forms credential in the ReportServerFormsCredential to view the report.

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
this.reportViewer1.ReportPath = " / AzureReportProject / Reports";
this.reportViewer1.ReportServerUrl = @"http://ServerName/ReportServer";
this.reportViewer1.ReportServerFormsCredential = new System.Net.NetworkCredential("userID", "Password");
this.reportViewer1.RefreshReport();
{% endhighlight %}