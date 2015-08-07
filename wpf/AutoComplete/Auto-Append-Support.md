---
layout: post
title: Auto-Append-Support
description: auto append support
platform: wpf
control: AutoComplete
documentation: ug
---

# Auto Append Support

Auto Append is used to guide the complete text by appending the entered text with suitable text from the data source, when a text is entered in the AutoComplete textbox. AutoComplete allows you to enable Auto Append using IsAutoAppend property.



![](Auto-Append-Support_images/Auto-Append-Support_img1.png)





## Adding Auto Append Support to an Application 

If the IsAutoAppend property is set as True, once you enter the text the AutoComplete guides you to complete text, by appending the entered text with suitable text from the data source. If this property is set as False the matched suitable text will not append with the entered text.

{% highlight xml %}

[XAML]
<syncfusion:AutoComplete x:Name="AutoComplete1" IsAutoAppend="true"/>
{% endhighlight %}

{% highlight cs %}

[C#]
AutoComplete autoComplete1 = new AutoComplete();this.autoComplete1.IsAutoAppend = true;
{% endhighlight %}


## Tables for properties, and events

### Properties

  _Property Table for Auto Append_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td><td>
Reference links </td></tr>
<tr>
<td>
IsAutoAppend</td><td>
Gets or sets the value of IsAutoAppend in the AutoComplete.</td><td>
DependencyProperty</td><td>
bool(true)</td><td>
</td></tr>
</table>


### Events

   _Event Table for Auto Append_

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th><th colspan = "2">
Reference links </th></tr>
<tr>
<th>
IsAutoAppendChanged</th><th>
 When the value of IsAutoAppend changed this event will be triggered.It cannot be cancelled.</th><th>
DependencyObject,DependencyPropertyChangedEventArgs</th><th colspan = "2">
DependencyPropertyChangedCallBack </th><th>
</th></tr>
</table>


## Sample Link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo

