---
layout: post
title: Serialization and Deserialization in WPF Pivot Grid | Syncfusion
description: Learn about Serialization and Deserialization support in Syncfusion Essential Studio WPF Pivot Grid control, its elements and more.
platform: wpf
control: Pivot grid
 documentation: ug
---

# Serialization and Deserialization in WPF Pivot Grid

Serialization can be implemented for applications that need to save their data and structure after closed. Serialization supports saving the structure and data of pivot grid control to an XML file and it can be loaded at any time.

The following are the properties of pivot grid that can be serialized.


    <table>
        <tr>
            <th>
                Property Name</th>
            <th>
                Type</th>
        </tr>
        <tr>
            <td>
                AllowResizeColumns</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                AllowResizeRows</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                AllowSelection</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                AllowSelectionWithHeaders</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                AutoSizeColumnCount</td>
            <td>
                int</td>
        </tr>
        <tr>
            <td>
                AutoSizeOption</td>
            <td>
                GridAutoSizeOption</td>
        </tr>
        <tr>
            <td>
                AutoSizeRowCount</td>
            <td>
                int</td>
        </tr>
        <tr>
            <td>
                DeferLayoutUpdate</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                Filters</td>
            <td>{{ '`ObservableCollection(<FilterExpression>)`' | markdownify }}</td>
        </tr>
        <tr>
            <td>
                FreezeHeaders</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                IsDynamicData</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                PivotCalculations</td>
            <td>{{ '`ObservableCollection(<PivotComputationInfo>)`' | markdownify }}</td>
        </tr>
        <tr>
            <td>
                PivotColumns</td>
            <td>{{ '`ObservableCollection(<PivotItem>)`' | markdownify }}</td>
        </tr>
        <tr>
            <td>
                PivotFields</td>
            <td>{{ '`ObservableCollection(<PivotItem>)`' | markdownify }}</td>
        </tr>
        <tr>
            <td>
                PivotRows</td>
            <td>{{ '`ObservableCollection(<PivotItem>)`' | markdownify }}</td>
        </tr>
        <tr>
            <td>
                ShowCalculationsAsColumns</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                ShowFieldList</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                ShowGrandTotals</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                ShowGroupingBar</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                GroupingBar.AllowFiltering</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                GroupingBar.AllowSorting</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                EnableColumnHeader</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                EnableRowHeader</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                AllowMultiFunctionalSortFilter</td>
            <td>
                bool</td>
        </tr>
        <tr>
            <td>
                VisibleRecords</td>
            <td>
                int</td>
        </tr>
    </table>

## Using the serialization/deserialization in pivot grid

On serialization, the expand and collapse states of pivot grid cells are maintained. So when deserializing, the item source specified for the grid should be same as the item source used in serialization. This can be ignored by setting the `IgnoreExpandCollapseOnSerialization` property of pivot grid control to "False".

The following are the methods used in pivot grid for serialization/deserialization.

Methods table

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
    Serializes the pivot grid into an XML file format using the save file dialog.</td><td>
    -</td><td>
    void</td></tr>
    <tr>
    <td>
    Deserialize()</td><td>
    Deserialize the pivot grid from the saved XML file using the open file dialog.</td><td>
    -</td><td>
    void</td></tr>
    <tr>
    <td>
    Serialize(string fileName)</td><td>
    Serializes the pivot grid into an XML file format and saves it in the specified location.</td><td>
    string fileName</td><td>
    void</td></tr>
    <tr>
    <td>
    Deserialize(string filename)</td><td>
    Deserialize the pivot grid from the specified XML file.</td><td>
    string fileName</td><td>
    void</td></tr>
    <tr>
    <td>
    SerializedXmlString()</td><td>
    Serializes some specific properties of pivot grid control in string format.</td><td>
    -</td><td>
    string</td></tr>
    <tr>
    <td>
    Deserialize(string XmlString)</td><td>
    Deserialize the XML string format in the pivot grid control.</td><td>
    string XmlString</td><td>
    void</td></tr>
    </table>

### Serialization

After defining a pivot grid control, call the Serialize() method in the separate event handler. Refer to the following code snippet.

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

### Deserialization

After defining a pivot grid control, call the De-Serialize() method in the separate event handler. Refer to the following code snippet.

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

![Pivot grid serialized as xml string](Serialization-images/Serialized PivotGrid.png)
