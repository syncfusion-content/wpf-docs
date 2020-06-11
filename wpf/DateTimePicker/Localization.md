---
layout: post
title: WPF DateTimeEdit Localization | Syncfusion
description: DateTimeEdit control provides localization support to translate the application resources into different language for the specific cultures.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Localizing WPF DateTimePicker (DateTimeEdit)

Localization is the process of translating the application resources into different language for the specific cultures. You can localize the [DateTimeEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit.html) by [adding resource file](https://msdn.microsoft.com/library/aa992030.aspx). Application culture can be changed by setting [CurrentUICulture](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo.currentuiculture?view=netframework-4.7.2) after `InitializeComponent` method. 

Below application culture changed to French.

{% tabs %}

{% highlight C# %}

public MainWindow()
{
    InitializeComponent();
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr-FR");
}    

{% endhighlight %}

{% endtabs %}

To localize the DateTimeEdit based on [CurrentUICulture](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo.currentuiculture?view=netframework-4.7.2) using resource files, follow the below steps. 

**Step 1:** Create new folder and named as **Resources** in your application. 

**Step 2:** Right-click on the Resources folder, select **Add** and then **NewItem**.

**Step 3:** In `Add New Item` wizard, select the **Resource File** option and name the filename as **Syncfusion.Shared.Wpf.&lt;culture name&gt;.resx**. For example, you have to give name as **Syncfusion.Shared.WPF.fr-FR.resx** for French culture.

![Adding new resource file in WPF application](Localization_images/Add-resource-file-in-wpf-application.png)

**Step 4:** Now, select `Add` option to add the resource file in **Resources** folder.

![Resource file](Localization_images/Resource-file.png)

**Step 5:** Add the Name/Value pair in Resource Designer of **Syncfusion.Shared.Wpf.fr-FR.resx** file and change its corresponding value to corresponding culture. 

![Added string property of DateTimeEdit which need to localized in resource file](Localization_images/wpf-datetimeedit-localized-string-properties.png)

The following screenshot shows the localized DateTimeEdit control.

![WPF DateTimeEdit contain localized today and none button text](Localization_images/wpf-datetimeedit-localization.png)

N> View [Sample](https://github.com/SyncfusionExamples/wpf-date-time-edit-examples/tree/master/Samples/Localization) in GitHub