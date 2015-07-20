---
layout: post
title: Show-RDL-Report-in-Report-Viewer-through-Code
description: show rdl report in report viewer through code
platform: wpf
control: Report Viewer
documentation: ug
---

# Show RDL Report in Report Viewer through Code

You can create a simple sample through code with the Syncfusion WPF ReportViewer control by using the following steps.

1. Create a new WPF application in VS2008/VS2010.
2. To add related references to the created application, right-click on References and select Add Reference.



{{ '![Description: 5.png](Show-RDL-Report-in-Report-Viewer-through-Code_images/Show-RDL-Report-in-Report-Viewer-through-Code_img1.png)' | markdownify }}
{:.image }


> _Note: The added references appeared under References folder._



> 

{{ '![Description: 6.png](Show-RDL-Report-in-Report-Viewer-through-Code_images/Show-RDL-Report-in-Report-Viewer-through-Code_img2.png)' | markdownify }}
{:.image }


3. Set Grid name in auto generated XAML of MainWindow.



<Window x:Class="WpfApplication13.MainWindow"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        Title=" Mail Merge" Height="350" Width="525">

    <Grid Name="grid1">

    </Grid>

</Window>



4. Add Report Viewer in MainWindowgrid.



   // ReportViewer control initialization

Syncfusion.Windows.Reports.Viewer.ReportViewer reportViewer1 = new Syncfusion.Windows.Reports.Viewer.ReportViewer();



// Sets ReportPath to view the Report in ReportViewer.

reportViewer1.ReportPath=@"D:\MailMerge.rdl";



// Adds ReportViewer in MainWindow grid

this.grid1.Children.Add(reportViewer1);



this.Loaded += (sender, arg) =>

{

//Renders the Report in ReportViewer.

reportViewer1.RefreshReport();

};





5. Run the application. The following output is displayed.



{{ '![Description: D:/TrunkReportingStructure/WPF/ReportViewer.WPF/samples/Product Showcase/Mail Merge/Images/mailmerge.png](Show-RDL-Report-in-Report-Viewer-through-Code_images/Show-RDL-Report-in-Report-Viewer-through-Code_img3.png)' | markdownify }}
{:.image }


