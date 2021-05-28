---
layout: post
title: Popup Resize Support in WPF AutoComplete Control | Syncfusion
description: Learn here all about Popup Resize Support in Syncfusion WPF AutoComplete (Classic) control and more.
platform: wpf
control: AutoComplete
 documentation: ug
---

# Popup Resize Support in WPF AutoComplete (Classic)

AutoComplete allows you to resize the drop-down list popup using the [CanResizePopup](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_CanResizePopup) property. If this property is set as True the thumb will be shown in the right bottom corner of the drop-down list which adjusts the height and the width of the popup at runtime. If this property is set as False, the visibility of the thumb will be collapsed and you will not be able to resize the popup at runtime. 

## Adding pop-up resizing support to an application 

You can use [CanResizePopup]((https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_CanResizePopup) property to attain this functionality by setting the value as True.

{% tabs %}
{% highlight xaml %}

<syncfusion:AutoComplete x:Name="AutoComplete1" CanResizePopup ="true" />

{% endhighlight %}

{% highlight c# %}

AutoComplete autoComplete1 = new AutoComplete();
autoComplete1. CanResizePopup = true;

{% endhighlight %}
{% endtabs %}

## Sample link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo
