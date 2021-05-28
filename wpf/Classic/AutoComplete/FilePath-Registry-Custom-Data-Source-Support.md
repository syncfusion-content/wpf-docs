---
layout: post
title: FilePath Registry in WPF AutoComplete Control | Syncfusion
description: Learn here all about FilePath Registry Custom Data Source Support in Syncfusion WPF AutoComplete (Classic) control and more.
platform: wpf
control: AutoComplete
 documentation: ug
---

# FilePath Registry Custom Data Source Support in WPF AutoComplete

AutoComplete can be used with different kinds of Data Source like FilePath, Registry & CustomSource. The Data 
Source of the AutoComplete control can be set using the [Source](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_Source) property.

When the value of the Source property is set as FilePath, the AutoComplete will displays the path in the local 
system as the source. This is illustrated in the following image. 

![file path support](FilePath-Registry--Custom-Data-Source-Support_images/FilePath-Registry--Custom-Data-Source-Support_img1.png)

Source—FilePath
{:.caption}

When the value of the [Source](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_Source) property is set as Registry, the AutoComplete loads the values from the Registry. It 
is used when the Registry keys are required as input. This is illustrated in the image given below.

![source registry](FilePath-Registry--Custom-Data-Source-Support_images/FilePath-Registry--Custom-Data-Source-Support_img2.png)

Source—Registry
{:.caption}

When the value of the [Source](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_Source) property is set as Custom, the AutoComplete loads the values from the Business objects 
bounded to the AutoComplete control by using the [CustomSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_CustomSource) property. This is illustrated in the image given 
below.

![source custom](FilePath-Registry--Custom-Data-Source-Support_images/FilePath-Registry--Custom-Data-Source-Support_img3.png)

Source—Custom
{:.caption}

## Adding data source support to an application

AutoComplete can be used with different kinds of Data Sources using the [Source](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_Source) property. This support can be added 
to the application as mentioned in the following code example.

{% tabs %}
{% highlight xaml %}

<syncfusion:AutoComplete x:Name="AutoComplete1" Source="FilePath"/>
<syncfusion:AutoComplete x:Name="AutoComplete2" Source ="Registry"/>
<syncfusion:AutoComplete x:Name="AutoComplete3" Source="Custom">     
<syncfusion:AutoComplete.CustomSource>             
<local:CustomerListCollection/>     
</syncfusion:AutoComplete.CustomSource>
</syncfusion:AutoComplete>

{% endhighlight %}

{% highlight c# %}

AutoComplete autoComplete1 = new AutoComplete();
this.autoComplete1.Source = SourceMode.FilePath;

AutoComplete autoComplete2 = new AutoComplete();
this.autoComplete2.SelectionMode = SourceMode.Registry;

AutoComplete autoComplete3 = new AutoComplete();
this.autoComplete3.SelectionMode = SourceMode.Custom;

List<String> products = new List<String>();
customSource.Add("Diagram");
customSource.Add("Gauge");
customSource.Add("Chart");
customSource.Add("Schedule");
customSource.Add("Grid");
customSource.Add("DocIo");
customSource.Add("XlsIo");
customSource.Add("Pdf");
customSource.Add("RichTextBox");
customSource.Add("ReportBuilder");
this.autoComplete3.CustomSource = products;

{% endhighlight %}
{% endtabs %}

## Tables for properties, methods, and events

### Events

* [SourceChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html)

## Sample link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo
