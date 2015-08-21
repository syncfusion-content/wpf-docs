---
layout: post
title: Common-Supports
description: common supports
platform: wpf
control: Introduction
documentation: ug
---

# Common Supports

## Expression Blend

Most of the Syncfusion controls are enhanced with blend support. The following steps allow the control to design in Visual Studio Expression Blend.

1. Create a WPF project in Expression Blend and refer to the Syncfusion corresponding control’s assemblies. For example, to add Docking Manager control, add its assembly Syncfusion.Tools.Wpf and its dependency assembly Syncfusion.Shared.Wpf
  
   
   ![C:/Users/labuser/Desktop/blend_images/docking-1_edited.png](Common-Supports_images/Common-Supports_img1.png)

  

2. Search for Control in the Toolbox.

  
   ![C:/Users/labuser/Desktop/blend_images/docking_2_Edited.png](Common-Supports_images/Common-Supports_img2.png)

  

3. Drag the control to the designer. It generates the control in designer.
   

   ![C:/Users/labuser/Desktop/blend_images/Docking-3.png](Common-Supports_images/Common-Supports_img3.png)

  
   {:.prettyprint}

## Testing

The following Syncfusion controls come with built in testing support like [Coded UI](https://msdn.microsoft.com/en-us/magazine/hh875174.aspx) and QTP that enables you to develop enriched automation Test Project for automation to ensure the reliability.

### Coded UI

* CellGrid
* DataGrid
* TreeGrid
* GridDataControl
* Ribbon
* DockingManager



### QTP

* CellGrid
* DataGrid
* TreeGrid
* GridDataControl



## Localization

Localization is the process of making your application multi-lingual, by formatting the content according to cultures. This involves configuring the application for a specific language. Culture is the combination of language and location, for example En-US is the culture for English spoken in United States; En-GB is the culture for English spoken in Great Britain. Syncfusion controls allow you to set custom resource through the Resx file with standard filename as [AssemblyName].[CultureInfo Code].resx, for example Syncfusion.Tools.wpf.fr-FR.resx, Syncfusion.SfSchedule.wpf.fr-FR.resx. And by giving the string values in the resource file for a specific culture and set the culture in the application. The string values should be set to the controls respective resource key.

### The followings are the step to localize a control:

* Add Resources file for the different cultures.
* Assign the value to each culture using key
* Assign a Current UI Culture to the application.

How to Add a Resource file, like Syncfusion.Tools.Wpf.dll Assembly?

To localize WPF controls, the resource file needs to be created as per following steps:

1. Create a folder named Resources in the application. 
2. Open the Add New Item Dialog using Ctrl+Shift+A keys
3. Create a resource file, Resx file, and name it Syncfusion.Tools.Wpf<culture info name>.resx For example, Syncfusion.Tools.Wpf.fr-FR.resx.



![](Common-Supports_images/Common-Supports_img4.png)





> Note: In case, the Shared dll controls is used in the application, then create another resource file in name Syncfusion.Shared.Wpf<your culture info name>.resx For example, Syncfusion.Shared.Wpf.fr-FR.resx and the naming convention needs to be followed mandatorily.



The following screenshot explains the addition of a Resource file to the application.

![](Common-Supports_images/Common-Supports_img5.png)



How to assign values in Resources file?

To assign Values in Resource, the resource file need to be updated as per the following steps.

1. Open the required file by double clicking it from Solution Explorer. 
2. Add key (Name) and its corresponding localized value by editing its field as shown in the following image.



   ![](Common-Supports_images/Common-Supports_img6.png)



3. Similarly add all need key (Name) for required assembly for example (Syncfusion.Tools.Wpf.dll). And the following screenshot displays the String property names for Tools.WPF controls with French values.

   ![http://help.syncfusion.com/ug/wpf/ImagesExt/image252_12.jpg](Common-Supports_images/Common-Supports_img7.jpeg)

   {:.prettyprint}



> Note: The default resource file for applicable assemblies can be downloaded by table provided at the end of this page.



How to assign UI Culture to the application?

Mention the culture to be referred while initializing the application, so that you can refer to the appropriate value provided in resource file. The following code illustrates the implementation of culture information settings.
{% highlight c# %}
public MainWindow()

 {

    InitializeComponent();



    System.Threading.Thread.CurrentThread.CurrentUICulture = newSystem.Globalization.CultureInfo("fr-FR");



  }
{% endhighlight  %}
### Localization Resource file

Following table represents available Resource file to the Assemblies and it can be downloaded.

_Properties_

<table>
<tr>
<th>
Assembly</th><th>
Resource file (.resx)</th></tr>
<tr>
<td>
Syncfusion.Tools.wpf.dll</td><td>
{{ '[Syncfusion.Tools.Wpf.resx](https://syncfusion.atlassian.net/secure/attachment/197843/Syncfusion.Tools.Wpf.resx)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.Shared.wpf.dll</td><td>
{{ '[Syncfusion.Shared.Wpf.resx](https://syncfusion.atlassian.net/secure/attachment/197842/Syncfusion.Shared.Wpf.resx)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.ReportViewer.wpf.dll.</td><td>
{{ '[Syncfusion.ReportViewer.Wpf.resx](https://syncfusion.atlassian.net/wiki/download/attachments/48955541/Syncfusion.ReportViewer.Wpf.resx?version=1&modificationDate=1429777829642&api=v2)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.ReportDesigner.wpf.dll</td><td>
{{ '[Syncfusion.ReportDesigner.Wpf.resx](https://syncfusion.atlassian.net/wiki/download/attachments/48955541/Syncfusion.ReportDesigner.Wpf.resx?version=1&modificationDate=1429778208537&api=v2)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.SfSchedule.WPF.dll</td><td>
{{ '[Syncfusion.Schedule.WPF.resx](https://syncfusion.atlassian.net/secure/attachment/198894/Syncfusion.Schedule.WPF.resx)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.Diagram.wpf.dll</td><td>
{{ '[Syncfusion.Diagram.Wpf.resx](https://syncfusion.atlassian.net/secure/attachment/198885/Syncfusion.Diagram.Wpf.resx)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.OlapChart.WPF.dll</td><td>
{{ '[Syncfusion.OlapChart.WPF.resx](https://syncfusion.atlassian.net/wiki/download/attachments/48955541/Syncfusion.OlapChart.WPF.resx?version=1&modificationDate=1429782554725&api=v2)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.OlapGrid.WPF.dll</td><td>
{{ '[Syncfusion.OlapGrid.WPF.resx](https://syncfusion.atlassian.net/wiki/download/attachments/48955541/Syncfusion.OlapGrid.WPF.resx?version=1&modificationDate=1429782601212&api=v2)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.OlapClient.WPF.dll</td><td>
{{ '[Syncfusion.OlapClient.WPF.resx](https://syncfusion.atlassian.net/wiki/download/attachments/48955541/Syncfusion.OlapClient.WPF.resx?version=1&modificationDate=1429782644966&api=v2)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.OlapGauge.WPF.dll</td><td>
{{ '[Syncfusion.OlapGauge.wpf.resx](https://syncfusion.atlassian.net/wiki/download/attachments/48955541/Syncfusion.OlapGauge.wpf.resx?version=1&modificationDate=1429782671861&api=v2)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.OlapShared.WPF.dll</td><td>
{{ '[Syncfusion.OlapShared.WPF.resx](https://syncfusion.atlassian.net/wiki/download/attachments/48955541/Syncfusion.OlapShared.WPF.resx?version=1&modificationDate=1429782739175&api=v2)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.OlapTools.WPF.dll</td><td>
{{ '[Syncfusion.OlapTools.WPF.resx](https://syncfusion.atlassian.net/wiki/download/attachments/48955541/Syncfusion.OlapTools.WPF.resx?version=1&modificationDate=1429782790451&api=v2)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.PivotAnalysis.WPF.dll</td><td>
{{ '[Syncfusion.PivotAnalysis.Wpf.resx](https://syncfusion.atlassian.net/wiki/download/attachments/48955541/Syncfusion.PivotAnalysis.Wpf.resx?version=1&modificationDate=1429782815969&api=v2)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.SfGrid.WPF.dll</td><td>
{{ '[Syncfusion.SfGrid.WPF.resx](https://syncfusion.atlassian.net/secure/attachment/198980/Syncfusion.SfGrid.WPF.resx)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.Spreadsheet.Wpf.dll</td><td>
{{ '[Syncfusion.Speradsheet.Wpf.resx](https://syncfusion.atlassian.net/wiki/download/attachments/48955541/Syncfusion.Speradsheet.Wpf.resx?version=1&modificationDate=1429786635340&api=v2)' | markdownify }}</td></tr>
<tr>
<td>
Syncfusion.Grid.WPF.dll</td><td>
{{ '[Syncfusion.Grid.Wpf.resx](https://syncfusion.atlassian.net/secure/attachment/199075/Syncfusion.Grid.Wpf.resx)' | markdownify }}</td></tr>
</table>


