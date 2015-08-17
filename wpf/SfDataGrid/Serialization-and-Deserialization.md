---
layout: post
title: Serialization-and-Deserialization
description: serialization and deserialization
platform: wpf
control: SfDataGrid
documentation: ug
---

# Serialization and Deserialization

The DataGrid control supports Serialization and Deserialization. The entire Grid setting can be serialized and deserialized at execute time. This section explains on how to serialize and deserialize DataGrid and how to customize serialization and deserialization process by using SerializationController. By customizing SerializationController, you can serialize and deserialize derived DataGrid and also customize column. 

### Overview

The DataGrid control includes following methods for Serialization and Deserialization.

_Methods Table_

<table>
<tr>
<td>
Method</td><td>
Overload</td><td>
Description</td></tr>
<tr>
<td>
Serialize</td><td>
Serialize(Stream stream)</td><td>
Serialize the datagrid and exports the DataGrid properties to given XML file.</td></tr>
<tr>
<td>
Serialize</td><td>
Serialize(Stream stream, SerializationOptions options)</td><td>
Serialize the datagrid and exports the DataGrid properties to given XML file based on the SerializationOptions </td></tr>
<tr>
<td>
Deserialize</td><td>
Deserialize(Stream stream)</td><td>
Reconstructs the DataGrid with the objects that are stored in the given XML file.</td></tr>
<tr>
<td>
Deserialize</td><td>
Deserialize(Stream stream, DeserializationOptions options)</td><td>
Reconstructs the DataGrid with the objects that are stored in the given XML file based on the DeserializationOptions </td></tr>
</table>


When you invoke the Serialize method, it exports the current DataGrid control properties to an XML file and the Deserialize method reconstructs the DataGrid control with the objects that are stored in the XML file.

The following code example illustrates on how to use Serialization and Deserialization in the DataGrid control using SerializationOptions and DeserializationOptions. SerializationOptions and DeserializationOptions are a class used to specify the options for customizing serialization and deserialization respectively. You can achieve this by clicking Serialize button and when the XML file is saved, reconstruct the DataGrid control by clicking the Deserialize button.


{% highlight xml %}

[XAML]

<Window.DataContext>

<local:ViewModel/>

</Window.DataContext>

<syncfusion:SfDataGrid x:Name="sfGrid" 

                         AllowDraggingColumns="True"

                         ColumnSizer="Star" 

                         NavigationMode="Row"

                         ItemsSource="{Binding EmployeeDetails}"

                         ShowGroupDropArea="True">

    <syncfusion:SfDataGrid.Columns>

        <syncfusion:GridTextColumn MappingName="EmployeeID" />

        <syncfusion:GridTextColumn HeaderText="Employee Name" 

        MappingName="Name" />

        <syncfusion:GridTextColumn MappingName="Gender" />

        <syncfusion:GridTextColumn HeaderText="Designation"

        MappingName="Title" MinimumWidth="240" />

        <syncfusion:GridTextColumn HeaderText="Marital Status" 

        MappingName="MaritalStatus" />

    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>

<StackPanel>

    <StackPanel>

        <TextBlock Margin="5" Text="Serialize the DataGrid" />

        <Button Width="150" x:Name="serializebtn" Margin="5"

        Click="OnSerializeDataGrid" Content="Serialize" />

    </StackPanel>

    <StackPanel>

        <TextBlock Margin="5" Text="Deserialize the DataGrid" />

        <Button Width="150" x:Name="deserializebtn" Margin="5"

        Click="OnDeserializeDataGrid" Content="Deserialize" />

    </StackPanel>

</StackPanel>
{% endhighlight %}

{% highlight C# %}

[C#]

Private void OnSerializeDataGrid(object sender, RoutedEventArgs args)

{

    var dataGrid = args.Source as SfDataGrid;

    if (dataGrid == null) return;

    try

    {

       using (var file = File.Create("DataGrid.xml"))

       {

           SerializationOptions options = new SerializationOptions();

           options.SerializeSorting = false;

           dataGrid.Serialize(file, options);

       }

    }

     catch (Exception)

     {                

     }

}

private async void OnDeserializeDataGrid(object sender, RoutedEventArgs args)

{

    var dataGrid = args.Source as SfDataGrid;

    if (dataGrid == null) return;

    try

    {

       using (var file = File.Open("DataGrid.xml", FileMode.Open))

       {

          DeserializationOptions options = new DeserializationOptions();

          options.DeserializeSorting = false;

          dataGrid.Deserialize(file, options);

       }

    }

    catch (Exception)

    {

    }

}

{% endhighlight %}

The following screenshot displays the output.



![](Features_images/Features_img196.png)



_DataGrid with Serialization and Deserialization_

### SerializationOptions and DeserializationOptions

To customize the serialization and deserialization process, you can use SerializationOptions and DeserializationOptions respectively. Following are the list of properties provided by these classes.

#### SerializationOptions

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td><td>
Default Value</td></tr>
<tr>
<td>
SerializeSorting</td><td>
Boolean</td><td>
Gets or sets the value that determines whether the method serialize datagrid’s SortColumnDescriptions</td><td>
True</td></tr>
<tr>
<td>
SerializeGrouping</td><td>
Boolean</td><td>
Gets or sets the value that determines whether the method serialize datagrid’s GroupColumnDescriptions</td><td>
True</td></tr>
<tr>
<td>
SerializeGroupSummaries</td><td>
Boolean</td><td>
Gets or sets the value that determines whether the method serialize GroupSummaryRows</td><td>
True</td></tr>
<tr>
<td>
SerializeCaptionSummary</td><td>
Boolean</td><td>
Gets or sets the value that determines whether the method serialize CaptionSummaryRow</td><td>
True</td></tr>
<tr>
<td>
SerializeTableSummaries</td><td>
Boolean</td><td>
Gets or sets the value that determines whether the method serialize TableSummaryRows</td><td>
True</td></tr>
<tr>
<td>
SerializeFiltering</td><td>
Boolean</td><td>
Gets or sets the value that determines whether the method serialize columns FilterPredicates</td><td>
True</td></tr>
<tr>
<td>
SerializeColumns</td><td>
Boolean</td><td>
Gets or sets the value that determines whether the method serialize grid Columns</td><td>
True</td></tr>
<tr>
<td>
SerializeStackedHeaders</td><td>
Boolean</td><td>
Gets or sets the value that determines whether the method serialize StackedHeaderRows</td><td>
True</td></tr>
</table>
DeserializationOptions

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td><td>
Default Value</td></tr>
<tr>
<td>
DeserializeSorting</td><td>
Boolean</td><td>
Gets or sets a value that determines whether the method deserialize datagrid’s SortColumnDescriptions</td><td>
True</td></tr>
<tr>
<td>
DeserializeGrouping</td><td>
Boolean</td><td>
Gets or sets a value that determines whether the method deserialize datagrid’s GroupColumnDescriptions</td><td>
True</td></tr>
<tr>
<td>
DeserializeGroupSummaries</td><td>
Boolean</td><td>
Gets or sets a value that determines whether the method deserialize GroupSummaryRows</td><td>
True</td></tr>
<tr>
<td>
DeserializeCaptionSummary</td><td>
Boolean</td><td>
Gets or sets a value that determines whether the method deserialize CaptionSummaryRow</td><td>
True</td></tr>
<tr>
<td>
DeserializeTableSummaries</td><td>
Boolean</td><td>
Gets or sets a value that determines whether the method deserialize TableSummaryRows</td><td>
True</td></tr>
<tr>
<td>
DeserializeFiltering</td><td>
Boolean</td><td>
Gets or sets a value that determines whether the method deserialize columns FilterPredicates</td><td>
True</td></tr>
<tr>
<td>
DeserializeColumns</td><td>
Boolean</td><td>
Gets or sets a value that determines whether the method deserialize grid Columns</td><td>
True</td></tr>
<tr>
<td>
DeserializeStackedHeaders</td><td>
Boolean</td><td>
Gets or sets a value that determines whether the method deserialize StackedHeaderRows</td><td>
True </td></tr>
</table>

#### Overriding SerializationController

SerializationController is a public class that handles serialization and deserialization operations in SfDataGrid. DataContractSerializer is used in SerializationController to perform serialization and deserialization.By overriding SerializationController, you can customize serialization and deserialization operations. SerializationController copies the SfDataGrid and its inner class properties to SerializableDataGrid (This class is serialized only using DataContractSerializer). Similarly SerializableDataGrid, GridColumn properties that are to be serialized is copied into SerializableGridColumn. Also GroupColumnDescriptions, SortColumnDescriptions, StackedHeaders and etc., is copied to its corresponding serializable classes.

SerializationController contains the following methods to perform serialization and deserialization operations.

_Methods table_

<table>
<tr>
<td>
Method </td><td>
Description</td></tr>
<tr>
<td>
public virtual void Serialize(Stream stream, SerializationOptions serializeOptions)</td><td>
Method used to serialize the SfDataGrid and exports its properties to given XML file.This method is useful while serializing derived data grid.</td></tr>
<tr>
<td>
protected virtual SerializableDataGrid StoreGridSettings(SerializationOptions serializeOptions)</td><td>
Called during serialization process to copy grid properties, sorting, filtering, grouping, etc.to SerializableDataGrid from SfDataGrid</td></tr>
<tr>
<td>
protected virtual void StoreGridProperties(SerializableDataGrid serializableDataGrid)</td><td>
Called during serialization process to copy grid properties to SerializableDataGrid.</td></tr>
<tr>
<td>
protected virtual SerializableDataGrid GetSerializableDataGrid()</td><td>
Called to get SfDataGrid instance while serializing grid. It is useful while serializing custom data grid. If you need to serialize the custom datagrid properties, you should add these properties to custom SerializableDataGrid class.</td></tr>
<tr>
<td>
protected virtual SerializableGridColumn GetSerializableGridColumn(GridColumn column)</td><td>
Called to get serializable grid column instance while serializing grid. It is useful while serializing custom column.</td></tr>
<tr>
<td>
protected virtual SerializableFilterSettings StoreFilterPredicates(SfDataGrid dataGrid)</td><td>
Called during serialization process to copy filter predicates to SerializableFilterSettings</td></tr>
<tr>
<td>
protected virtual void StoreGridColumnProperties(GridColumn column, SerializableGridColumn serializableColumn)</td><td>
Called during serialization process to copy grid column properties to SerializableGridColumn</td></tr>
<tr>
<td>
protected virtual SerializableColumns StoreGridColumns(SfDataGrid dataGrid)</td><td>
Called during serialization process to copy grid columns to SerializableColumns</td></tr>
<tr>
<td>
protected virtual SerializableStackedHeaderRow StoreGridStackedHeaderRow(StackedHeaderRow stackedHeaderRow)</td><td>
Called during serialization process to copy grid stacked header row to SerializableStackedHeaderRow.</td></tr>
<tr>
<td>
protected virtual SerializableGridSummaryRow StoreGridSummaryRow(GridSummaryRow gridSummaryRow)</td><td>
Called during serialization process to copy grid summary row from SfDataGrid to SerializableGridSummaryRow</td></tr>
<tr>
<td>
protected virtual SerializableGroupColumnDescriptions StoreGroupColumnDescriptions(SfDataGrid dataGrid)</td><td>
Called during serialization process to copy group column descriptions from SfDataGrid to SerializableGroupColumnDescriptions</td></tr>
<tr>
<td>
protected virtual SerializableSortColumnDescriptions StoreSortColumnDescriptions(SfDataGrid dataGrid)</td><td>
Called during serialization process to copy sort column descriptions to SerializableSortColumnDescriptions.</td></tr>
<tr>
<td>
public virtual void Deserialize(Stream stream, DeserializationOptions deserializeOptions)</td><td>
Method used to deserialize the SfDataGrid. It reconstructs the DataGrid with the objects that are stored in the given XML file.This method is useful while deserializing derived data grid.</td></tr>
<tr>
<td>
protected virtual void ReloadGrid(SerializableDataGrid dataGrid, DeserializationOptions deserializationOptions)</td><td>
Called during deserialization process to restore grid properties from SerializableDataGrid  and reload the grid</td></tr>
<tr>
<td>
protected virtual void UnWireSerializablePropertyEvents()</td><td>
Called during serialization process to unwire SortColumnDescriptions, GroupColumnDescriptions collection changed, etc. event</td></tr>
<tr>
<td>
protected virtual void RestoreGridSettings(SerializableDataGrid serializableDataGrid, SfDataGrid dataGrid, DeserializationOptions options)</td><td>
Called during deserialization process to restore grid properties, sorting, filtering, grouping, etc. from SerializableDataGrid</td></tr>
<tr>
<td>
protected virtual void RestoreGridProperties(SerializableDataGrid serializableDataGrid)</td><td>
Called during deserialization process to copy grid properties from SerializableDataGrid</td></tr>
<tr>
<td>
protected virtual void RestoreGridColumns(SerializableDataGrid serializableDataGrid)</td><td>
Called during deserialization process to copy grid columns from SerializableDataGrid</td></tr>
<tr>
<td>
protected virtual GridColumn GetGridColumn(SerializableGridColumn serializableColumn)</td><td>
Called to get GridColumn instance while deserializing grid. It is useful while deserializing custom column. The returned grid column is added to datagrid columns collection while deserializing.</td></tr>
<tr>
<td>
protected virtual void RestoreColumnProperties(SerializableGridColumn serializableColumn, GridColumn column)</td><td>
Called during deserialization process to copy grid column properties from SerializableGridColumn</td></tr>
<tr>
<td>
protected virtual void RestoreFilterPredicates(SerializableDataGrid serializableDataGrid)</td><td>
Called during deserialization process to copy filter predicates from SerializableDataGrid</td></tr>
<tr>
<td>
protected virtual StackedHeaderRow RestoreGridStackedHeaderRow(SerializableStackedHeaderRow serializableStackedHeaderRow)</td><td>
Called during deserialization process to restore grid stacked header row from SerializableStackedHeaderRow</td></tr>
<tr>
<td>
protected virtual GridSummaryRow RestoreGridSummaryRow(SerializableGridSummaryRow serializableGridSummaryRow)</td><td>
Called during deserialization process to restore grid summary row from SerializableGridSummaryRow</td></tr>
<tr>
<td>
protected virtual void RestoreGroupColumnDescriptions(SerializableDataGrid serializableDataGrid)</td><td>
Called during deserialization process to restore group column descriptions from SerializableDataGrid</td></tr>
<tr>
<td>
protected virtual void RestoreSortColumnDescriptions(SerializableDataGrid serializableDataGrid)</td><td>
Called during deserialization process to restore sort column descriptions from SerializableDataGrid</td></tr>
<tr>
<td>
protected virtual void WireSerializablePropertyEvents()</td><td>
Called during Deserialization process to wire SortColumnDescriptions, GroupColumnDescriptions collection changed, etc. event</td></tr>
<tr>
<td>
public virtual Type[] KnownTypes()</td><td>
Called during serialization and deserialization operations. It is useful while using custom columns. If you want to serialize the columns, its types should be returned as a list</td></tr>
<tr>
<td>
public virtual void Dispose()</td><td>
Method used to dispose SerializationController</td></tr>
</table>

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td><td>
Default Value</td></tr>
<tr>
<td>
Datagrid</td><td>
SfDataGrid</td><td>
Gets the SfDataGrid instance to copy properties from/to SerializableDataGrid</td><td>
Null</td></tr>
</table>

The following code example illustrates to override methods and how to handle operations in SerializationController. SerializationControllerExt class is derived from SerializationController and you can assign this to existing SerializationController. SerializationControllerExt overrides existing one.


{% highlight C# %}

[C#]

// Assign custom serialization controller to datagrid SerializationController

this.dataGrid.SerializationController = new SerializationControllerExt(this.dataGrid);





/// <summary>

/// SerializationControllerExt class is the custom SerializationController

/// </summary>



public class SerializationControllerExt : SerializationController

{ 

   public SerializationControllerExt(SfDataGrid grid)

            : base(grid)

   {

   }



        /// <summary>

        /// Store grid settings - properties, columns,   sortdescriptions,groupdescriptions, stacked headers, filter predicates, summaries

        /// </summary>

        /// <param name="serializeOptions">options for serializing grid</param>

        /// <returns>SerializableDataGrid</returns>

    protected override SerializableDataGrid StoreGridSettings(SerializationOptions         serializeOptions)

        {

            return base.StoreGridSettings(serializeOptions);

        }



        /// <summary>

        /// Restore grid properties,columns,sortdescriptons,groupdescriptions,filter predicates,stacked headers,summaries

        /// </summary>

        /// <param name="serializableDataGrid">serializableDataGrid instance</param>

        /// <param name="dataGrid">SfDataGrid</param>

        /// <param name="options">DeserializationOptions</param>



        protected override void RestoreGridSettings(SerializableDataGrid  serializableDataGrid, SfDataGrid dataGrid, DeserializationOptions options)

        {

            base.RestoreGridSettings(serializableDataGrid, dataGrid, options);

        }

    }
{% endhighlight %}

### How To

#### How to retain new columns when you deserialize SfDataGrid?

By default, the columns that exist in the grid when you apply serialization alone are displayed after deserializing the grid. When you want to preserve the columns that currently exist in the grid while applying deserialization, but not in the layout while serialization, customize SerializationController to achieve this. The following code example illustrates how to customize SerializationController.


{% highlight xml %}

[XAML]

<syncfusion:SfDataGrid Name="dataGrid"     Grid.Column="0"

                                           AllowDraggingColumns="True"

                                           AllowFiltering="True"

                                           AutoGenerateColumns="False"

                                           ColumnSizer="Star"

                                           ItemsSource="{Binding ProductInfo}"

                                           NavigationMode="Row"

                                           ShowGroupDropArea="True">



                        <syncfusion:SfDataGrid.Columns>

                            <syncfusion:GridTextColumn HeaderText="Product ID"   MappingName="ProductID" />

                            <syncfusion:GridTextColumn HeaderText="Product Name" MappingName="ProductName" />

                            <syncfusion:GridTextColumn HeaderText="Quantity Per Unit" MappingName="QuantityPerUnit" />

                            <syncfusion:GridTextColumn HeaderText="Price"

                                                       MappingName="UnitPrice"

                                                       TextAlignment="Right" />

                            <syncfusion:GridTextColumn HeaderText="Units In Stock" MappingName="UnitsInStock" />

                        </syncfusion:SfDataGrid.Columns>

{% endhighlight %}

After serialization, when new column is added to grid, it is not displayed during deserialization. 


{% highlight C# %}

[C#]

// To add new unbound column at run time

dataGrid.Columns.Add(new GridUnBoundColumn() { MappingName = "UnboundColumn", Expression = "2 * UnitPrice" });
{% endhighlight %}

The following screenshot illustrates the grid after deserialization.



![](Features_images/Features_img197.png)



_DataGrid after Serialization and Deserialization_

You can overcome the above scenario by customizing the SerilalizationController and refer to the following code example that illustrates how to preserve the new unbound column during deserialization.


{% highlight C# %}

[C#]

// Assigning custom serialization controller to datagrid SerializationController

dataGrid.SerializationController = new SerializationControllerExt(dataGrid);



    /// <summary>

    /// SerializationControllerExt class is the custom SerializationController

    /// </summary>

    public class SerializationControllerExt : SerializationController

    {

        public SerializationControllerExt(SfDataGrid dataGrid)

            : base(dataGrid)

        {



        }

        /// <summary>

        /// Restore grid columns from serializableDataGrid

        /// </summary>

        /// <param name="serializableDataGrid"></param>



        protected override void RestoreGridColumns(SerializableDataGrid serializableDataGrid)

        {

            foreach (var serializableColumn in serializableDataGrid.Columns)

            {

                var column = GetGridColumn(serializableColumn);

                RestoreColumnProperties(serializableColumn, column);

                if (!this.Datagrid.Columns.Any(x =>  x.MappingName.Equals(column.MappingName)))

                    this.Datagrid.Columns.Add(column);

            }

        }

    }
{% endhighlight %}


The following screenshot illustrates the output image after deserializing grid using custom serialization controller.

![](Features_images/Features_img198.png)


_DataGrid after Serialization and Deserialization using custom serialization controller_

#### How to serialize custom column in SfDataGrid

By default, the grid columns are serialized during serialization of DataGrid. But when custom column is added in grid, it is not serialized. Since DataContractSerializer is used the custom column type has to be identified to serialize and deserialize the custom column. To serialize the custom column, you can override SerializationController. Refer to the following code example.


{% highlight C# %}

[C#]

  public class DatePickerColumn : GridColumn

    {

        public static readonly DependencyProperty DateMappingNameProperty = DependencyProperty.Register("DateMappingName",

    typeof(string), typeof(DatePickerColumn));

        public DatePickerColumn()

        {

            SetCellType("DatePickerRenderer");

        }

        public string DateMappingName

        {

            get { return (string)GetValue(DateMappingNameProperty); }

            set { SetValue(DateMappingNameProperty, value); }

        }

        protected override Freezable CreateInstanceCore()

        {

            return new DatePickerColumn();

        }

    }

{% endhighlight %}

Consider, the grid contains the following columns. Here DatePickerColumn is custom column.	


{% highlight xml %}

[XAML]

<Syncfusion:SfDataGrid x:Name="_dataGrid"

                               AutoGenerateColumns="False"

                               ColumnSizer="Star"                              

                               ItemsSource="{Binding Path=DataItems}>

            <Syncfusion:SfDataGrid.Columns>



                <Syncfusion:GridTextColumn AllowEditing="True" MappingName="ItemNumber"/>

                <demo:DatePickerColumn AllowEditing="True"

                                       DateMappingName="Date"

                                       HeaderText="DatePickerColumn"

                                       MappingName="Date" />

            </Syncfusion:SfDataGrid.Columns>

</Syncfusion:SfDataGrid>
{% endhighlight %}


During grid serialization, when you want to copy DatePickerColumn properties, you can create the SerializableCustomGridColumn (derived from SerializableGridColumn) class containing the properties as follows.


{% highlight C# %}

[C#]

[DataContract(Name="SerializableCustomGridColumn")]

public class SerializableCustomGridColumn : SerializableGridColumn

{

    [DataMember]

    public string DateMappingName { get; set; }

}

{% endhighlight %}

The following code illustrates how to override SerializationController to serialize custom column.


{% highlight C# %}

[C#]

// Assigning custom serialization controller to datagrid SerializationController

dataGrid.SerializationController = new SerializationControllerExt(dataGrid);



   /// <summary>

   /// SerializationControllerExt class is the custom SerializationController

   /// </summary>

public class SerializationControllerExt : SerializationController

{

        public SerializationControllerExt(SfDataGrid dataGrid)

            : base(dataGrid)

        {

        }

       /// <summary>

        /// Get grid column instance for deserialization

        /// </summary>

        /// <param name="serializableColumn">serializableColumn</param>

        /// <returns>GridColumn</returns>

        protected override GridColumn GetGridColumn(SerializableGridColumn serializableColumn)

        {

            if (serializableColumn is SerializableCustomGridColumn)

                return new DatePickerColumn();

            return base.GetGridColumn(serializableColumn);

        }



        /// <summary>

        /// Get serializable grid column instance

        /// </summary>

        /// <param name="column">grid column</param>

        /// <returns>SerializableGridColumn</returns>



        protected override SerializableGridColumn GetSerializableGridColumn(GridColumn column)

        {

            if (column.MappingName == "Date")

            {

                return new SerializableCustomGridColumn();

            }

            return base.GetSerializableGridColumn(column);

        }





        /// <summary>

        /// Store Grid Column Properties to serializable grid column

        /// </summary>

        /// <param name="column">grid column</param>

        /// <param name="serializableColumn">serializableColumn</param>



        protected override void StoreGridColumnProperties(GridColumn column, SerializableGridColumn serializableColumn)

        {

            base.StoreGridColumnProperties(column, serializableColumn);

            if (column is DatePickerColumn)

                (serializableColumn as SerializableCustomGridColumn).DateMappingName = (column as DatePickerColumn).DateMappingName;

        }



        /// <summary>

        /// Restore grid column properties from SerializableGridColumn

        /// </summary>

        /// <param name="serializableColumn">serializableColumn</param>

        /// <param name="column">grid column</param>

        protected override void RestoreColumnProperties(SerializableGridColumn serializableColumn, GridColumn column)

        {

            base.RestoreColumnProperties(serializableColumn, column);

            if (column is DatePickerColumn)

                (column as DatePickerColumn).DateMappingName = (serializableColumn as SerializableCustomGridColumn).DateMappingName;

        }

        /// <summary>

        /// Get known types of serializable columns for serialization and deserialization

        /// </summary>

        /// <returns></returns>

        public override Type[] KnownTypes()

        {

            var types = base.KnownTypes();

            var list = types.Cast<Type>().ToList();

            list.Add(typeof(SerializableCustomGridColumn));

            return list.ToArray();

        }

}
{% endhighlight %}
