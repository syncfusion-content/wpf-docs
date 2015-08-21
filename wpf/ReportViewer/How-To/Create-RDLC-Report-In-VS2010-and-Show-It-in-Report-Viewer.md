---
layout: post
title: Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer
description: create rdlc report in vs2010 and show it in report viewer
platform: wpf
control: Report Viewer
documentation: ug
---

### Create RDLC Report In VS2010 and Show It in Report Viewer

This section covers the steps to create RDLC report in VS2010 and shows the created RDLC report in the Report viewer.

1. Create a new WPF application with .Net Framework 4. The Solution Explorer dialog opens.
> Note: In the following example, the new WPF application is created in the name of ReportsApplication8.


2. To add a new RDLC report in the WPF application, right-click on the newly added WPF application in the Solution Explorer dialog.



![Description: sshot-1.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img1.png)



3. Select Add, and then click New Item. The Add New Item dialog opens.
4. To create a dataset for the RDLC report, click Reporting under Visual C# Items.
5. Click Report, and then click Add. 
6. The Report Wizard opens.



![Description: C:/Users/lingarajs/AppData/Local/Microsoft/Windows/Temporary Internet Files/Content.Outlook/EV1EZW4I/reportA (2).png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img2.png)





![Description: sshot-2.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img3.png)



1. Enter a dataset name in Name field.To choose a data source for the dataset, click New on the right of Data source drop-down combo box. The Data Source Configuration Wizard opens.



  ![Description: sshot-3.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img4.png)



2. Click Database under Where will the application get data from? and then click Next.



  ![Description: sshot-4.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img5.png)



3. Click Entity Data Model under What type of database model do you want to use?
4. Click Next. The Entity Data Model Wizard opens.



  ![Description: sshot-5.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img6.png)



5. Click Generate from database under what should the model contain? 
6. Click Next.



![Description: sshot-6.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img7.png)



7. Select a data connection from Which data connection should your application use to connect to the database? drop-down combo box.



> Note: You can create a new data connection by clicking New Connection.



8. Click Next.



  ![Description: sshot-7.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img8.png)



9. Select the required object and click Next. The Data Source Configuration Wizard opens.

  ![Description: sshot-8.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img9.png)



10. Select Object under Where will the application get data from? 
11. Click Next.



  ![Description: sshot-9.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img10.png)



12. Select the object under What objects do you want to bind to? 
13. Click Finish. The Report Wizard shows the details of the dataset under Fields.



  ![Description: sshot-10.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img11.png)



14. Click Next.



> Note: The fields are added under the dataset in Data Sources window.


  ![Description: sshot-add.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img12.png)



15. On Toolbox window, in Report Items, select Table.



  ![Description: sshot-11.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img13.png)



16. Draw a table on the WPF Designer window.



  ![Description: sshot-1.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img14.png)





17. Drag the dataset field on the Table.



  ![Description: sshot-12.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img15.png)





18. To add Report Viewer in the WPF application, select ReportViewer under Reporting.



  ![Description: sshot-13.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img16.png)



> Note: The following window is shown in the WPF Designer window.


  ![Description: sshot-14.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img17.png)



19. Set the ReportPath and the ProcessingMode as local in the Report Viewer.

{% highlight xml %}

<Window x:Class="WpfApplication15.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        Title="MainWindow" Height="350" Width="525" xmlns:syncfusion="http://schemas.syncfusion.com/wpf">

    <Grid >

        <syncfusion:ReportViewer Name="reportViewer1" ProcessingMode="Local" ReportPath="..\..\SampleReport.rdlc" />

    </Grid>

</Window>

{% endhighlight %}

20. Set the DataSource information in the code to view the report in the Report Viewer.


{% highlight C# %}

public MainWindow()

{

    InitializeComponent();

    this.Loaded += new RoutedEventHandler(MainWindow_Loaded);

}



void MainWindow_Loaded(object sender, RoutedEventArgs e)

{

    this.reportViewer1.DataSources.Clear();

    this.reportViewer1.DataSources.Add(new Syncfusion.Windows.Reports.ReportDataSource()

    {

                Name = "DataSet1",

                Value = new AdventureWorksEntities().Addresses.Take(100)

   });

    this.reportViewer1.RefreshReport();

}

{% endhighlight %}

21. Run the application. The following output is displayed.



  ![Description: sshot-15.png](Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_images/Create-RDLC-Report-In-VS2010-and-Show-It-in-Report-Viewer_img18.png)



