---
layout: post
title: MultiSelection Support | wpf | Syncfusion
description: Learn about MultiSelection support in Syncfusion WPF ComboBox (ComboBoxAdv) control and more details.
platform: wpf
control: ComboBoxAdv
documentation: ug
---

# Multiple Selections in ComboBox

If we want to select more than one item in the ComboBoxAdv, AllowMultiSelect property will be helpful to do this. It allows you to select multiple items in the drop down list. The selected items will be displayed in ascending order as shown in the drop down list. When AllowMultiSelect property is true, the SelectedItems property exposes the items that are selected in the drop down list.

## Properties

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
AllowMultiSelect</td><td>
Multiple items can be selected.</td><td>
Dependency Property</td><td>
Boolean</td><td>
NA</td></tr>
<tr>
<td>
SelectedItems</td><td>
It contains the selected items value</td><td>
Dependency Property</td><td>
ObservableCollection&lt;object&gt;</td><td>
NA</td></tr>
</table>

## Adding multiple selections to an application 

`AllowMultiSelect` property can be added directly to an application using the following code snippet.

{% tabs %}
{% highlight xaml %}

<syncfusion:ComboBoxAdv AllowMultiSelect="True"></syncfusion:ComboBoxAdv></td></tr>

{% endhighlight %}

{% highlight c# %}

ComboBoxAdv comboBox = new ComboBoxAdv();
comboBox.AllowMultiSelect = true;

{% endhighlight %}
{% endtabs %}

![Adding multiple selections to an application](ComboBoxAdv_images/ComboBoxAdv_img9.png)
