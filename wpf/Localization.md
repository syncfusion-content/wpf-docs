---
layout: post
title: Steps to localize the Syncfusion Essential WPF controls
description: common supports
platform: wpf
control: Localization
documentation: ug
---

# Getting Started for Localization

Localization is the process of making your application multi-lingual, by formatting the content according to cultures. This involves configuring the application for a specific language. Culture is the combination of language and location, for example `en-US` is the culture for English spoken in United States; `en-GB` is the culture for English spoken in Great Britain. 

Syncfusion controls allows you to set custom resource through the Resx file with standard filename as [AssemblyName].[CultureInfo Code].resx, for example Syncfusion.Tools.wpf.fr-FR.resx, Syncfusion.SfSchedule.wpf.fr-FR.resx. And by giving the string values in the resource file for a specific culture and set the culture in the application. The string values should be set to the controls respective resource key.

The following are the steps to localize a control:

1. Add Resources file for the different cultures.
2. Assign the value to each culture using key
3. Assign a Current UI Culture to the application.

## Assign the value to each culture by using key


To localize WPF controls, the resource file needs to be created as per following steps:

1. Create a folder named "Resources" in the application.
2. Open the "Add New Item" Dialog using Ctrl+Shift+A keys.
3. Create a resource file, Resx file, and name it Syncfusion.Tools.Wpf.resx For example, Syncfusion.Tools.Wpf.fr-FR.resx

![](Localization_images/GettingStarted_img1.jpeg)


N> In case, the Shared dll controls is used in the application, then create another resource file in name Syncfusion.Shared.Wpf.resx For example, Syncfusion.Shared.Wpf.fr-FR.resx and the naming convention needs to be followed mandatorily.

## How to assign UI Culture to the application

To assign "Values" in Resource, the resource file needs to be updated according to the following steps.

1.Open the required file by double clicking it from Solutions Explorer.
2.Add the key, Name, and its corresponding localized value by editing its field as shown in the following image.

![](Localization_images/GettingStarted_img2.jpeg)


3.Similarly add all the keys, Name, needed for the required assembly. For example (Syncfusion.Tools.Wpf.dll). The following screenshot displays the String property names for Tools.WPF controls with French values.

![](Localization_images/GettingStarted_img3.jpeg)


N> The default resource file for applicable assemblies can be downloaded from the table provided at the end.

## Assign a Current UI culture to the application

Mention the culture to be referred while initializing the application, so that you can refer to the appropriate value provided in resource file.

{% tabs %}

{%highlight C#%}

public partial class MainWindow
{
public MainWindow() 
{     
	InitializeComponent();  
   	System.Threading.Thread.CurrentThread.CurrentUICulture = newSystem.Globalization.CultureInfo("fr-FR");   
}
} 
 
{%endhighlight%}

{% highlight VB %}

Partial Public Class MainWindow
Public Sub New()
	InitializeComponent()
	   System.Threading.Thread.CurrentThread.CurrentUICulture = newSystem.Globalization.CultureInfo("fr-FR")
End Sub
End Class

{%endhighlight%}

{% endtabs %}