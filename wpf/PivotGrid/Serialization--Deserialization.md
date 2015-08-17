---
layout: post
title: Serialization/Deserialization 
description: Serialization/Deserialization 
platform: wpf
control: PivotGrid
documentation: ug
---


## Serialization/Deserialization


Using this feature, you can save the current state of PivotGrid as an XML file format and restore the same at any time. 

The following properties of PivotGrid control can be serialized.

_Property Table_

<table>
<tr>
<td>
{{ '**Property Name**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td></tr>
<tr>
<td>
AllowResizeColumns</td><td>
bool</td></tr>
<tr>
<td>
AllowResizeRows</td><td>
bool</td></tr>
<tr>
<td>
AllowSelection</td><td>
bool</td></tr>
<tr>
<td>
AutoSizeColumnCount</td><td>
int</td></tr>
<tr>
<td>
AutoSizeOption</td><td>
GridAutoSizeOption</td></tr>
<tr>
<td>
AutoSizeRowCount</td><td>
int</td></tr>
<tr>
<td>
DeferLayoutUpdate</td><td>
bool</td></tr>
<tr>
<td>
Filters</td><td>
ObservableCollection</td></tr>
<tr>
<td>
FreezeHeaders</td><td>
bool</td></tr>
<tr>
<td>
IsDynamicData</td><td>
bool</td></tr>
<tr>
<td>
PivotCalculations</td><td>
ObservableCollection</td></tr>
<tr>
<td>
PivotColumns</td><td>
ObservableCollection</td></tr>
<tr>
<td>
PivotFields</td><td>
ObservableCollection</td></tr>
<tr>
<td>
PivotRows</td><td>
ObservableCollection</td></tr>
<tr>
<td>
ShowCalculationsAsColumns</td><td>
bool</td></tr>
<tr>
<td>
ShowFieldList</td><td>
bool</td></tr>
<tr>
<td>
ShowGrandTotals</td><td>
bool</td></tr>
<tr>
<td>
ShowGroupingBar</td><td>
bool</td></tr>
<tr>
<td>
GroupingBar.AllowFiltering</td><td>
bool</td></tr>
<tr>
<td>
GroupingBar.AllowSorting</td><td>
bool</td></tr>
</table>


On Serialization, the expand and the collapse state of PivotGrid cells are maintained. So while de-serializing, the item source specified for the Grid should be as same as that when used in Serialization. This can be ignored by setting IgnoreExpandCollapseOnSerialization property of PivotGrid control to False.

#### Use Case Scenarios

Serialization can be implemented for applications which need to save its data and structure after the application is closed. Serialization supports to save the structure and data of PivotGridControl to an XML file and it can be loaded at any time.

#### Adding Serialization/Deserialization

Serialization/Deserialization can be achieved using the following code snippet,

{% highlight C# %} 

[C#]



/// Serialize the PivotGrid into XML file format.

this.pivotGrid1.Serialize();



/// De serialize the PivotGrid from the saved XML file.

this.pivotGrid1.Deserialize();



/// Serialize the PivotGrid into XML file format and saves it in the specified location.

this.pivotGrid1.Serialize(@"C:/PivotGrid.xml");



/// De serialize the PivotGrid from the specified XML file.

this.pivotGrid1.Deserialize(@"C:/PivotGrid.xml");

 {% endhighlight %} 

{% highlight vbnet %} 

[VB]



' Serialize the PivotGrid into XML file format.

Me.pivotGrid1.Serialize()



' De serialize the PivotGrid from the saved XML file.

Me.pivotGrid1.Deserialize()





' Serialize the PivotGrid into XML file format and saves it in the specified location.

Me.pivotGrid1.Serialize("C:/PivotGrid.xml")



' De serialize the PivotGrid from the specified XML file.

Me.pivotGrid1.Deserialize("C:/PivotGrid.xml")

{% endhighlight %} 



#### Methods

_Methods Table_

<table>
<tr>
<td>
{{ '**Method**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Parameters**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Return Type**' | markdownify }}</td></tr>
<tr>
<td>
Serialize()</td><td>
Serializes the PivotGrid into XML file format using the save file dialog</td><td>
</td><td>
void</td><td>
void</td></tr>
<tr>
<td>
Deserialize()</td><td>
Deserializes the PivotGrid from the saved XML file using the open file dialog</td><td>
</td><td>
void</td><td>
void</td></tr>
<tr>
<td>
Serilize(string fileName)</td><td>
Serializes the PivotGrid into XML file format and saves it in the specified location</td><td>
string fileName</td><td>
void</td><td>
void</td></tr>
<tr>
<td>
Deserialize(string filename)</td><td>
Deserializes the PivotGrid from the specified XML file</td><td>
string fileName</td><td>
void</td><td>
void</td></tr>
</table>


![Description: C:/Users/dwarageshmb/Desktop/2011 Vol 1 Docs/Serialization.png](Features_images/Features_img23.png)



#### Sample Link

To access a Conditional Formatting sample:

1. Open the Syncfusion Dashboard.
2. Click Business Intelligence.
3. Click the WPF drop-down list, and select Explore Samples.
4. Navigate to PivotAnalysis.WPF -> Samples -> Serialization -> Serialization Demo.


