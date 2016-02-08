---
layout: post
title: RTL Support| OLAP Client  | Wpf | Syncfusion
description: rtl support
platform: wpf
control: OLAP Client 
documentation: ug
---

# RTL Support

Right-to-left support has been provided for the OLAP Client control for WPF. Users can now display content from right to left by setting 
the flow direction option in the control. 

## Adding RTL Support for OLAP Client in an Application 

To enable RTL support, the FlowDirection property of the OLAP Client control needs to be set as RightToLeft. The following code sample explains how to set the FlowDirection property. It can be set through XAML or C# code.


{% tabs %}
{% highlight xaml %} 



<syncfusion:OlapClient x:Name="olapClient1" FlowDirection="RightToLeft" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"                                       OlapDataManager="{Binding ClientDataManager}" />

{% endhighlight %}


{% highlight C# %} 


  this.olapClient1.FlowDirection = System.Windows.FlowDirection.RightToLeft;
  
 {% endhighlight %}

{% highlight vbnet %} 



  Me.olapClient1.FlowDirection = System.Windows.FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}


![](RTL-Support_images/RTL-Support_img1.jpeg)



RTL support of OLAP Client
{:.caption}


### Sample Link

A sample is available locally in the following location:

SystemDrive:\Users\<user_name>\AppData\Local\Syncfusion\EssentialStudio\<version_number>\BI\WPF\OlapClient.WPF\Localization\LocalizationDemo

