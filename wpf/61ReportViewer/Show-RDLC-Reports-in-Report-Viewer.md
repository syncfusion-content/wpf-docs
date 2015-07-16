---
layout: post
title: Show-RDLC-Reports-in-Report-Viewer
description: show rdlc reports in report viewer
platform: wpf
control: Report Viewer
documentation: ug
---

# Show RDLC Reports in Report Viewer

You can show RDLC reports in Report Viewer by using following steps.

1. Initialize the Report Viewer control and set the ReportPath to load the RDLC reports from local machine.



// ReportViewer control initialization

Syncfusion.Windows.Reports.Viewer.ReportViewer reportViewer1 = new Syncfusion.Windows.Reports.Viewer.ReportViewer();



// Set ReportPath to view the Report in ReportViewer.

reportViewer1.ReportPath = @"D:\Company Sales.Rdlc";



// Add ReportViewer in MainWindow grid

this.grid1.Children.Add(reportViewer1);





> _Note: To load the company sales report, you can use following installed sample location._

> _&lt;InstalledLocation&gt;\Syncfusion\Essential Studio\&lt;Version Number&gt;\ Common\Data\ReportTemplate\Company Sales.rdl_



2. Set the ProcessingMode as Local to process a local report in Report Viewer.





// To render the report based on local Data Source

reportViewer1.ProcessingMode = Syncfusion.Windows.Reports.Viewer.ProcessingMode.Local;





3. Set the DataSources to view the report in the Report Viewer.





reportViewer1.DataSources.Clear();

reportViewer1.DataSources.Add(new Syncfusion.Windows.Reports.ReportDataSource { Name = "Sales", Value = new AdventureWorks().GetData() });





> _Note: AdventureWorks().GetData() information can be obtained from following location._ 

> _&lt;Installed Location&gt;\Syncfusion\Essential Studio\&lt;Version Number&gt;\ Reports\WPF\ReportViewer.WPF\Samples\Product Showcase\Company Sales\CS\DataSource.cs_



4. Use RefreshReport method to render the RDLC report in the Report Viewer.





this.Loaded += (sender, arg) =>

{

     // To Render the Report in ReportViewer.

     reportViewer1.RefreshReport();

};



5. Run the application. The following output displays.



{ ![Description: C:/Users/lingarajs/AppData/Local/Syncfusion/EssentialStudio/9.4.0.62/Reports/WPF/ReportViewer.WPF/Samples/Product Showcase/Company Sales/Images/CompanySalesDemo.png](Show-RDLC-Reports-in-Report-Viewer_images/Show-RDLC-Reports-in-Report-Viewer_img1.png) | markdownify }
{:.image }


