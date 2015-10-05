---
layout: post
title: Create RDLC Reports in the Report Designer | ReportDesigner | wpf | Syncfusion
description: create rdlc reports in the report designer
platform: wpf
control: Report Designer
documentation: ug
---

# Create RDLC Reports in the Report Designer

The RDLC reports can be created by using the ReportDesigner control and an available list of business objects. The following steps demonstrate how to view an RDLC report in the Report Designer.

1.Create a new WPF application in the Visual Studio and add the necessary ReportDesigner references to the application.

2.Set the following properties to design the RDLC report.

{% highlight C# %}

this.ReportDesignerControl.DesignMode = Syncfusion.Windows.Reports.Designer.DesignMode.RDLC;

this.ReportDesignerControl.Assemblies = new List<Assembly>();            this.ReportDesignerControl.Assemblies.Add(Assembly.GetExecutingAssembly());

{% endhighlight %}

3.Here is a code sample of available business objects with their executing assemblies.

{% highlight C# %}

public class DataSource

{        

        public List<Device> deviceLists = new List<Device>();     

        public  List<Device> GetDataSource()

        {

            deviceLists.Add(new Device("Fax", "Microsoft Shared Fax Driver"));

            deviceLists.Add(new Device("Printer", "Brother MFC-7360 Printer"));

            deviceLists.Add(new Device("Printer", "Microsoft XPS Document Writer"));

            deviceLists.Add(new Device("Printer", "Send To Microsoft OneNote 2010 Driver"));



            return deviceLists;

        }

    }

    public class Device

    {

        public Device(string _category, string _deviceName)

        {

            this.Category = _category;

            this.DeviceName = _deviceName;

        }

        public string DeviceName { get; set; }

        public string Category { get; set; }

    }

{% endhighlight %}

4.Right click the Dataset folder to add a data set to the report. 



   ![](Create-RDLC-Reports-in-the-Report-Designer_images/Create-RDLC-Reports-in-the-Report-Designer_img1.png)



5.Select a namespace that contains the business object.



  ![](Create-RDLC-Reports-in-the-Report-Designer_images/Create-RDLC-Reports-in-the-Report-Designer_img2.png)



6.Select a business object type to design the report by using fields.



  ![](Create-RDLC-Reports-in-the-Report-Designer_images/Create-RDLC-Reports-in-the-Report-Designer_img3.png)



7.Drag and drop the fields from the data set in the necessary report items.

8.Click Run to preview the report in the designer. You have to provide a DataSet value to preview the report.

9.Select the collection of business objects by selecitng the necessary method in the provided assembly.

  ![](Create-RDLC-Reports-in-the-Report-Designer_images/Create-RDLC-Reports-in-the-Report-Designer_img4.png)



10.The output is displayed as shown in the following figure.



  ![](Create-RDLC-Reports-in-the-Report-Designer_images/Create-RDLC-Reports-in-the-Report-Designer_img5.png)



