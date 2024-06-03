---
layout: post
title: Localization in WPF Spreadsheet control | Syncfusion
description: Learn here all about Localization support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Localization in WPF Spreadsheet (SfSpreadsheet)

Localization is the process of configuring the application to a specific language. SfSpreadsheet provides support to localize all the static text in a Ribbon and all dialogs to any desired language. Localization can be done by adding resource file and setting the specific culture in the application.

SfSpreadsheet allows you to set custom resource using Resx file. You can define your string values in resource file for a specific culture and set the culture in your application.

## Set Current UI Culture to the Application

To set the CultureInformation in the Application, set the `CurrentUICulture` before the InitializeComponent() method is called. 

Setting of the culture information,

{% tabs %}
{% highlight c# %}
public MainWindow()
{
    System.Threading.Thread.CurrentThread.CurrentUICulture = new CultureInfo("ja-JP");
    InitializeComponent();
}
{% endhighlight %}
{% endtabs %}

Now, the Application is set to the Japanese Culture info. 

## Localization using Resource file

The following steps show how to implement the localization in SfSpreadsheet,

* Create a folder and name it as ‘Resources’ in your application.
* Add the default resource[English("en-US")] file of `SfSpreadsheet` in the 'Resources' folder named as Syncfusion.SfSpreadsheet.WPF.resx.
  You can download the Resx file [here](https://github.com/syncfusion/wpf-controls-localization-resx-files/blob/master/Syncfusion.SfSpreadsheet.WPF/Syncfusion.SfSpreadsheet.Wpf.resx) 
* Create Resx(resource) file under the 'Resources' folder and name it as Syncfusion.SfSpreadsheet.WPF.[Culture name].resx. 
  For example, Syncfusion.SfSpreadsheet.WPF.ja.resx for Japanese culture. 

![WPF Spreadsheet Localization using Resource File](localization_images/wpf-spreadsheet-localization-using-resource-file.JPG)

* Add the resource key such as name and its corresponding localized value in Resource Designer of Syncfusion.SfSpreadsheet.WPF.ja.resx file.
  For your reference, you can download the Japanese("ja-JP") Resx file [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfSpreadsheet.WPF.ja1723377679)

![WPF Spreadsheet Localization with Resource Key](localization_images/wpf-spreadsheet-localization-with-resource-key.JPG)

The following screenshot shows you the localization in SfSpreadsheet,

![WPF Spreadsheet Localization](localization_images/wpf-spreadsheet-localization.jpg)

## Modifying the localized strings in Resource file

Users can modify the default localized strings in Resource file by adding the default [Resx](https://github.com/syncfusion/wpf-controls-localization-resx-files/blob/master/Syncfusion.SfSpreadsheet.WPF/Syncfusion.SfSpreadsheet.Wpf.resx) (resource) file of `SfSpreadsheet` in the 'Resources' folder of your application and name it as Syncfusion.SfSpreadsheet.WPF.resx.

Now, the default localized strings can be modified by changing the Name/Value pair in the Syncfusion.SfSpreadsheet.WPF.resx file.

![WPF Spreadsheet Localized using Resource String](localization_images/wpf-spreadsheet-localized-using-resource-string.jpg)


N> You can refer to our [WPF Spreadsheet](https://www.syncfusion.com/wpf-controls/spreadsheet) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Spreadsheet example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the spreadsheet.

## Localize when the resource file is present in a different assembly or different namespace

[WPF-Spreadsheet](https://help.syncfusion.com/wpf/spreadsheet/getting-started) (SfSpreadsheet) reads the localization resource files based on the assembly name from its default namespace. If you have the localization resource file other than the executing assembly (Assembly.GetExecutingAssembly())or other than the default namespace, then you have to pass the assembly having the resource file and its default namespace to [GridResourceWrapper.SetResources](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.Resources.GridResourceWrapper.html#Syncfusion_UI_Xaml_Spreadsheet_Resources_GridResourceWrapper_SetResources_System_Reflection_Assembly_System_String_) method.

{% tabs %}
{% highlight c# %}
 public MainWindow()
 {
      System.Threading.Thread.CurrentThread.CurrentUICulture = new CultureInfo("ja");
      Assembly assembly = Assembly.Load("Another assemblyname having resource file");
      Syncfusion.UI.Xaml.Spreadsheet.Resources.GridResourceWrapper.SetResources(assembly, "namespacename");
      InitializeComponent();
 }
{% endhighlight %}
{% endtabs %}
