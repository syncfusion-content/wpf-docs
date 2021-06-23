---
layout: post
title: Localization in WPF Pdf Viewer control | Syncfusion
description: Learn about Localization support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Localization in WPF Pdf Viewer

Localization is the process of configuring the application to a specific language. [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) provides support to localize all the static text used for tooltip and context menu contents. Localization can be done by adding resource file (.resx) in the application.
We are using `en-US` culture-based resource file as default in PDF Viewer, which can be downloaded from this [GitHub](https://github.com/syncfusion/wpf-controls-localization-resx-files/tree/master/Syncfusion.PdfViewer.WPF) location.


## Adding Resource file

* Create a folder names `Resources` in your application.
* Add default English (“en-US”) [Resx](https://github.com/syncfusion/wpf-controls-localization-resx-files/blob/master/Syncfusion.PdfViewer.WPF/Syncfusion.PdfViewer.WPF.resx) (resource) file of `PdfViewerControl` in `Resources` folder named as Syncfusion.PdfViewer.WPF.resx.
* Create a Resx (resource) files and named as Syncfusion.PdfViewer.WPF.[Culture name].resx. For example, Syncfusion.PdfViewer.WPF.fr.resx for French culture. 
* Add the resource key such as `OpenDocument` and its corresponding localized value in Syncfusion.PdfViewer.WPF.fr.resx file. Refer the below screenshot for the same.
* Execute the application in the French culture to see the changes.

![Resource file](Localization_images/Localization_image2.png)

The following screenshot shows the `PdfViewerControl` in French language

![Localization](Localization_images/Localization_image1.png)

## Localize Resource File with Different Assembly or Namespace

In general, [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) try to read the resource file from executing assembly and its default namespace by using [Assembly.GetExecuteAssembly](https://docs.microsoft.com/en-us/dotnet/api/system.reflection.assembly.getexecutingassembly) method. When the resource file is located at different assembly or namespace, then it can be set to the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) by using `LocalizationManager.SetResources` method.

{% tabs %}
{% highlight c# %}
public MainWindow()
{
    Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr-FR");
	
	// Set the Custom assembly and namespace for the localization.
	LocalizationManager.SetResources(typeof(Custom_Class).Assembly, "ClassLibrary");
    InitializeComponent();
}    
{% endhighlight %}
{% endtabs %}
