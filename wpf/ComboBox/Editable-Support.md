---
layout: post
title: Editable Support | wpf | Syncfusion
description: Learn about Editable support in Syncfusion WPF ComboBox (ComboBoxAdv) control and more details.
platform: wpf
control: ComboBoxAdv
documentation: ug
---

# Editable Property in ComboBox

## IsEditable

It allows user to edit the text in the ComboBoxAdv.

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
IsEditable </td><td>
It is possible to edit the text of ComboBoxAdv.</td><td>
Dependency Property</td><td>
Boolean</td><td>
NA</td></tr>
</table>

## Adding IsEditable property to an application 

IsEditable property can be added directly to an application in the following way: 

{% tabs %}
{% highlight xaml %}

<syncfusion:ComboBoxAdv IsEditable="true"></syncfusion:ComboBoxAdv>

{% endhighlight %}

{% highlight c# %}

ComboBoxAdv comboBox = new ComboBoxAdv();       
comboBox.IsEditable = true;
{% endhighlight %}
{% endtabs %}

![Adding IsEditable property to an application](ComboBoxAdv_images/ComboBoxAdv_img12.png)

N> It can be applied when `AllowMultiSelect` property is not assigned as true.
