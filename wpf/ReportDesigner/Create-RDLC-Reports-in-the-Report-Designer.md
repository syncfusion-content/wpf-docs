---
layout: post
title: Create-RDLC-Reports-in-the-Report-Designer
description: create rdlc reports in the report designer
platform: wpf
control: Report Designer
documentation: ug
---

# Create RDLC Reports in the Report Designer

The RDLC reports can be created by using the ReportDesigner control and an available list of business objects. The following steps demonstrate how to view an RDLC report in the Report Designer.

1. Create a new WPF application in the Visual Studio and add the necessary ReportDesigner references to the application.
2. Set the following properties to design the RDLC report.



this.ReportDesignerControl.DesignMode = Syncfusion.Windows.Reports.Designer.DesignMode.RDLC;

this.ReportDesignerControl.Assemblies = new List<Assembly>();            this.ReportDesignerControl.Assemblies.Add(Assembly.GetExecutingAssembly());



3. Here is a code sample of available business objects with their executing assemblies.



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



4. Right click the Dataset folder to add a data set to the report. 



{{ '![C:/Users/arshiazeba/AppData/Local/Microsoft/Windows/Temporary Internet Files/Content.Word/Fig86.png](Create-RDLC-Reports-in-the-Report-Designer_images/Create-RDLC-Reports-in-the-Report-Designer_img1.png)' | markdownify }}
{:.image }


5. Select a namespace that contains the business object.



{{ '![C:/Users/anandakumars/Desktop/1.PNG](Create-RDLC-Reports-in-the-Report-Designer_images/Create-RDLC-Reports-in-the-Report-Designer_img2.png)' | markdownify }}
{:.image }


6. Select a business object type to design the report by using fields.



{{ '![C:/Users/anandakumars/Desktop/2.PNG](Create-RDLC-Reports-in-the-Report-Designer_images/Create-RDLC-Reports-in-the-Report-Designer_img3.png)' | markdownify }}
{:.image }


7. Drag and drop the fields from the data set in the necessary report items.
8. Click Run to preview the report in the designer. You have to provide a DataSet value to preview the report.
9. Select the collection of business objects by selecitng the necessary method in the provided assembly.

{{ '![C:/Users/anandakumars/Desktop/FRImages/21.png](Create-RDLC-Reports-in-the-Report-Designer_images/Create-RDLC-Reports-in-the-Report-Designer_img4.png)' | markdownify }}
{:.image }


10. The output is displayed as shown in the following figure.



{{ '![C:/Users/anandakumars/Desktop/3.PNG](Create-RDLC-Reports-in-the-Report-Designer_images/Create-RDLC-Reports-in-the-Report-Designer_img5.png)' | markdownify }}
{:.image }


