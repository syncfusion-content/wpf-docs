---
layout: post
title: Popup-Resize-Support | AutoComplete | wpf | Syncfusion
description: popup resize support
platform: wpf
control: AutoComplete
documentation: ug
---

# Pop-up Resize Support

AutoComplete allows you to resize the drop-down list popup using the CanResizePopup property. If this property is set as True the thumb will be shown in the right bottom corner of the drop-down list which adjusts the height and the width of the popup at runtime. If this property is set as False, the visibility of the thumb will be collapsed and you will not be able to resize the popup at runtime. 

## Adding pop-up resizing support to an application 

You can use CanResizePopup property to attain this functionality by setting the value as True.

{% tabs %}
{% highlight xaml %}

<syncfusion:AutoComplete x:Name="AutoComplete1" CanResizePopup ="true" />

{% endhighlight %}

{% highlight c# %}

AutoComplete autoComplete1 = new AutoComplete();
autoComplete1. CanResizePopup = true;

{% endhighlight %}
{% endtabs %}

## Properties

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
CanResizePopup</td><td>
Gets or sets the value of CanResizePopup in the AutoComplete.</td><td>
DependencyProperty</td><td>
bool</td><td>
</td></tr>
</table>

## Sample link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo
