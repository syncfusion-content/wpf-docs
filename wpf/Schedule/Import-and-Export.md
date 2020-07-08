---
layout: post
title: Import and Export| SfSchedule | Wpf | Syncfusion
description: This section explains how to import and export of Syncfusion WPF Scheduler control and more details. 
platform: wpf
control: SfSchedule
documentation: ug
---

# Import and Export of WPF SfSchedule

The schedule control allows users to export or import appointments and events as an .ics files. Appointments and events scheduled with the control can be exported as an .ics file and opened or imported in other schedulers such as Microsoft Outlook, Google Calendar, or any other scheduler supporting .ics files. 

Similarly, files exported from other schedulers can also be imported into Essential Schedule. The code given below demonstrates how to import and export .ics files.

## Exporting in the schedule control 
{% highlight c# %}




Schedule.ExportICS();


{% endhighlight  %}


When the export function is called, a dialog box opens for selecting the location where the file has to be exported.

The exported .ics file will be saved in specified location. These exported files can then be imported in any other scheduler, such as Microsoft Outlook. Similarly, you can import .ics files from other schedulers.



![ImportandExportimg1](Import-and-Export_images/Import-and-Export_img1.png)



## Importing in the schedule control 


{% highlight c# %}




Schedule.ImportICS();



{% endhighlight  %}

If the imported calendar has already been given a name, it can be imported into the schedule control by using the method ImportICS, which will open a dialog for browsing to the location, as seen below.



![ImportandExportimg2](Import-and-Export_images/Import-and-Export_img2.png)



