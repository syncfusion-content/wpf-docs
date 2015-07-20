---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: Report Viewer
documentation: ug
---

# Getting Started

## Create Report Viewer through Designer

The section illustrates how to add the Report Viewer to the WPF application. It includes the following steps:

1. Create a new WPF application in VS2008 or VS2010.



{ ![](Getting-Started_images/Getting-Started_img1.png) | markdownify }
{:.image }




2. To add the Report Viewer control through designer, drag the Report Viewer control from Toolbox to Report Viewer window. The Report Viewer window is modified as shown.



{ ![Description: 3.png](Getting-Started_images/Getting-Started_img2.png) | markdownify }
{:.image }


> _Note: The following code is auto generated in XAML window._

> 

<Window x:Class="WpfApplication6.Window1"    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

    Title="Window1" Height="371" Width="559" xmlns:syncfusion="http://schemas.syncfusion.com/wpf">

    &lt;Grid&gt;

        &lt;syncfusion:ReportViewer Name="reportViewer1" /&gt;

    &lt;/Grid&gt;

&lt;/Window&gt; 



3. Set the ReportPath to load the report in Report Viewer from a local machine.
                        1. <Window x:Class="WpfApplication6.Window1"    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                        2.     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                        3.     Title="Window1" Height="371" Width="559" xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
                        4.     &lt;Grid&gt;
                        5.         &lt;syncfusion:ReportViewer Name="reportViewer1" ReportPath="D:\ReportTemplate\Invoice.rdl"/&gt;
                        6.     &lt;/Grid&gt;

&lt;/Window&gt; 



4. To render the provided report in Report Viewer, call the RefreshReport method in window or parent control loaded event.

this.Loaded += (sender, arg) =>

                {

                      // To Render the Report in ReportViewer.

                    this.reportViewer1.RefreshReport();

                };



5. Run the application. The following output displays.

{ ![Description: C:/Users/lingarajs/AppData/Local/Syncfusion/EssentialStudio/9.4.0.62/Reports/WPF/ReportViewer.WPF/Samples/Product Showcase/Invoice/Images/InvoiceDemo.png](Getting-Started_images/Getting-Started_img3.png) | markdownify }
{:.image }


6. Click export drop-down button in Report Viewer toolbar and select PDF or XPS as needed. The report is exported into PDF or XPS formats, respectively.



{ ![Description: sa.png](Getting-Started_images/Getting-Started_img4.png) | markdownify }
{:.image }


The following output is the exported PDF report.

> 

{ ![Description: C:/Users/lingarajs/AppData/Local/Syncfusion/EssentialStudio/9.4.0.62/Reports/WPF/ReportWriter.WPF/Samples/Product Showcase/Invoice/Images/Invoice.png](Getting-Started_images/Getting-Started_img5.png) | markdownify }
{:.image }


