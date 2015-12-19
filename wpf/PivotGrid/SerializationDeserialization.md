---
layout: post
title: 13416-SerializationDeserialization
description: 1.3.4.16 serialization/deserialization
platform: wpf
control: PivotGridControl
documentation: ug
---

# Serialization/Deserialization

Serialization can be implemented for applications which need to save its data and structure after the application is closed. Serialization supports to save the structure and data of PivotGridControl to an XML file and it can be loaded at any time.

**Use Case Scenarios**

User could save the current state of PivotGrid in a XML file format and restore the same at any time. 

The following properties of PivotGrid can be serialized.

                                                      List of Properties which gets Serialized

<table>
<tr>
<th>
Property Name</th><th>
Type</th></tr>
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
AllowSelectionWithHeaders</td><td>
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
ObservableCollection<FilterExpression></td></tr>
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
ObservableCollection<PivotComputationInfo></td></tr>
<tr>
<td>
PivotColumns</td><td>
ObservableCollection<PivotItem></td></tr>
<tr>
<td>
PivotFields</td><td>
ObservableCollection<PivotItem></td></tr>
<tr>
<td>
PivotRows</td><td>
ObservableCollection<PivotItem></td></tr>
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
<tr>
<td>
EnableColumnHeader</td><td>
bool</td></tr>
<tr>
<td>
EnableRowHeader</td><td>
bool</td></tr>
<tr>
<td>
AllowMultiFunctionaSortFilter</td><td>
bool</td></tr>
<tr>
<td>
VisibleRecords</td><td>
int</td></tr>
</table>

##Using the Serialization/Deserialization in PivotGrid

On Serialization, expand and collapse state of PivotGrid cells are maintained. So while de-serializing, the item source specified for the Grid should be as same as that when used in Serialization. This can be ignored by setting IgnoreExpandCollapseOnSerialization property of PivotGrid control to False.

The following are the methods which has been used in PivotGrid for serialization/deserialization.

                                                          Methods Table

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Return Type</th></tr>
<tr>
<td>
Serialize()</td><td>
Serializes the PivotGrid into XML file format using the save file dialog</td><td>
-</td><td>
void</td></tr>
<tr>
<td>
Deserialize()</td><td>
Deserializes the PivotGrid from the saved XML file using the open file dialog</td><td>
-</td><td>
void</td></tr>
<tr>
<td>
Serilize(string fileName)</td><td>
Serializes the PivotGrid into XML file format and saves it in the specified location</td><td>
string fileName</td><td>
void</td></tr>
<tr>
<td>
Deserialize(string filename)</td><td>
Deserializes the PivotGrid from the specified XML file</td><td>
string fileName</td><td>
void</td></tr>
<tr>
<td>
SerializedXmlString()</td><td>
Serializes some specific properties in PivotGridControl into string format.</td><td>
-</td><td>
string</td></tr>
<tr>
<td>
Deserialize(string xmlstring)</td><td>
De-serializes the XML string format into PivotGridControl.</td><td>
string xmlstring</td><td>
void</td></tr>
</table>

###Serialization

After defining a PivotGrid control, call the Serialize() method in separate event handler. Please refer the below code snippet.

{% highlight C# %}

public partial class MainWindow: Window {
    PivotGridControl pivotGrid = new PivotGridControl();
    public MainWindow() {
        InitializeComponent();
        this.grid1.Children.Add(pivotGrid);
    }

    void button1_Click(object sender, RoutedEventArgs e) {
        // Serialize the PivotGrid into XML file format.
        pivotGrid.Serialize();
        // Serialize the PivotGrid into XML file format and saves it in the specified location.
        pivotGrid.Serialize(@ "C:/PivotGrid.xml");
        // Serializes some specific properties in PivotGridControl into string format
        pivotGrid.SerializedXmlString();
    }
}

{% endhighlight %}

###De-Serialization

After defining a PivotGrid control, call the De-Serialize() method in separate event handler. Please refer the below code snippet.

{% highlight C# %}

public partial class MainWindow: Window {
    PivotGridControl pivotGrid = new PivotGridControl();
    public MainWindow() {
        InitializeComponent();
        this.grid1.Children.Add(pivotGrid);
    }

    void button1_Click(object sender, RoutedEventArgs e) {
        // De-Serialize the PivotGrid into XML file format.
        pivotGrid.Deserialize();
        // De-serializes the PivotGrid from the specified XML file
        pivotGrid.Deserialize(@ "C:/PivotGrid.xml");
        // De-serializes the XML string format into PivotGridControl
        pivotGrid.DeserializeXmlString(pivotGrid.SerializedXmlString());
    }
}

{% endhighlight %}

![](Serialization images/Serialized PivotGrid.png)
