---
layout: post
title: Serialization in WPF GridControl | Syncfusion
description: Learn about Serialization support in Syncfusion Essential Studio WPF GridControl, its elements and more details.
platform: wpf
control: GridControl
documentation: ug
---

# Serialization in WPF GridControl

Essential GridControl supports Serialization. The whole grid can be serialized and deserialized at run-time. 

### Use Case Scenarios

Serialization can be implemented for the applications which need to save its data and structure after the application is closed. Serialization supports to save the structure and data of the GridControl to an XML file and it can be loaded at any time.

## Adding Serialization to an Application 

The following sample application explains the implementation of the Serialization support to GirdControl.

1.Create an application. Create a WPF application and add the GridControl to it. 
2.Call the Serialization support methods

In the application, create three buttons. The first button to call the Serialize() method, the second button to make changes to the Grid and the third button is to call the Deserialize() method. The following code snippet explains the implementation of Serialization.

{% tabs %}
{% highlight c# %}
// To Serialize the GridControl.
this.grid.Model.Serialize("Data.xml");

// To Deserialize the GridControl.
this.grid.Model.Deserialize("Data.xml");
{% endhighlight  %}
{% endtabs %}

3.Run the application

Run the application. Click the Serialize button to serialize the initial load; this creates an XML file and saves it. Click the second button ModifyGridStyle to make some changes in the GridControl. Now click the Deserialize button which restores the old settings of the GridControl. 

### Supported Properties for Serialization

The following properties are Serialized in the GridControl.

* RowCount
* ColCount
* ActivateCurrentCellBehavior
* AllowSelection
* AllowSelectionOnShiftTab
* ColumnSizer
* CurrentCellBorder
* CurrentCellBorderWidth
* DataObjectConsumerOptions
* DrawSelectionOptions
* ExcelLikeCurrentCell
* ExcelLikeSelectionFrame
* HighlightSelectionBorder
* HighlightSelectionBorderWidth
* ListBoxModeAllowUIElementClick
* ListBoxSelectionMode
* MaxLength
* ScrollFrozen
* ShowCurrentCell
* WrapCell
* WrapCellBehavior

## Methods

<table>
<tr>
<th>
Method </th><th>
Description </th><th>
Parameters </th><th>
Type </th><th>
Return Type </th></tr>
<tr>
<td>
Serialize()</td><td>
A virtual method called to Serialize the GridControl. It stores the settings in an XML file named as specified in its parameter.</td><td>
string  fileName</td><td>
public</td><td>
void</td></tr>
<tr>
<td>
Deserialize()</td><td>
A virtual method called to Deserialize the GridControl. It restores the settings in an XML file named as specified in its parameter.</td><td>
string  fileName</td><td>
public</td><td>
void</td></tr>
<tr>
<td>
SerializeToStream()</td><td>
Serializes the Grid to Stream.</td><td>
TextWriter textWriter</td><td>
public </td><td>
void</td></tr>
<tr>
<td>
SerializeAsString()</td><td>
Serialize the Grid as String.</td><td>
NA</td><td>
public</td><td>
string </td></tr>
<tr>
<td>
DeserializeFromStream</td><td>
Deserialize from the given TextReader.</td><td>
TextReader textReader</td><td>
public</td><td>
void</td></tr>
<tr>
<td>
DeserializeFromString</td><td>
Deserialize from the given String content.</td><td>
string content</td><td>
public</td><td>
void</td></tr>
</table>


N> Download demo application from [GitHub](https://github.com/syncfusion/wpf-demos/tree/master/GridControl/Serialization)



