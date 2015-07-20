---
layout: post
title: Basic-Core-Features
description: basic core features
platform: wpf
control: AutoComplete
documentation: ug
---

# Basic Core Features

AutoComplete supports basic core features which are listed as follows.

* SelectedIndex— Used to set and get the index of the selected item.
* SelectedItem—Used to get which item of the AutoComplete has been selected.
* SelectedValue—Used to get the value of the selected item, the value of the SelectedValue property will be set based on the value of the SelectedValuePath property.
* SelectedValuePath—Used to set the value of the SelectedValue property of the AutoComplete.
* DisplayMemberPath—Used to set the value for the items displayed in the drop-down list.
* IsDropDownOpen—Used to open or close the Drop-down list by setting its value as True or False.
* SelectionChanged.
* TextChanged.

Using Basic Core Features in an Application

In the SelectionChanged event the SelectedIndex, SelectedItem & SelectedValue properties can be used in the application to get these property values. The properties and events listed can be used in the application as mentioned below.

[C#]

List<String> Products = new List<String>();

Products.Add("Diagram");

Products.Add("Gauge");

Products.Add("Chart");

Products.Add("Business Intelligence");

AutoComplete autoComplete1 = new AutoComplete();

autoComplete1.CustomSource = Products;

autoComplete1.SelectedIndex = 1;

autoComplete1.IsDropDownOpen = true;

autoComplete1.SelectionChanged += 

new SelectionChangedEventHandler(autoComplete1_SelectionChanged);

autoComplete1.TextChanged += new PropertyChangedCallback(autoComplete1_TextChanged);



void autoComplete1_TextChanged(DependencyObject d, 

                                   DependencyPropertyChangedEventArgs e)

{

      this.textBlock.Text = this.autoComplete1.Text;

}



void autoComplete1_SelectionChanged(object sender, 

                                            SelectionChangedEventArgs e)

{

      MessageBox.Show("SelectedItem: " +

      this.autoComplete1.SelectedItem.ToString()+ "\n" + "SelectedValue: "

      + this.autoComplete1.SelectedValue.ToString())

}



Tables for Properties, and Events

Properties

  _Properties Table for Basic Features_

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
SelectedIndex</td><td>
Gets or sets the SelectedIndex of the AutoComplete.</td><td>
DependencyProperty</td><td>
Int(-1)</td><td>
</td></tr>
<tr>
<td>
SelectedValue</td><td>
Gets or sets the SelectedValue of the AutoComplete.</td><td>
DependencyProperty</td><td>
Object(null)</td><td>
</td></tr>
<tr>
<td>
SelectedItem</td><td>
Gets or sets the SelectedItem of the AutoComplete.</td><td>
DependencyProperty</td><td>
Object(null)</td><td>
</td></tr>
<tr>
<td>
SelectedValuePath</td><td>
Gets or sets the SelectedValuePath of the AutoComplete.</td><td>
DependencyProperty</td><td>
String(null)</td><td>
</td></tr>
<tr>
<td>
DisplayMemberPath</td><td>
Gets or sets the DisplayMemberPath of the AutoComplete.</td><td>
DependencyProperty</td><td>
String(null)</td><td>
</td></tr>
</table>
Events

   _Events Table for Basic Features_

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th><th>
Reference links </th></tr>
<tr>
<th>
SelectionChanged</th><th>
When the value of SelectedItem property is changed this event will be triggered.It cannot be cancelled.</th><th>
Object,SelectionChangedEventArgs</th><th>
SelectionChangedEventHandler </th><th>
</th></tr>
<tr>
<th>
TextChanged</th><th>
When the value of the Text property is changed this event will be triggered.It cannot be cancelled.</th><th>
DependencyObject,DependencyPropertyChangedEventArgs</th><th>
DependencyPropertyChangedCallBack </th><th>
</th></tr>
</table>


Sample Link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo

