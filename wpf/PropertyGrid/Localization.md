---
layout: post
title: Localization in WPF PropertyGrid control | Syncfusion
description: Learn about Localization support in Syncfusion Essential Studio WPF PropertyGrid control, its elements and more details.
platform: wpf
control: PropertyGrid
documentation: ug
---

# Localization in WPF PropertyGrid

Localization is the process of translating the application resources into different language for the specific cultures. You can localize the [PropertyGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.PropertyGrid.html) by adding resource file. Application culture can be changed by setting `CurrentUICulture` after `InitializeComponent` method. 

Below application culture changed to `French`.

{% tabs %}
{% highlight C# %}

public MainWindow()
{
    InitializeComponent();
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr-FR");
}    

{% endhighlight %}
{% endtabs %}

To localize the `PropertyGrid` based on `CurrentUICulture` using resource files, follow the below steps. 

**Step 1:** Create new folder and named as `Resources` in your application. 

**Step 2:** Right-click on the `Resources` folder, select `Add` and then `NewItem`.

**Step 3:** In `Add New Item` wizard, select the `Resource File` option and name the filename as **Syncfusion.PropertyGrid.Wpf.&lt;culture name&gt;.resx**. For example, you have to give name as `Syncfusion.PropertyGrid.Wpf.fr-FR.resx` for `French` culture.

![Adding new resource file in WPF application](Localization_images/Add-resource-file-in-wpf-application.png)

**Step 4:** Now, select `Add` option to add the resource file in `Resources` folder.

![Resource file](Localization_images/Resource-file.png)

**Step 5:** Add the Name/Value pair in Resource Designer of `Syncfusion.PropertyGrid.Wpf.fr-FR.resx` file and change its corresponding value to corresponding culture. 

![Added string property of PropertyGrid which need to localized in resource file](Localization_images/wpf-PropertyGrid-localized-string-properties.png)

The following screenshot shows the localized `PropertyGrid` control.

![WPF PropertyGrid contain localized today and none button text](Localization_images/wpf-PropertyGrid-localization.png)

N> View [Sample](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Localization) in GitHub
