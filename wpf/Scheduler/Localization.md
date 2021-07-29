---
layout: post
title: Localization in WPF Scheduler control | Syncfusion
description: Learn here all about Localization support in Syncfusion WPF Scheduler (SfScheduler) control and more.
platform: wpf
control: SfScheduler
documentation: ug
---

# Localization in WPF Scheduler (SfScheduler)

Localization is the process of customizing the user interface, based on a culture specific to a particular country or region in order to display the regional data. The culture is represented by a unique string, for example, ―en-US ‖ for U.S. English and ― fr-FR ‖ for French (common).

Localization is the key feature that provides solutions to global customers with the help of localized resource files provided by the control. The Scheduler supports localization, and creates a resource file for any culture to be applied in the scheduler.

## Set Current UI Culture to the Application
Application culture can be changed by setting [CurrentUICulture](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo.currentuiculture?redirectedfrom=MSDN&view=netcore-3.1#System_Globalization_CultureInfo_CurrentUICulture).

{% tabs %}
{% highlight c# %}

public MainWindow()
{
    this.InitializeComponent();
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr-FR");
}

{% endhighlight  %}
{% endtabs %}

## Localization using Resource file

To localize the Scheduler based on `CurrentUICulture` using resource files, follow the below steps. 

1. Create new folder, named as **Resources** in the application. 

2. Add the default resource file of Scheduler into **Resources** folder. 

N> [View **Syncfusion.SfScheduler.WPF.resx** in GitHub](https://github.com/syncfusion/wpf-controls-localization-resx-files/tree/master/Syncfusion.SfScheduler.WPF)

![Addition of default resource file of WPF Scheduler into Resources folder](Localization_images/Localization_Image1.png)

3. Right-click on the Resources folder, select **Add** and then **NewItem**.

4. In `Add New Item` wizard, select the **Resource File** option and name the filename as **Syncfusion.SfScheduler.WPF.&lt;culture name&gt;.resx**. For example, give the name as **Syncfusion.SfScheduler.WPF.de.resx** for German culture.
 
5. The culture name that indicates the name of language and country. 

![Shows the name of resource file to be added for WPF Scheduler](Localization_images/Localization_Image2.png)

6. Now, select `Add` option to add the resource file in **Resources** folder.

![Shows the added resource file for French language in WPF Scheduler](Localization_images/Localization_Image3.png)

7. Add the Name/Value pair in Resource Designer of **Syncfusion.SfScheduler.WPF.fr-FR.resx** file and change its corresponding value to corresponding culture. 

![Shows the added resource file name / value pair in the resource designer in WPF Scheduler](Localization_images/Localized_String.png)

![Shows the localized strings in French for WPF Scheduler](Localization_images/Localized_Scheduler.png)

N> [View sample in GitHub](https://github.com/SyncfusionExamples/wpf-scheduler-localization). You can refer to our [WPF Scheduler](https://www.syncfusion.com/wpf-controls/scheduler) feature tour page for its groundbreaking feature representations.