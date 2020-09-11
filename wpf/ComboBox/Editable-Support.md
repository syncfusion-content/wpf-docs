---
layout: post
title: Editable Support | wpf | Syncfusion
description: editable support in comboboxadv 
platform: wpf
control: ComboBoxAdv
documentation: ug
---

# IsEditable

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

#### Adding IsEditable property to an application 

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

![](ComboBoxAdv_images/ComboBoxAdv_img12.png)

N> It can be applied when `AllowMultiSelect` property is not assigned as true.
