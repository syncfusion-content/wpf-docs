---
layout: post
title: Delimiter Support in WPF ComboBox control | Syncfusion
description: Learn here all about Delimiter Support support in Syncfusion WPF ComboBox (ComboBoxAdv) control and more.
platform: wpf
control: ComboBoxAdv
documentation: ug
---

## Delimiter String Customization

A Delimiter string in a ComboBoxAdv is “A string that can be displayed between the selected items in the ComboBoxAdv”. We can customize this string by using the property called `SelectedValueDelimiter` in the ComboBoxAdv.

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
SelectedValueDelimiter </td><td>
The selected items can be separated by the given string.</td><td>
Dependency Property</td><td>
String</td><td>
NA</td></tr>
</table>

### Adding delimiter string customization to an application 

Delimiter string customization can be added directly to an application using the following code snippet: 

{% tabs %}
{% highlight xaml %}

<syncfusion:ComboBoxAdv SelectedValueDelimiter="#"></syncfusion:ComboBoxAdv>

{% endhighlight %}

{% highlight c# %}

ComboBoxAdv comboBox = new ComboBoxAdv();     
comboBox.SelectedValueDelimiter = "#";

{% endhighlight %}
{% endtabs %}

![ComboBoxAdv_img11](ComboBoxAdv_images/ComboBoxAdv_img11.png)
