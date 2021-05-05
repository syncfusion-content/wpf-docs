---
layout: post
title: Watermark Support in WPF ComboBox control | Syncfusion
description: Learn here all about Watermark Support support in Syncfusion WPF ComboBox (ComboBoxAdv) control and more.
platform: wpf
control: ComboBoxAdv
documentation: ug
---

# Watermark Support in WPF ComboBox (ComboBoxAdv)

It displays the default text in the ComboBoxAdv when none of the items is selected in the drop down list.

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
DefaultText </td><td>
It is possible to display the default text.</td><td>
Dependency Property</td><td>
String</td><td>
NA</td></tr>
</table>

#### Adding DefaultText property to an application 

DefaultText property can be added directly to an application in the following way: 

{% tabs %}
{% highlight xaml %}

<syncfusion:ComboBoxAdv DefaultText="..Choose Items.."></syncfusion:ComboBoxAdv>

{% endhighlight %}

{% highlight c# %}

ComboBoxAdv comboBox = new ComboBoxAdv();       
comboBox.DefaultText = "..Choose Items..";

{% endhighlight %}
{% endtabs %}

![Adding default text of watermark-support in WPF combobox](ComboBoxAdv_images/ComboBoxAdv_img10.png)
