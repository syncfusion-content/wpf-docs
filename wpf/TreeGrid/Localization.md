---
layout: post
title: Localization in WPF TreeGrid | Syncfusion®
description: Localization in TreeGrid customizes grid content to support multiple languages and regional settings for global usability.
platform: wpf
control: TreeGrid
documentation: ug
---
# Localization in WPF TreeGrid

Localization is the process of translating the application resources into different language for the specific cultures. You can localize the TreeGrid by [adding resource file](https://learn.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2010/aa992030(v=vs.100)). Application culture can be changed by setting `CurrentUICulture` before InitializeComponent method.

Below application culture changed to German.

{% tabs %}
{% highlight c# %}
public MainWindow()
{
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("de");
    InitializeComponent();
}
{% endhighlight %}
{% endtabs %}

## Localize the drag and drop window text in TreeGrid

To localize the TreeGrid, drag and drop window based on CurrentUICulture using resource files, follow the below steps.

1.Create new folder and named as `Resources` in your application. 

2.Add the default resource file of treegrid into `Resources` folder. You can download the Syncfusion.SfGrid.WPF.resx [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfGrid.WPF2020296999.zip).

![Resouce File](Localization_images/wpf-treegrid-resource-file.jpeg)

3.Right-click on the Resources folder, select `Add` and then `NewItem`.

4.In Add New Item wizard, select the `Resource File` option and name the filename as `Syncfusion.SfGrid.WPF.&lt;culture name&gt;.resx`. For example, you have to give name as `Syncfusion.SfGrid.WPF.de.resx` for German culture.

5.The culture name that indicates the name of language and country.

![Creating Resource File](Localization_images/wpf-treegrid-create-resource-file.jpeg)

6.Now, select Add option to add the resource file in `Resources` folder.

![Adding Created Resource File as Resource](Localization_images/wpf-treegrid-add-resource-file.jpeg)

7.Add the Name/Value pair in Resource Designer of `Syncfusion.SfGrid.WPF.de.resx` file and change its corresponding value to corresponding culture.

![Changing Resource Dile as per Culture](Localization_images/wpf-treegrid-culture.jpeg)

![displays Drag and Drop Window with Localized Text](Localization_images/wpf-treegrid-drag-and-drop.jpeg)

You can download the sample [here](https://github.com/SyncfusionExamples/how-to-localize-the-drag-and-drop-window-text-in-treegrid/tree/master/WPF).

## Localize when the resource file is present in different assembly or different namespace

By default, the treegrid try to read the resource file from executing assembly and its default namespace by using [Assembly.GetExecuteAssembly](https://learn.microsoft.com/en-us/dotnet/api/system.reflection.assembly.getexecutingassembly?redirectedfrom=MSDN&view=net-5.0#System_Reflection_Assembly_GetExecutingAssembly) method. When the resource file is located at different assembly or namespace, then you can let treegrid know by using [GridResourceWrapper.SetResources](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridResourceWrapper.html#Syncfusion_UI_Xaml_Grid_GridResourceWrapper_SetResources_System_Reflection_Assembly_) method.

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

## Edit default culture resource 

You can edit default resource file by adding it to `Resources` folder of your application where treegrid reads the static texts from here. You can download the default resource file from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfGrid.WPF-804035924.zip).

![Resource File](Localization_images/wpf-treegrid-edit-resource-file.jpeg)

Now, change the Name/Value pair in Resource Designer of `Syncfusion.SfGrid.WPF.resx` file.

![Changing Default Resource File](Localization_images/wpf-treegrid-change-default-resource-file.jpeg)

![Modified Resource File](Localization_images/wpf-treegrid-modified-resource-file.jpeg)

N> You can refer to our [WPF TreeGrid](https://www.syncfusion.com/wpf-controls/treegrid) feature tour page for its groundbreaking feature representations. You can also explore our [WPF TreeGrid example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the control.