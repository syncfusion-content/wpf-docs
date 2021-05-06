---
layout: post
title: Localization in WPF Olap Gauge control | Syncfusion
description: Learn about Localization support in Syncfusion WPF Olap Gauge control and more.
platform: wpf
control: OLAP Gauge
documentation: ug
---

# Localization in WPF Olap Gauge

Localization is the key feature to provide software solutions that are targeted at global users. The OLAP gauge allows users to localize the control to a specific locale and supports “resx” based localization.

You should perform the following steps to localize the control:

* Translation.
* Resource file and file name conventions.
* Culture specification.

## Translation

The first step in localization is translating the strings that can be localized to the destination locale.

N> Localization key field should be same for all the locales. Do not translate the key fields.

## Resource file and file name conventions

After translating the strings, perform the following steps in the application:

1. Right-click the project file to create a new folder in the project by selecting Add > New Folder and rename the folder as “Resources”.

2. Then, right-click the **Resources** folder to create a new resource file by selecting Add > New Item.

![Shows add new item for WPF OLAPGauge](Localization_images/Localization-step1.png)

![Shows add new resource file for WPF OLAPGauge](Localization_images/Localization-step2.png)

N> The resource file name should be in the format “Syncfusion.OlapGauge.wpf.&lt;Culture Code&gt;.resx”.

3. Copy and paste the translated locale to the resource file which is created in the previous step.

## Culture specification

You should specify the CurrentUICulture in the Application_Startup method of App.xaml.cs file or in the constructor of MainPage.xaml.cs file.

N> If you are specifying the current culture in the constructor of MainPage, then ensure that the culture is specified before calling the InitializeComponent() method.

{% tabs %}

{% highlight c# %}

public MainWindow()
{
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("ar");
    InitializeComponent();
}

{% endhighlight %}

{% highlight vb %}

Public Sub New()
    System.Threading.Thread.CurrentThread.CurrentUICulture = New System.Globalization.CultureInfo("ar")
    InitializeComponent()
End Sub

{% endhighlight %}

{% endtabs %}

## RTL

The OLAP gauge provides RTL support to display the content from right-to-left direction by setting the `FlowDirection` property to **RightToLeft**.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge x:Name="OlapGauge1" FlowDirection="RightToLeft"/>

{% endhighlight %}

{% highlight C# %}

OlapGauge1.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}

{% highlight vb %}

OlapGauge1.FlowDirection = FlowDirection.RightToLeft

{% endhighlight %}

{% endtabs %}

![Shows the content move from right to left direction in WPF OLAPGauge](Localization_images/Localization-RTL.png)

A demo sample is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Localization\Localization Demo\
