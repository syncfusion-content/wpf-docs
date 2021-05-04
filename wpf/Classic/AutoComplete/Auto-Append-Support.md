---
layout: post
title: Auto Append Support in WPF Wizard Control control | Syncfusion
description: Learn here all about Auto Append Support support in Syncfusion WPF AutoComplete (Classic) control and more.
platform: wpf
control: AutoComplete
documentation: ug
---

# Auto Append Support in WPF AutoComplete (Classic)

Auto Append is used to guide the complete text by appending the entered text with suitable text from the data source, when a text is entered in the AutoComplete textbox. AutoComplete allows you to enable Auto Append using [IsAutoAppend](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_IsAutoAppend) property.

![Auto append support](Auto-Append-Support_images/Auto-Append-Support_img1.png)

Auto Append
{:.caption}

## Adding auto append support to an application 

If the [IsAutoAppend](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_IsAutoAppend) property is set as True, once you enter the text the AutoComplete guides you to complete text, by appending the entered text with suitable text from the data source. If this property is set as False the matched suitable text will not append with the entered text.

{% tabs %}
{% highlight xaml %}

<syncfusion:AutoComplete x:Name="AutoComplete1" IsAutoAppend="true"/>

{% endhighlight %}

{% highlight c# %}

AutoComplete autoComplete1 = new AutoComplete();this.autoComplete1.IsAutoAppend = true;

{% endhighlight %}
{% endtabs %}

## Tables for properties and events

### Properties

* [IsAutoAppend](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_IsAutoAppend)

### Events

* [IsAutoAppendChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html)

## Sample link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo
