---
layout: post
title: RTL Support| OlapGrid | Wpf | Syncfusion
description: rtl support
platform: wpf
control: OlapGrid
documentation: ug
---

# Localization

Localization is the key feature for providing IT solutions targeted at global users. OlapGrid allows user to localize the control to a specific locale. OlapGrid supports "resx" based localization.

The following steps need to be performed, in order to localize the control.

* Translation
* Resource File and File name conventions
* Tag inclusion into the project file
* Specifying the CurrentUICulture

### Translation

The first step in localization is translating the strings that can be localized to the destination locale.

N> Localization key field should be same for the all locales. Do not translate it.

### Resource File and File Name Conventions

After translating the strings that can be localized, perform the following in the application:

Right-click the project file to create a new folder in the project. Select Add-> New Folder and re-name the folder as "Resources".

N> The folder name should strictly be "Resources".

Now, right-click the Resources folder to create a new resource file in the Visual Studio project. Navigate to Add -> New Item.

![](Localization_images/Localization_img54.png)

![](Localization_images/Localization_img55.png)

Select "Resources File" from the list. Then name the resource file: Syncfusion.OlapGrid.WPF.ar-AE.resx and click Add.

N> The resource file name should strictly be in the format "Syncfusion.OlapGrid.WPF.<<Culture Code>>.resx".
   
Copy and paste the translated locale to the resource file created in the earlier step.

### Specifying the CurrentUICulture

Now, you need to specify the CurrentUICulture of the application. We can specify the CurrentUICulture either from Application_Startup in App.xaml.cs or from the constructor in the MainPage (If you are specifying the current culture on the main page, then make sure that it is assigned before the InitializeComponent method).

{% highlight c# %}
 
public MainWindow()
{
	//Set the current thread culture to load the localization resource file.    
	System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("ar-AE");
	InitializeComponent();
	if (System.Globalization.CultureInfo.CurrentUICulture.ToString() == "ar-AE") 
		this.FlowDirection = System.Windows.FlowDirection.RightToLeft;
}

{% endhighlight %}

## RTL Support

RTL support for OlapGrid is used to display the content from right to left by setting the "FlowDirection" property to "RightToLeft". The following code sample explains how to set this property.

{% tabs %}
  
{% highlight xaml %}

<syncfusion:OlapGrid x:Name="olapGrid" FlowDirection="RightToLeft" ReportName="SalesReport" SharedDataManagerName="localManager" olapshared:DataSource.DataManagerName="localManager"/>  

{% endhighlight %}

{% highlight c# %}

this.olapGrid.FlowDirection = System.Windows.FlowDirection.RightToLeft;

{% endhighlight %}

{% highlight vbnet %}

Me.olapGrid.FlowDirection = System.Windows.FlowDirection.RightToLeft;

{% endhighlight %}

{% endtabs %}

![](Localization_images/Localization_img53.png)

A sample is locally available in the following location:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapGrid.WPF\Samples\Localization\Localization
