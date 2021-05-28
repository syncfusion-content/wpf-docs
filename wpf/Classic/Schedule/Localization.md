---
layout: post
title: Loclization in WPF SfSchedule Control | Syncfusion
description: Learn here all about Loclization support in Syncfusion WPF Schedule (Classic) control, its elements and more details.
platform: wpf
control: SfSchedule
 documentation: ug
---

# Localization in WPF Schedule (Classic)

Localization is the process of customizing the user interface based on a culture specific to a particular country or region in order to display regional data. The culture is represented by a unique string, for example, ―en-US‖ for U.S. English and ―fr‖ for French (common).

Localization is the key feature that provides solutions to global customers with the help of localized resource files provided by the control. The Scheduler supports localization, and you can create a resource file for any culture to be applied in the schedule.

## Set Current UI Culture to the Application
Application culture can be changed by setting [CurrentUICulture](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.currentuiculture.aspx)

{% tabs %}
{% highlight c# %}

public MainWindow()
{
    this.InitializeComponent();
    //Download resx files from GitHub. https://github.com/syncfusion/wpf-demos/tree/master/Schedule/Localization/CS/Resources
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr-FR");
    System.Threading.Thread.CurrentThread.CurrentCulture = new CultureInfo("fr-FR");
}

{% endhighlight  %}
{% endtabs %}

## Localization using Resource file

To localize the Scheduler based on `CurrentUICulture` using resource files, follow the below steps. 

1.Create new folder and named as **Resources** in your application. 
2.Add the default resource file of Scheduler into **Resources** folder. You can download the Syncfusion.SfSchedule.WPF.resx [here](https://github.com/syncfusion/wpf-demos/blob/master/Schedule/Localization/CS/Resources/Syncfusion.SfSchedule.WPF.resx).

![Addition of default resource file of WPF Scheduler into Resources folder](Localization_images/Localization_img1.png)

3.Right-click on the Resources folder, select **Add** and then **NewItem**.

4.In `Add New Item` wizard, select the **Resource File** option and name the filename as **Syncfusion.SfSchedule.WPF.&lt;culture name&gt;.resx**. For example, you have to give name as **Syncfusion.SfSchedule.WPF.de.resx** for German culture.
 
5.The culture name that indicates the name of language and country. 

![Shows the name of resource file to be added for WPF Scheduler](Localization_images/Localization_img2.png)

6.Now, select `Add` option to add the resource file in **Resources** folder.

![Shows the added resource file for French language in WPF Scheduler](Localization_images/Localization_img3.png)

7.Add the Name/Value pair in Resource Designer of **Syncfusion.SfSchedule.WPF.fr-FR.resx** file and change its corresponding value to corresponding culture. 

![Shows the added resource file name / value pair in the resource designer in WPF Scheduler](Localization_images/Localized-strings.png)

![Shows the localized in French for WPF Scheduler](Localization_images/Localization.png)

You can get the sample from [here](https://github.com/syncfusion/wpf-demos/tree/master/Schedule/Localization/CS)
