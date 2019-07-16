---
layout: post
title: Add DataSource | ReportDesigner | wpf | Syncfusion
description: add datasource
platform: wpf
control: Report Designer
documentation: ug
---

# Add DataSource

This feature allows you to add a DataSource to the Report Designer. It binds the database from the server. The following steps are used to add the DataSource to the Report Designer.

1. In the Report Data, Click New, and then click the DataSource.

   ![WPF ReportDesigner displays add new data source](Add-DataSource_images/Add-DataSource_img1.png)

2. Right click on the Data Sources field and then click on Add Data Source.
   
   ![WPF ReportDesigner displays add new data source field](Add-DataSource_images/Add-DataSource_img2.png)

3. Enter the DataSource name in the Name field and choose use a embedded connection radio button and select the connection type from the Select connection type drop-down.

   ![WPF ReportDesigner displays Data Source Properties window](Add-DataSource_images/Add-DataSource_img3.png)

4. Click Build, then connection properties Wizard opens

5. Enter the server name in the Server name field. 

6. In log on to server column select use windows authentication, then select or enter a database name in the Select or enter a database name drop-down ComboBox in connect to a database column.

   ![WPF ReportDesigner displays select database name and server in Connection Properties window](Add-DataSource_images/Add-DataSource_img4.png)
   
7. Click the Test Connection to check the server connection.

8. The Test Results dialog box is displayed after completing the connection check.

   ![WPF ReportDesigner displays the test result](Add-DataSource_images/Add-DataSource_img5.png)

9. Click OK. It provides a connection string for the DataSource. 

    ![WPF ReportDesigner displays add connection string for data source](Add-DataSource_images/Add-DataSource_img6.png)

10. Click OK. The added DataSource (Adventure) appears in the Report Data panel.

    ![WPF ReportDesigner displays added data source in report data panel](Add-DataSource_images/Add-DataSource_img7.png)