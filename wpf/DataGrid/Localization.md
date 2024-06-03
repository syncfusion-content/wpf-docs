---
layout: post
title: Localization in WPF DataGrid control | Syncfusion
description: Learn here all about Localization support in Syncfusion WPF DataGrid (SfDataGrid) control, its elements and more details.
platform: wpf
control: SfDataGrid
documentation: ug
---


# Localization in WPF DataGrid (SfDataGrid)

Localization is the process of translating the application resources into different language for the specific cultures. You can localize the SfDataGrid by adding [resource](https://learn.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2010/aa992030(v=vs.100)?redirectedfrom=MSDN) file. Application culture can be changed by setting [CurrentUICulture](https://learn.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo.currentuiculture?view=net-7.0&redirectedfrom=MSDN#System_Globalization_CultureInfo_CurrentUICulture) before `InitializeComponent()` method. 

Below application culture changed to German.

{% tabs %}
{% highlight c# %}
public MainWindow()
{
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("de-DE");

    InitializeComponent();
}    
{% endhighlight %}
{% endtabs %}


To localize the SfDataGrid based on `CurrentUICulture` using resource files, follow the below steps. 

1.Create new folder and named as **Resources** in your application. 
2.Add the default resource file of SfDataGrid into **Resources** folder. You can download the Syncfusion.SfGrid.WPF.resx [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfGrid.WPF71700028.zip).

![Displaying Default Resource File of WPF DataGrid into Resources Folder](Localization_images/wpf-datagrid-default-resource-file.png)

3.Right-click on the Resources folder, select **Add** and then **NewItem**.

4.In `Add New Item` wizard, select the **Resource File** option and name the filename as **Syncfusion.SfGrid.WPF.&lt;culture name&gt;.resx**. For example, you have to give name as **Syncfusion.SfGrid.WPF.de.resx** for German culture.
 
5.The culture name that indicates the name of language and country. 

![Changing name of New Resource File for WPF DataGrid](Localization_images/wpf-datagrid-change-resource-file-name.png)

6.Now, select `Add` option to add the resource file in **Resources** folder.

![Displaying Resource File with German Language for WPF DataGrid](Localization_images/wpf-datagrid-with-german-resource-file.png)

7.Add the Name/Value pair in Resource Designer of **Syncfusion.SfGrid.WPF.de.resx** file and change its corresponding value to corresponding culture. 

![Displaying Added Resource File Name and Value pair in WPF DataGrid](Localization_images/wpf-datagrid-resource-file-name-and-value.png)

![Displaying Localized File in German for WPF DataGrid](Localization_images/wpf-datagrid-localized-file.png)

You can get the sample from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Localization1013710435.zip)

## Localize when the resource file present in different assembly or different namespace?

By default, SfDataGrid try to read the resource file from executing assembly and its default namespace by using [Assembly.GetExecuteAssembly](https://learn.microsoft.com/en-us/dotnet/api/system.reflection.assembly.getexecutingassembly?view=net-7.0) method. When the resource file is located at different assembly or namespace, then you can let SfDataGrid know by using [GridResourceWrapper.SetResources](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridResourceWrapper.html#Syncfusion_UI_Xaml_Grid_GridResourceWrapper_SetResources_System_Reflection_Assembly_) method.

{% tabs %}
{% highlight c# %}
public MainWindow()
{
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("de-DE");            
    Syncfusion.UI.Xaml.Grid.GridResourceWrapper.SetResources("Assembly_name", "namespace_name");
    InitializeComponent();
}
{% endhighlight %}
{% endtabs %}


## Editing default culture resource

You can edit default resource file by adding it to **Resources** folder of your application where SfDataGrid reads the static texts from here. You can download the default resource file from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfGrid.WPF71700028.zip).

![Displaying Default Culture Resource File Editing for WPF DataGrid](Localization_images/wpf-datagrid-edit-localized-file.png)

Now, change the Name/Value pair in Resource Designer of **Syncfusion.SfGrid.WPF.resx** file.

![Displaying Name and Value pair in Resource Designer for Default Culture in WPF DataGrid](Localization_images/wpf-datagrid-resource-file-name-and-value.png)


![WPF DataGrid displays Editing Default Culture Resource](Localization_images/wpf-datagrid-edit-default-resource.png)

