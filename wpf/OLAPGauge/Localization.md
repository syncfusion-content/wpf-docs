---
layout: post
title: RTL Support | OlapGauge | wpf | Syncfusion
description: rtl support
platform: wpf
control: OlapGauge
documentation: ug
---

# Localization

Localization deals with customizing data and resources for specific culture or language. The built-in localization and globalization mechanism in WPF allows you to localize any string resource used by OlapGauge control.

We need to create and place the resource files in a separate location inside in the user application. Then we can access to the culture specific resources from the current application assembly.

For this, first create a resource file for our OlapGauge control and translate the strings to your culture. Once it is translated, you might use the resources in your projects by setting corresponding culture in your application.

![](Localization_images/RTL-Support_img1.png)

Please refer the below code sample 

{% highlight C# %}

public MainWindow()
{
    //Set the current thread culture to load the localization resource file.    
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("ar-AE");
    InitializeComponent();
    if (System.Globalization.CultureInfo.CurrentUICulture.ToString() == "ar-AE") 
    {
        this.FlowDirection = System.Windows.FlowDirection.RightToLeft;
    }
}

{% endhighlight %}

## RTL Support

RTL support for OlapGauge is used to display the content from right to left by setting the **"FlowDirection"** property to **"RightToLeft"**. The following code sample explains how to set this property.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge x:Name="olapGauge" FlowDirection="RightToLeft" Grid.Column="0" HorizontalAlignment="Stretch" ReportName="SalesReport" olapshared:DataSource.ConnectionString="{Binding OlapConnectionString}">

{% endhighlight %}

{% highlight c# %}
 
this.olapGauge.FlowDirection = System.Windows.FlowDirection.RightToLeft;

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapGauge.FlowDirection = System.Windows.FlowDirection.RightToLeft;

{% endhighlight %}

{% endtabs %}

![](Localization_images/RTL-Support_img2.png)

A sample is available locally in the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGauge.WPF\Samples\Localization\Localization Demo\

