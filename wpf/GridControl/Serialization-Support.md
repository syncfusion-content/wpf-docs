---
layout: post
title: Serialization-Support
description: serialization support
platform: wpf
control: Grid Control
documentation: ug
---

# Serialization Support

Essential GridControl supports Serialization. The whole grid can be serialized and deserialized at run-time. 

## Use Case Scenarios

Serialization can be implemented for the applications which need to save its data and structure after the application is closed. Serialization supports to save the structure and data of the GridControl to an XML file and it can be loaded at any time.

Adding Serialization to an Application 

The following sample application explains the implementation of the Serialization support to GirdControl.

1. Create an application. Create a WPF application and add the GridControl to it. 
2. Call the Serialization support methods



In the application, create three buttons. The first button to call the Serialize() method, the second button to make changes to the Grid and the third button is to call the Deserialize() method. The following code snippet explains the implementation of Serialization.

{% highlight c# %}

[C#]

// To Serialize the GridControl.

this.grid.Model.Serialize("Data.xml");



// To Deserialize the GridControl.

this.grid.Model.Deserialize("Data.xml");


{% endhighlight  %}


3. Run the application

Run the application. Click the Serialize button to serialize the initial load; this creates an XML file and saves it. Click the second button ModifyGridStyle to make some changes in the GridControl. Now click the Deserialize button which restores the old settings of the GridControl. 

Supported Properties for Serialization

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

_Serialization Support Table_

<table>
<tr>
<th>
Method </th><th>
Description </th><th>
Parameters </th><th>
Type </th><th>
Return Type </th></tr>
<tr>
<th>
Serialize()</th><th>
A virtual method called to Serialize the GridControl. It stores the settings in an xml file named as specified in its parameter.</th><th>
string  fileName</th><th>
public</th><th>
void</th></tr>
<tr>
<th>
Deserialize()</th><th>
A virtual method called to Deserialize the GridControl. It restores the settings in an xml file named as specified in its parameter.</th><th>
string  fileName</th><th>
public</th><th>
void</th></tr>
<tr>
<th>
SerializeToStream()</th><th>
Serializes the Grid to Stream.</th><th>
TextWriter textWriter</th><th>
public </th><th>
void</th></tr>
<tr>
<th>
SerializeAsString()</th><th>
Serializes the Grid as String.</th><th>
NA</th><th>
public</th><th>
string </th></tr>
<tr>
<th>
DeserializeFromStream</th><th>
Deserializes from the given TextReader.</th><th>
TextReader textReader</th><th>
public</th><th>
void</th></tr>
<tr>
<th>
DeserializeFromString</th><th>
Deserializes from the given String content.</th><th>
string content</th><th>
public</th><th>
void</th></tr>
</table>


## Sample Link

1. Refer to the samples in the shipped Sample Browser. 
2. Go to Essential Studio WPF Sample Browser  Grid  Serialization GridControl Serialization Demo



