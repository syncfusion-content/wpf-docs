---
layout: post
title: Filter-Support
description: filter support
platform: wpf
control: AutoComplete
documentation: ug
---

# Filter Support

Filter support is used to filter the matched list of items from the linked source depending on the text entered in the AutoComplete textbox. AutoComplete allows the user to enable Filter the items using IsFilter property.

![](Filter-Support_images/Filter-Support_img1.png)

_Filter Support_




## Adding Filter Support to an Application 

If the IsFilter property is set as True, once you enter text in the AutoComplete textbox, the matched list of items will be displayed in the drop-down list. If this property is set as False the matched list of items will not be displayed in the drop-down list, instead all the items will be displayed.




{% highlight xml %}

<syncfusion:AutoComplete x:Name="AutoComplete1" IsFilter="true"/></td></tr>
{% endhighlight %}

{% highlight c# %}

AutoComplete autoComplete1 = new AutoComplete();this.autoComplete1.IsFilter = true;</td></tr>
{% endhighlight %}


## Tables for properties, methods, and events

### Properties

  _Property Table for Filter_

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
IsFilter</td><td>
Gets or sets the value of IsFilter in the AutoComplete.</td><td>
DependencyProperty</td><td>
bool(true)</td><td>
</td></tr>
</table>


### Events

  _Event Table for Filter_

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th><th colspan = "2">
Reference links </th></tr>
<tr>
<td>
IsFilterChanged</td><td>
 When the value of IsFilter is changed, this event will be triggered.It cannot be cancelled.</td><td>
DependencyObject,DependencyPropertyChangedEventArgs</td><td colspan = "2">
DependencyPropertyChangedCallBack </td><td>
</td></tr>
</table>


## Sample Link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo

