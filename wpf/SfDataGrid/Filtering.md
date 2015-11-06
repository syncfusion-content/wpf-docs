---
layout: post
title: Filtering | SfDataGrid | WPF | Syncfusion
description: filtering
platform: wpf
control: SfDataGrid
documentation: ug
---

# Filtering

This section explains you about Filtering and how to filter records programmatically or using UI. Different approaches to filter records in both the methods, properties, methods and events that participate in filtering are discussed in this section.

## Overview

The SfDataGrid control allows you to filter data based on your own criteria. Filtering helps to view certain subset of the ItemsSource collection that meets a given Filtering criteria. Filtering is done in two ways:

* Advanced Filtering
* Programmatic Filtering

## Advanced Filtering 


This section explains you how to apply Filtering on records using UI. UI Filtering is one way of Filtering the data in a Grid. This allows you to easily filter data from multiple columns with enriched UI interactions that resembles the filter drop-down lists in Excel. 

Grid supports the following two types of UI filtering. 

1. Checkbox Filter
2. Advanced Filter

### GridFilterPopupControl structure

The following highlighted one is CheckBoxFiltering.



![](Features_images/Features_img103.png)


### CheckBox Filtering

The following screenshot displays you the control structure of TextFilters in Excel-Like filtering. When you set cangenerateuniqueitems to ‘true’, you can get Filter value combobox instead of TextBox.

![](Features_images/Features_img104.png)



Control structure of Text Filters
{:.caption}
### Enable UI Filtering 

To access UI Filtering, you can enable it. UI Filtering is enabled or disabled by setting the AllowFiltering property that applies in both SfDataGrid and GridColumn. 



{% highlight xml %}

 



<syncfusion:SfDataGrid x:Name="syncgrid"

                       AllowFiltering="{Binding IsChecked,

                                            ElementName=ckbAllowFilters}"

                       AutoGenerateColumns="False"

                       ColumnSizer="Star"

                       ItemsSource="{Binding EmployeeDetails}"

                       LiveDataUpdateMode="AllowDataShaping"

                       NavigationMode="Row">

    <syncfusion:SfDataGrid.Columns>

        <syncfusion:GridTextColumn AllowBlankFilters="{Binding ElementName=ckbAllowBlankFiltersOrderID,

                                                            Mode=TwoWay,

                                                            Path=IsChecked}"

                                   AllowFiltering="{Binding ElementName=ckbAllowFilterOrderID,

                                                        Mode=TwoWay,

                                                        Path=IsChecked}"

                                   ImmediateUpdateColumnFilter="{Binding IsChecked,

                                                                        Mode=TwoWay,

                                                                        ElementName=ckbImmediateUpdateColumnFilterOrderID}"

                                   MappingName="OrderID"

                                   TextAlignment="Right" />



        <syncfusion:GridTextColumn MappingName="CustomerID" />



        <syncfusion:GridTextColumn AllowBlankFilters="{Binding ElementName=ckbAllowBlankFiltersShipPostalCode,

                                                            Mode=TwoWay,

                                                            Path=IsChecked}"

                                   AllowFiltering="{Binding ElementName=ckbAllowFilterShipPostalCode,

                                                        Mode=TwoWay,

                                                        Path=IsChecked}"

                                   HeaderText="Ship PostalCode"

                                   ImmediateUpdateColumnFilter="{Binding IsChecked,

                                                                        Mode=TwoWay,

                                                                        ElementName=ckbImmediateUpdateColumnFilterShipPostalCode}"

                                   MappingName="ShipPostalCode" />



        <syncfusion:GridTextColumn DisplayBinding="{Binding Path=OrderDate,

                                                        StringFormat=d}"

                                   HeaderText="Order Date"

                                   MappingName="OrderDate"

                                   TextAlignment="Right" />



        <syncfusion:GridTextColumn AllowBlankFilters="{Binding ElementName=ckbAllowBlankFiltersShippedDate,

                                                            Mode=TwoWay,

                                                            Path=IsChecked}"

                                   AllowFiltering="{Binding ElementName=ckbAllowFilterShippedDate,

                                                        Mode=TwoWay,

                                                        Path=IsChecked}"

                                   DisplayBinding="{Binding Path=ShippedDate,

                                                        StringFormat=d}"

                                   HeaderText="Shipped Date"

                                   ImmediateUpdateColumnFilter="{Binding IsChecked,

                                                                        Mode=TwoWay,

                                                                        ElementName=ckbImmediateUpdateColumnFilterShippedDate}"

                                   MappingName="ShippedDate"

                                   TextAlignment="Right" />



        <syncfusion:GridTextColumn DisplayBinding="{Binding Path=Freight,

                                                        StringFormat='{}{0:c}'}"

                                   MappingName="Freight"

                                   TextAlignment="Right" />

    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>

{% endhighlight %}



The following image displays a funnel icon in the header of the Grid. On clicking the filter icon, an Excel-like filter drop-down list opens and you can filter the data.

![](Features_images/Features_img105.png)



DataGrid with enabled UI Filtering
{:.caption}
You can achieve it using code behind also. By simply setting AllowFiltering to’ true’.


{% highlight C# %}



syncgrid.AllowFiltering = true;
{% endhighlight %}


N> A column’s AllowFiltering is given more priority than the SfDataGrid control.

#### Filter Mode

In UI Based Filtering, it has different modes to filter records. This section explains you different modes in GridFilterControl. FilterMode property allows you to specify the filter options for GridFilterControl. The filter modes are

* CheckboxFilter -- Only CheckboxFilter is loaded in the filter popup.
* AdvancedFilter – Only Advanced Filter is loaded in the filter popup.
* Both - Both AdvancedFilter and CheckboxFilter are loaded while opening the filter pop-up. You can switch between AdvancedFilter and Checkboxfilter.

By default, FilterMode is set to Both.By setting the FilterMode property as CheckboxFilter in GridFilterControl style; you can disable the Advancedfiltering option. 

The following code example shows how to disable the advanced filtering option.


{% highlight xml %}

 



<Style TargetType="syncfusion:GridFilterControl">

    <Setter Property="FilterMode" Value="CheckBoxFilter" />

</Style>
{% endhighlight %}


By setting the FilterMode property as AdvancedFilter in the GridFilterControl style, you can disable the Checkboxfiltering option.

This filter allows you to filter the data by selecting one or more items using checkbox as shown in the following screenshot.(CheckBoxFilter).



![](Features_images/Features_img106.png)

DataGrid with Filter mode
{:.caption}
It allows you to filter the data based on some conditions as shown in the following screenshot. (AdvancedFilter).



![](Features_images/Features_img107.png)



DataGrid with Advanced filter
{:.caption}
Advanced filter type is automatically detected based on underlying date type .There are three types of Advanced filtering.

1. Text Filters
2. Number Filters
3. Date Filters

### Text Filters

When the string value is bounded to the GridColumn or the items source is dynamic, then TextFilters are loaded in AdvancedFilterControl. Also when the column is unbound or mask column, TextFilters are loaded. 

The following filter types are available for Text Filters.

1. Equals - Checks the records that are equal to the filter value.
2. NotEquals - Checks the records that are not equal to the filter value.
3. BeginsWith - Checks the records that begin with the filter value.
4. EndsWith - Checks the records that end with the filter value.
5. Contains - Checks the records that contain the filter value.
6. Empty - Checks for records with empty values.
7. NotEmpty - Checks for records that are not empty.
8. Null - Checks the records for null values.
9. NotNull - Checks the records with no null values.



N> When CanGenerateUniqueItems is set to ‘True’, the FilterValue combobox is not editable. Therefore, BeginsWith, EndsWith and Contains are unavailable. These options are available only when CanGenerateUniqueItems is set to ‘False’. So, when you use DataTable as items Source, AdVanceFiltering does not support CaseSensitive.

When integer, double, short, decimal, byte or long, Nullable and unsigned types are bound to the GridColumn then Number Filters are loaded in the AdvancedFilterControl.

The following filter types are available for Number Filters.

1. Equals
2. NotEquals
3. Less Than
4. Less Than or Equal
5. Greater Than 
6. Greater Than or Equal
7. Null
8. NotNull

### Date Filters

When the date value is bounded to the GridColumn, Date Filters are loaded in the AdvancedFilterControl.

The following filter types are available for Date Filters.

1. Equals
2. NotEquals
3. Before
4. Before Or Equal
5. After
6. After Or Equal
7. Null
8. NotNull

By setting the FilterBehavior as StringTyped, you can load the Text Filters to the particular column. When you set the FilterBehavior to StronglyTyped, then filter type is automatically detected based on underlying data type.

N> Null and NotNull options are available only when AllowBlankFilter is set to ‘True’

### Blank Filters

AllowBlankFilters propertyallows you to enable or disable the visibility of null values in the filter element list. Blank text is shown for the null values when it is enabled and the null values are not taken into consideration when it is disabled.


{% highlight xml %}

 



<syncfusion:GridTextColumn AllowBlankFilters="True"

                           AllowFiltering="True"

                           HeaderText="Ship PostalCode"

                           MappingName="ShipPostalCode" />
{% endhighlight %}




By default, AllowBlankFilter is set to ‘True’, so the null values are included in the filter list elements as blanks.



![](Features_images/Features_img108.png)



DataGrid with Blank Filter
{:.caption}


### Immediate Filtering

ImmediateUpdateColumnFilter enables or disables the immediate update of the column filters. When selecting or clearing the check box in the filter element list view using CheckboxFilter, the filter is updated immediately. In AdavncedFilter type, the column filters are updated when Filter type combo box or filter value or radio button state is changed. In this case, the OK and Cancel buttons are unavailable and the Select All option is not reflected in the filter updates.


{% highlight xml %}

 



<syncfusion:GridTextColumn AllowBlankFilters="True"

                           AllowFiltering="True"

                           HeaderText="Ship PostalCode"

                           ImmediateUpdateColumnFilter="True"

                           MappingName="ShipPostalCode" />

{% endhighlight %}



![](Features_images/Features_img109.png)



DataGrid with Immediate Filtering
{:.caption}
### Events

This topic describes you the events that participates in filtering. The SfDataGrid control provides the following events while filtering: 

* FilterChanging: This eventoccurswhile applying Filters to a particular column. The event argument of this event handler GridFilterEventArgs has the following properties associated with the FilterChanging event:
* FilterPredicate: Provides information about the Filter predicates.
* Column: Provides information about the column.
* Handled: You can use this argument to stop the filtering.

You can use this event to change the FilterPredicates, FilterType, and FilterBehaviour while applying Filter.

* FilterChanged: This event is raised after the Filter is applied. The event argument of this event handler, GridFilterEventArgs has the following properties associated with the FilterChanged event:
* FilterPredicate: Provides information about the Filter predicates.
* Column: Provides information about the column.
* Handled: Provides information about how the filtering is handled.
* FilterItemsPopulating: This event is raised while the filter list item is populated and the ItemSource of the GridFilterControl is set. Its argument, FilterItemsPopulatingArgs has the following properties associated with the FilterItemsPopulating event:
* ItemSource: Allows you to manually specify filter values.
* Column: Provides information about the column.
* FilterControl: You can access the control and change its properties.
* Handled: You can skip the population of list items for the GridFilterControl by using handled property. The FilterItemsPopulated event is not invoked when Handled property is set to ‘true’.

You can change the AdvancedFilterType for particular column based on underlying data source. For example, when you use GridTextColumn for numeric values, you can filter it based on NumberFilter. You can achieve it by FilterItemsPopulating event. You can use SetColumnDataType to set type of source you need to filter. It’s for validation purpose. When you use FilterControl to change its properties like – AdvancedFilterType, ColumnDataType, you need to specify the property value AscendingSortString for sorting purpose.

* FilterItemsPopulated: This event is raised after the filter list items are populated. The event argument of this event handler, FilterItemsPopulatedArgs has the following properties associated with the FilterItemsPopulated event:
* ItemSource: Allows you to manually specify Filter values.
* Column: Gives information about the column.
* FilterControl: Can access the control and change its properties.

The following code example illustrates to hook event. 


{% highlight C# %}





syncgrid.FilterChanging += syncgrid_FilterChanging;

syncgrid.FilterItemsPopulating += syncgrid_FilterItemsPopulating;

…



void syncgrid_FilterChanging(object sender, GridFilterEventArgs e)

{

    e.FilterPredicates.Add(new Syncfusion.Data.FilterPredicate() { FilterBehavior = Syncfusion.Data.FilterBehavior.StronglyTyped, FilterType = Syncfusion.Data.FilterType.Equals, PredicateType = Syncfusion.Data.PredicateType.Or, FilterValue = 10001 });

}



void syncgrid_FilterItemsPopulating(object sender, GridFilterItemsPopulatingEventArgs e)

{

    if(e.Column.MappingName == "OrderID")

    e.FilterControl.AdvancedFilterType = AdvancedFilterType.TextFilter;

    e.FilterControl.SetColumnDataType(typeof(string));

    e.FilterControl.AscendingSortString = GridResourceWrapper.SortNumberAscending;

}

{% endhighlight %}

###  GridFilter Popup Customization

The Grid UI Filter is derived from a content control and has its own structure. This structure is customized using the following APIs provided in the SfDataGrid and GridColumn controls. 

* SfDataGrid.FilterPopupStyle: Determines the style for the filter pop-up.
* SfDataGrid.FilterPopupTemplate: Determines the template for the filter pop-up.

These APIs discussed above, changes the appearance for the entire column filters in the SfDataGrid control. When you need to change the appearance of the GridFilterControl for a particular column, the following column-level properties are used. 

* GridColumn.FilterPopupStyle: Determines the style for the filter pop-up of the corresponding column.
* GridColumn.FilterPopupTemplate: Determines the template for the filter pop-up of the corresponding column.

The GridFilterControl has its own properties for its core functionality as follows

GridFilterControl property table

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
AscendingSortString</td><td>
string</td><td>
Gets the string for the ascending Sort button’s content.</td></tr>
<tr>
<td>
DescendingSortString</td><td>
string </td><td>
Gets the string for the descending Sort button’s content.</td></tr>
<tr>
<td>
SortOptionVisibility</td><td>
Visibility</td><td>
Shows or hides the sorting options in the GridFilterControl.</td></tr>
<tr>
<td>
AllowBlankFilters</td><td>
Boolean</td><td>
Enables or disables the null values that are displayed as blanks in filters.</td></tr>
<tr>
<td>
ImmediateUpdateColumnFilter </td><td>
Boolean</td><td>
Enables or disables the filter to perform immediate update based on the selection of the check box in the GridFilterControl.</td></tr>
<tr>
<td>
CheckboxFilterStyle</td><td>
Style</td><td>
Gets or sets the style for the CheckboxFilterControl</td></tr>
<tr>
<td>
AdvancedFilterStyle</td><td>
Style</td><td>
Gets or sets the style for the AdvancedFilterControl.</td></tr>
<tr>
<td>
IsOpen</td><td>
Boolean</td><td>
Gets or sets the IsOpen state of the GridFilterControl.</td></tr>
<tr>
<td>
FilterMode</td><td>
FilterMode</td><td>
Gets or sets the FilterMode of the GridFilterControl</td></tr>
<tr>
<td>
FilteredFrom</td><td>
FilteredFrom</td><td>
Decides whether the filtering is done using CheckboxFilter or AdvancedFilter</td></tr>
</table>


The Filter pop-up is customized with the properties provided in the SfDataGrid control and in the GridColumn as explained in previous sections. 

It is customized using the properties provided in the GridFilterControl. The following code example illustrates this. You can write style for GridFilterControl and bind it to FilterPopupStyle property.



{% highlight xml %}





<Style TargetType="syncfusion:GridFilterControl">

    <Setter Property="SortOptionVisibility" Value="Collapsed" />

</Style>



<syncfusion:GridTextColumn AllowBlankFilters="{Binding ElementName=ckbAllowBlankFiltersOrderID,

                                                       Mode=TwoWay,

                                                       Path=IsChecked}"

                           AllowFiltering="{Binding ElementName=ckbAllowFilterOrderID,

                                                    Mode=TwoWay,

                                                    Path=IsChecked}"

                           FilterPopupStyle="{StaticResource style}"

                           ImmediateUpdateColumnFilter="{Binding IsChecked,

                                                                 Mode=TwoWay,                                                                 ElementName=ckbImmediateUpdateColumnFilterOrderID}"

                           MappingName="OrderID"

                           TextAlignment="Right" />


{% endhighlight %}


This code collapses the sorting options in the GridFilterControl as shown in the following screenshot.

![](Features_images/Features_img110.png)



Sorting options collapsed in GridFilterControl
{:.caption}
GridFilterControl has DBNullString static property that displays some value instead of null; you can assign that value to DBNullString.

### CanGenerateUniqueItems

Using CanGenerateUniqueItems property, you can customize the AdvancedFilterControl.

When this property is set to ‘True’, then all the unique items in the column are loaded in the AdvancedFilterComboBox that allows you to select the value easily from the combo box and filter it. 

When the property is set to ‘False’, then a textbox is loaded instead of AdvancedFilterComboBox that allows you to manually enter text for filtering. Setting the property to ‘False’, shows a considerable increase in GridFilterControl’s loading performance.

The following code example shows how to set the CanGenerateUniqueItems property.



{% highlight xml %}





<Style TargetType="syncfusion:AdvancedFilterControl">

    <Setter Property="CanGenerateUniqueItems" Value="False" />

</Style>

{% endhighlight %}


![](Features_images/Features_img111.png)



DataGrid with CanGenerateUniqueItems property
{:.caption}
N> You can bind written style to FilterPopupStyle where you need to apply style. It’s in SfDataGrid and also in each column.

## Programmatic Filtering

This section explains you how to perform filtering on data programmatically. Programmatic Filtering allows you to set a predicate that performs the filtering functionality. The SfDataGrid control allows you to filter programmatically in two ways:

* Through Column Filter
* Through View Predicate

### Column Filtering

Column-level Filtering is achieved by adding filter predicates to the Grid Column. FilterPredicates is the property used to add the predicates to the column. The collection change of FilterPredicates applies the filter to the SfDataGrid control.

FilterPredicate has the following properties.

FilterPredicate Property table

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Descriptions</th></tr>
<tr>
<td>
FilterBehavior</td><td>
FilterBehavior</td><td>
Determines the filter behavior of the predicate.</td></tr>
<tr>
<td>
FilterType</td><td>
FilterType</td><td>
Determines the type of filter to be applied for the predicate.</td></tr>
<tr>
<td>
FilterValue</td><td>
Object</td><td>
Determines the filter value to be applied for the predicate.</td></tr>
<tr>
<td>
IsCaseSensitive</td><td>
Boolean</td><td>
Determines whether the predicate to be applied with the filter value is case sensitive or not.</td></tr>
<tr>
<td>
PredicateType</td><td>
PredicateType</td><td>
Determines the relations of multiple predicates and whether they are applied with OR / AND or not</td></tr>
</table>


### Filter Behavior

* StringTyped: Records are filtered without considering the type and it takes all the types as string.
* StronglyTyped: Records are filtered according to the underlying type.

### Filter Type

* Contains: Checks the records that contain the filter value.
* EndsWith: Checks the records that end with the filter value.
* Equals: Checks the records that are equal to the filter value.
* GreaterThan: Checks the records that are greater than the filter value.
* GreaterThanOrEqual: Checks the records that are greater than or equal to the filter value.
* LessThan: Checks the records that are lesser than the filter value. 
* LessThanOrEqual: Checks the records that are lesser than or equal to the filter value.
* NotEquals: Checks the records that are not equal to the filter value.
* StartsWith: Checks the records that start with the filter value.
* Between: Checks the records that have values between the filter values.

### Predicate Type

* AND: Applies AND operator between the predicates.
* OR: Applies OR operator between the predicates. 

#### Examples

The following code example illustrates how the EmployeeId column is filtered for an employee with an employee ID as ‘4’. 


{% highlight C# %}





// A custom filter method is assigned when you click the filter button.

void FilterBtn_Click(object sender, RoutedEventArgs e)

{ 

this.datagrid.Columns["EmployeeID"].FilterPredicates.Add(new FilterPredicate() {FilterType = FilterType.Equals, FilterValue = 1001,

PredicateType = PredicateType.Or });

}
{% endhighlight %}


The following screenshot displays the output when the filter is applied:



![](Features_images/Features_img112.png)



Filtered EmployeeId column
{:.caption}
As an example of multi-column filtering, the following code example illustrates how to filter the data for employees whose titles are equal to Tool Designer or Marketing Manager and whose gender is male. 


{% highlight C# %}





//A custom filter method is assigned when the filter button is clicked.

void FilterBtn_Click(object sender, RoutedEventArgs e)

{ 

      this.datagrid.Columns["Gender"].FilterPredicates.Add(new FilterPredicate() { FilterType = FilterType.Equals, FilterValue = "Male", PredicateType = PredicateType.And });

            this.datagrid.Columns["Title"].FilterPredicates.Add(new FilterPredicate() { FilterType = FilterType.Equals, FilterValue = "Tool Designer", PredicateType = PredicateType.Or });

            this.datagrid.Columns["Title"].FilterPredicates.Add(new FilterPredicate() { FilterType = FilterType.Equals, FilterValue = "Marketing Manager", PredicateType = PredicateType.Or });

}

{% endhighlight %}



The following screenshot displays the list of male employees with title as Marketing Manager or Tools designer. 

![](Features_images/Features_img113.png)


DataGrid with filtered details of Employees
{:.caption}
### Clear Filtering

The SfDataGrid control allows you to clear the Filter by clearing the filter predicates. This is achieved by invoking any one of the following methods:

* SfDataGrid.ClearFilters: Clears filters for all the columns.
* SfDataGrid.ClearFilter(String columnName): Clears the filter for that particular column that has the columnName as MappingName.
* SfDataGrid.ClearFilter(GridColumn column): Clears the filter for that particular column alone.

Filter predicates are cleared for a particular column by invoking the following method:

* GridColumn.ClearFilter: Clears the filter for the corresponding column.

#### View Filtering

SfDataGrid provides support to achieve view filtering by setting the SfDataGrid.View.Filter property. FilterRecords method filters the data that contains the filterText value. Assign FilterRecords method to SfDataGrid.View.Filter predicate to filter CustomerName column.


{% highlight C# %}





public bool FilterRecords(object o)

{

    string filterText = this.filterBox.Text.ToString();

    var item = o as OrderInfo;

    if (item != null)

    {

        if (this.filterBox.Text.ToString() != string.Empty)

        {

            if (filterText.Contains(","))

            {

                 var ids = filterText.Split(',');

                 foreach (var idd in ids)

                 {

                     if (item.CustomerName.Contains(idd))

                         return true;

                 }

            }

            else

      {

     if (item.CustomerName.Contains(filterText))

                      return true;

            }

         }

     }

    return false;

}

{% endhighlight %}



The following code example demonstrates view-level filtering.


{% highlight C# %}





// A custom filter method is assigned when the filter button is clicked.

void FilterBtn_Click(object sender, RoutedEventArgs e)

{

     this.datagrid.View.Filter = FilterRecords;

     this.datagrid.View.RefreshFilter();

}
{% endhighlight %}




The following screenshot displays the filtered records that contain the word “son”.



![](Features_images/Features_img114.png)



DataGrid with filtered records that contain the word “son”
{:.caption}
N> View.Filter is not applied when itemssource is DataTable.

## How To

### How to change look and feel of FilterIcon when Filter is applied

You can edit the FilterToggleButton style in blend. You can see Filtered and UnFiltered VisualStates in it. You can change PathFillColor for FilterToggleButton. 

1. Create new project in Blend for VisualStudio 2013.
2. Add assemblies to project.
3. In assets category you can see SfDataGrid.
4. Drag that control and drop it to DesignView.
5. Then right-click on SfDataGrid that you dropped in Design view.
6. Select “Edit Additional Templates”.
7. Then select Edit HeaderStyle.
8. Now copy of GridHeaderCellControlstyle is created.
9. In Objects and Timeline panel, you can see the Template is created for GridHeaderCellControl.
10. Now expand to PART_FilterToggleButton.
11. Right-click on that select Edit a copy.
12. In code View, you can get a FilterToggleButton style.

You can add the following code example within Filtered Layer.


{% highlight xml %}





<ColorAnimation Duration="0:0:0:1"

                Storyboard.TargetName="PathFillColor"

                Storyboard.TargetProperty="Color"

                To="Red" />

{% endhighlight %}



Add the following code example within UnFiltered Layer.


{% highlight xml %}



<ColorAnimation Duration="0:0:0:1"

                Storyboard.TargetName="PathFillColor"

                Storyboard.TargetProperty="Color"

                To="Gray" />


{% endhighlight %}


Now bind this PathFillColor to PART_FilterToggleButtonIndicator.


{% highlight xml %}





<Path.Fill>

    <SolidColorBrush x:Name="PathFillColor" Color="Gray" />

</Path.Fill>

{% endhighlight %}



When you apply above style to FilterToggleButton, FilterIcon changes from Default to Gray and to Red when filtering is applied. When you clear it, it changes from Red to Gray and to default style.

### How to improve filter Popup opening time

You can improve the filter pop-up opening time by setting CanGenerateUniqueItems property value to ‘False’. A textbox is loaded instead of AdvancedFilterComboBox that allows you to manually enter text for filtering. This increases GridFilterControl’s loading performance.


{% highlight xml %}





<Style TargetType="syncfusion:AdvancedFilterControl">

    <Setter Property="CanGenerateUniqueItems" Value="False" />

</Style>
{% endhighlight %}


#### Disable Advanced filter options in GridFilterControl?

By setting the FilterMode property as CheckboxFilter in GridFilterControl style, you can disable the advanced filtering option. This loads the CheckboxFilter only in GridFilterControl.


{% highlight xml %}

 



<Style TargetType="syncfusion:GridFilterControl">

    <Setter Property="FilterMode" Value="CheckBoxFilter"/>

</Style>
{% endhighlight %}


### Apply filtering for particular column in code behind?

You can apply filtering for a particular column by setting filter predicates for a particular column. The EmployeeId column needs to be filtered for the employee whose employee ID is 4. This is illustrated in the following code example.


{% highlight C# %}





// A custom filter method is assigned when you click the filter button.

void FilterBtn_Click(object sender, RoutedEventArgs e)

{ 

this.datagrid.Columns["EmployeeID"].FilterPredicates.Add(new FilterPredicate() {FilterType = FilterType.Equals, FilterValue = 1001,

PredicateType = PredicateType.Or });

}

{% endhighlight %}

### How to Load the Text Filters for the column having Number or Date value as underlying type

When you use the Text Filters for the column that has number or date value as underlying type, you can set FilterBehavior property of the Grid Column as StringTyped. This loads the Text Filters instead of Number or Date Filters.



{% highlight xml %}





<syncfusion:GridNumericColumn FilterBehavior="StringTyped" MappingName="CustomerID" />

{% endhighlight %}



You can achieve this by using FilterItemsPopulating (in Event topic you can find about this event) event also. The following code example illustrates how to use this event.


{% highlight C# %}



syncgrid.FilterItemsPopulating += syncgrid_FilterItemsPopulating;

…

void syncgrid_FilterItemsPopulating(object sender, GridFilterItemsPopulatingEventArgs e)

{

    if(e.Column.MappingName == "OrderID")

    e.FilterControl.AdvancedFilterType = AdvancedFilterType.TextFilter;

    e.FilterControl.SetColumnDataType(typeof(string));

    e.FilterControl.AscendingSortString = GridResourceWrapper.SortNumberAscending;

}
{% endhighlight %}


### How to get the Filtered records list

You can get Filtered records from the view of SfDataGrid using FilterChanged event. SfDataGrid has view property that returns the collection. When filter is applied, the filtered records are available in this view. You need to wire this event. The following code example illustrates you how to get the filtered records.


{% highlight C# %}



// To Hook Event

syncgrid.FilterChanged += syncgrid_FilterChanged;

…

void syncgrid_FilterChanged(object sender, GridFilterEventArgs e)

{

    //Orders Is Model Class For that You Need Record List

    ObservableCollection<Orders> order = new ObservableCollection<Orders>();

    var recordEntry = (sender as SfDataGrid).View.Records;

    foreach(RecordEntry record in recordEntry)

    {

         // You can Get Filtered Record List In Order Collection.

        order.Add(record.Data as Orders); 

    }            

}
{% endhighlight %}