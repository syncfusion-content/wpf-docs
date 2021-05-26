---
layout: post
title: Filtering in WPF TreeGrid control | Syncfusion
description: Learn here all about Filtering support in Syncfusion WPF TreeGrid (SfTreeGrid) control, its elements and more.
platform: wpf
control: SfTreeGrid
documentation: ug
---

# Filtering in WPF TreeGrid (SfTreeGrid)

Filtering is the process of retrieving the values from a collection that satisfies the specified condition. In SfTreeGrid, filtering can be applied through the UI as well as the programmatic filters.

## FilterLevel

You can filter the nodes based on level using the [SfTreeGrid.FilterLevel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_FilterLevel) property.

{% tabs %}
{% highlight c# %}

treeGrid.FilterLevel = FilterLevel.All;

{% endhighlight %}
{% endtabs %}

* Root - Filter will be applied to root nodes only in SfTreeGrid.

* All - Filter will be applied to all the nodes in SfTreeGrid.

* Extended - Filter will be applied to all the nodes. If a node matches the filter condition, its all ancestors will be displayed even though the parent node does not match the filter condition.

**Root**

Filter will be applied to root nodes only in SfTreeGrid. For other nodes, `IsFiltered` value will be false, and they always will be displayed in view.

**All**

Filter will be applied to all the nodes in SfTreeGrid. If a parent node does not match the filter condition, filter will not be applied for child nodes. Else, filter will be applied to its child nodes also.

**Extended**

Filter will be applied to all the nodes. If a node matches the filter condition, its all ancestors will also be displayed even though the parent node does not match the filter condition, and parent node’s `IsFiltered` value will be set to false.

N> You can change the `FilterLevel` at run time.

## Programmatic filtering

The programmatic filtering can be applied to SfTreeGrid using the following methods:

*	View Filtering
* 	Column Filtering


### View filtering

View filtering can be achieved by setting the [SfTreeGrid.View.Filter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridView.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridView_Filter) delegate and calling the [SfTreeGrid.View.RefreshFilter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridView.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridView_RefreshFilter) method.

{% tabs %}
{% highlight c# %}

public bool FilerNodes(object o)
{
    var data = o as Employee;

    if (data.Salary > 70000)
        return true;
    return false;
}

private void Button_Click(object sender, RoutedEventArgs e)
{
    treeGrid.View.Filter = FilerNodes;
    treeGrid.View.RefreshFilter();
}

{% endhighlight %}
{% endtabs %}

Here, `FilterNodes` delegate filters the data based on Salary. `FilterNodes` delegate is assigned to [SfTreeGrid.View.Filter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridView.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridView_Filter) predicate to filter the tree grid. After that, [SfTreeGrid.View.RefreshFilter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridView.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridView_RefreshFilter) method is called to refresh the nodes. If the node satisfies the filter conditions, true will be returned. Else false will be returned.

![WPF TreeGrid with Filtering](Filtering_images/wpf-treegrid-filtering.png)

While filtering, if the node satisfies filter condition, [IsFiltered](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeNode.html#Syncfusion_UI_Xaml_TreeGrid_TreeNode_IsFiltered) property of [TreeNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeNode.html) will be set as false. Else, it will be true. If `IsFiltered` value is True, the node will not be displayed in view, else it will be displayed in view.

N> SfTreeGrid refreshes the filtering on property change if [SfTreeGrid.LiveNodeUpdateMode ](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_LiveNodeUpdateMode)property is set as `AllowDataShaping`.

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/FilteringDemo-587565594).

### Clear filters

You can clear the view filters applied in tree grid by setting the `SfTreeGrid.View.Filter` delegate to null and calling the `SfTreeGrid.View.RefreshFilter` method.

{% tabs %}
{% highlight c# %}

treeGrid.View.Filter = null;
treeGrid.View.RefreshFilter();

{% endhighlight %}
{% endtabs %}

**HasVisibleChildNodes**

You can find whether a particular node has child node(s) displayed in a view (matches filtering criteria) using the [HasVisibleChildNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeNode.html#Syncfusion_UI_Xaml_TreeGrid_TreeNode_HasVisibleChildNodes) property in [TreeNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeNode.html).

{% tabs %}
{% highlight c# %}

var treeNode=treeGrid.View.Nodes[0];
var hasVisibleChildNodes = treeNode.HasVisibleChildNodes;

{% endhighlight %}
{% endtabs %}

### Column filtering

The column filtering can be achieved by adding the `FilterPredicate` to the [TreeGridColumn.FilterPredicates](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_FilterPredicates) property.

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.Columns["FirstName"].FilterPredicates.Add(
  new Syncfusion.Data.FilterPredicate()
  {
      FilterType = Syncfusion.Data.FilterType.Equals,
      FilterValue = "Chester"
  });

{% endhighlight %}
{% endtabs %}

#### Filter behavior
The [FilterBehavior](https://help.syncfusion.com/cr/wpf/Syncfusion.Data.FilterPredicate.html#Syncfusion_Data_FilterPredicate_FilterBehavior) property is used to specify whether to consider the [FilterValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Data.FilterPredicate.html#Syncfusion_Data_FilterPredicate_FilterValue) as string or specific data type.

* StringTyped - Records are filtered without considering the type and it takes FilterValue type as string.
* StronglyTyped - Records are filtered by considering the FilterValue underlying type.

#### Clear filtering

The filters applied to SfTreeGrid can be removed by clearing the `FilterPredicates` added for the columns. This can be achieved using the following methods:

* [SfTreeGrid.ClearFilters](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ClearFilters) - Clears filters for all the columns programmatically.
* [SfTreeGrid.ClearFilter(String columnName)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ClearFilter_System_String_) - Clears the filter for a specific column that has the columnName as MappingName.
* [SfTreeGrid.ClearFilter(TreeGridColumn column)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ClearFilter_Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_) - Clears the filter for a specific column alone.

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.ClearFilters();
this.sfTreeGrid.ClearFilter("FirstName");
this.sfTreeGrid.ClearFilter(this.sfTreeGrid.Columns["FirstName"]);


{% endhighlight %}
{% endtabs %}

#### Adding multiple filter predicates for a column

The [PredicateType](https://help.syncfusion.com/cr/wpf/Syncfusion.Data.FilterPredicate.html#Syncfusion_Data_FilterPredicate_PredicateType) property is used to apply multiple FilterPredicates for a column.

* And: Performs And operation in filters.
* AndAlso: Performs AndAlso operation in filters.
* Or: Performs Or operation in filters.
* OrElse: Performs OrElse operation in filters.

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.Columns["FirstName"].FilterPredicates.Add(
  new Syncfusion.Data.FilterPredicate()
  {
      FilterType = Syncfusion.Data.FilterType.Equals,
      FilterValue = "Chester",
      PredicateType = Syncfusion.Data.PredicateType.Or
  });

this.sfTreeGrid.Columns["FirstName"].FilterPredicates.Add(
    new Syncfusion.Data.FilterPredicate()
    {
        FilterType = Syncfusion.Data.FilterType.Equals,
        FilterValue = "Martin",
        PredicateType = Syncfusion.Data.PredicateType.Or
    });

{% endhighlight %}
{% endtabs %}

![WPF TreeGrid Column with Multiple Filter](Filtering_images/wpf-treegrid-multi-filter.png)

#### Filter DateColumn with range between two dates

A [TreeGridDateTimeColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridDateTimeColumn.html) can be filtered with a range between two dates by applying two FilterPredicate for the same column. The [FilterType](https://help.syncfusion.com/cr/wpf/Syncfusion.Data.FilterPredicate.html#Syncfusion_Data_FilterPredicate_FilterType) for the FilterPredicate with start date should be `GreaterThanOrEqual` and end date should be `LessThanOrEqual`.

## UI filtering

SfTreeGrid provides Excel-like filtering UI and advanced filter UI to filter the data easily. UI filtering can be enabled by setting the [SfTreeGrid.AllowFiltering](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_AllowFiltering) property to `true`. This allows to open the filter UI by clicking the filter icon on the column header to filter the nodes.

The filtering can be enabled or disabled for a specific column by setting the [TreeGridColumn.AllowFiltering](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_AllowFiltering) property.

{% tabs %}
{% highlight c# %}

// Enable UI filtering for SfTreeGrid.
this.sfTreeGrid.AllowFiltering = true;

// Enable UI filtering for EmployeeID column.
this.sfTreeGrid.Columns["EmployeeID"].AllowFiltering = true;


{% endhighlight %}
{% endtabs %}

N> `TreeGridColumn.AllowFiltering` has higher priority than the `SfTreeGrid.AllowFiltering` property.

### Built-in UI views

The SfTreeGrid provides the following types of filter pop-up modes:

* Check box filter: Provides Excel-like filter interface with a list of check boxes.

* Advanced filter: Provides advanced filter options to filter the data.

* Both: Both check box filter and advanced filter are loaded while opening the filter pop-up.

By default, the filter pop-up mode of the column is set to Both. The check box and the advanced filters can be switched using the Advanced Filter button.

#### Checkbox filtering UI

![Checkbox Filter in WPF TreeGrid](Filtering_images/wpf-treegrid-checkbox-filter.png)

#### Advanced filtering UI

![Advanced Filter in WPF TreeGrid](Filtering_images/wpf-treegrid-advanced-filter.png)

## Changing filter UI for grid

Filter UI view can be changed for all the columns in grid by changing the [FilterMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html#Syncfusion_UI_Xaml_TreeGrid_Filtering_TreeGridFilterControl_FilterMode) in [TreeGridFilterControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html) by writing style and assign it to [SfTreeGrid.FilterPopupStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_FilterPopupStyle).

{% tabs %}
{% highlight xaml %}

<Style x:Key="filterControlStyle" TargetType="syncfusion:TreeGridFilterControl">
    <Setter Property="FilterMode" Value="AdvancedFilter" />
</Style>

<syncfusion:SfTreeGrid Name="sfTreeGrid"
                           FilterPopupStyle="{StaticResource filterControlStyle}"
                           AllowFiltering="True”
                           ItemsSource="{Binding EmployeeDetails}" />

{% endhighlight %}
{% endtabs %}

## Changing filter UI for a column

Filter UI view can be changed for a specific column by changing the [FilterMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html#Syncfusion_UI_Xaml_TreeGrid_Filtering_TreeGridFilterControl_FilterMode) in [TreeGridFilterControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html) by writing style and assigning it to [TreeGridColumn.FilterPopupStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_FilterPopupStyle).

{% tabs %}
{% highlight xaml %}

<Style x:Key="filterControlStyle" TargetType="syncfusion:TreeGridFilterControl">
    <Setter Property="FilterMode" Value="AdvancedFilter" />
</Style>

<syncfusion:TreeGridTextColumn MappingName="FirstName"
                               FilterPopupStyle="{StaticResource filterControlStyle}"/>

{% endhighlight %}
{% endtabs %}

## Setting default filter popup style for a specific column

You can skip the [TreeGridFilterControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html) styling for a specific column in [SfTreeGrid.FilterPopupStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_FilterPopupStyle) by setting [TreeGridColumn.FilterPopupStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_FilterPopupStyle) to null.

{% tabs %}
{% highlight xaml %}

<Style x:Key="filterControlStyle" TargetType="syncfusion:TreeGridFilterControl">
    <Setter Property="FilterMode" Value="AdvancedFilter" />
</Style>

<syncfusion:SfTreeGrid Name="sfTreeGrid"
                           FilterPopupStyle="{StaticResource filterControlStyle}"
                           AllowFiltering="True”
                           ItemsSource="{Binding EmployeeDetails}" />

<syncfusion:TreeGridTextColumn MappingName="LastName" FilterPopupStyle="{x:Null}"/>

{% endhighlight %}
{% endtabs %}

## Check box filtering

The check box filtering is the same as Excel-like filter popup, which displays a search text box and a list of check boxes with unique items from the expanded tree nodes.

The items in the checked state will be visible in the view, and the other items will be filtered out of the view.

This filtering operation is performed based on the value of [SfTreeGrid.FilterLevel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_FilterLevel) property.

## Advanced filtering

Advanced filter UI provides multiple filter options to filter the data easily. Filter menu options are loaded based on advanced filter type by automatically detecting the underlying date type.

The following built-in filter types are supported in SfTreeGrid:

* Text filter: Loads various menu options to filter the display text effectively.

* Number filter: Loads various menu options to filter the numeric data.

* Date filter: Loads various menu options and [DatePicker](https://msdn.microsoft.com/en-in/library/system.windows.controls.datepicker.aspx) to filter date-time type columns.

<table>
<tr>
<th>
Text filters
</th>
<th>
Number filters
</th>
<th>
Date filters
</th>
</tr>
<tr>
<td>
When the string value is bound to the {{'[TreeGridColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html)'| markdownify }} or the items source is {{'[dynamic](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/dynamic)'| markdownify}}, then `TextFilters` are loaded in {{'[TreeGridAdvancedFilterControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridAdvancedFilterControl.html)'|markdownify}}.
</td>
<td>
When integer, double, short, decimal, byte, or long are bound to the {{'[TreeGridColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html)'|markdownify}}, then `Number Filters` are loaded in {{'[TreeGridAdvancedFilterControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridAdvancedFilterControl.html)'|markdownify}}.
</td>
<td>
When the DateTime type value is bound to the {{'[TreeGridColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html)'|markdownify}}, then `Date Filters` are loaded in {{'[TreeGridAdvancedFilterControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridAdvancedFilterControl.html)'|markdownify}}.
</td>
</tr>
<tr>
<td>
<img src="Filtering_images/wpf-treegrid-text-filter.png" alt="Displays Text Filter in WPF TreeGrid/>
</td>
<td>
<img src="Filtering_images/wpf-treegrid-number-filter.png" alt="Displays Number Filter in WPF TreeGrid"/>
</td>
<td>
<img src="Filtering_images/wpf-treegrid-date-filter.png" alt="Displays Date Filter in WPF TreeGrid"/>
</td>
</tr>
<tr>
<td>
<br><br>
<b>Filter menu options</b>
<ol>
<li>Equals</li>
<li>Does Not Equal</li>
<li>Begins With</li> 
<li>Ends With</li> 
<li>Contains</li> 
<li>Does Not Contain</li>
<li>Empty</li> 
<li>Not Empty</li>
<li>Null</li> 
<li>Not Null</li> 
</ol>
</td>
<td>
<b>Filter menu options</b>
<ol>
<li>Equals</li>
<li>Does Not Equal</li>
<li>Null</li>
<li>Not Null</li>
<li>Less Than</li>
<li>Less Than or Equal</li>
<li>Greater Than</li>
<li>Greater Than or Equal</li>
</ol>
</td>
<td>
<b>Filter menu options</b>
<ol>
<li>Equals</li>
<li>Does Not Equal</li>
<li>Before</li>
<li>Before Or Equal</li>
<li>After</li>
<li>After Or Equal</li>
<li>Null</li>
<li>Not Null</li>
</ol>
</td>
</tr>
</table>

N> The `Null` and `Not Null` options are available only when `AllowBlankFilters` is set to `True`.

## Instant filtering

By default, filters are applied to the columns when OK button is clicked in UI filtering. To update the filters immediately whenever update in filter popup, set [TreeGridColumn.ImmediateUpdateColumnFilter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_ImmediateUpdateColumnFilter) to `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:TreeGridTextColumn MappingName="EmployeeID" 
                               ImmediateUpdateColumnFilter="True"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.Columns["EmployeeID"].ImmediateUpdateColumnFilter = true;

{% endhighlight %}
{% endtabs %}

Here, the OK and Cancel buttons are unavailable and Done button is available to just close the popup.

The following screenshot illustrates the check box filter when `ImmediateUpdateColumnFilter` is set to `true`.

![CheckBox Filter with Immediate Filter in WPF TreeGrid](Filtering_images/wpf-treegrid-immediate-checkbox-filter.png)

The following screenshot illustrates the advanced filter when `ImmediateUpdateColumnFilter` is set to `true`.

![Advanced Filter with Immediate Filter in WPF TreeGrid](Filtering_images/wpf-treegrid-immediate-advanced-filter.png)

N> In check box filter, the `SelectAll` option is not reflected in the filter updates if [ImmediateUpdateColumnFilter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_ImmediateUpdateColumnFilter) is true.

## Filtering null values

To filter the null values, the [TreeGridColumn.AllowBlankFilters](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_AllowBlankFilters) property should be enabled. Enabling `AllowBlankFilters` includes null values into the filter items list.

{% tabs %}
{% highlight xaml %}

<syncfusion:TreeGridTextColumn MappingName="FirstName" AllowBlankFilters="True"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.Columns["FirstName"].AllowBlankFilters = true;

{% endhighlight %}
{% endtabs %}

The following screenshot illustrates the check box filter when `AllowBlankFilters` is set to `true`.

![Filter Null Values using CheckBox Filter in WPF TreeGrid](Filtering_images/wpf-treegrid-filter-null-values.png)

The following screenshot illustrates advanced filter when `AllowBlankFilters` is set to `true`.

![Filter Null Values using Advanced Filter in WPF TreeGrid](Filtering_images/wpf-treegrid-null-values.png)

## Changing AdvancedFilter type when loading dynamic ItemsSource

By default, the text filters will be loaded for the columns if `ItemsSource` is [dynamic](https://msdn.microsoft.com/en-us/library/dd264741.aspx). The [TreeGridColumn.ColumnMemberType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridColumn_ColumnMemberType) property loads number filters or date filters based on the column values.

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.Columns["EmployeeID"].ColumnMemberType = typeof(double);

{% endhighlight %}
{% endtabs %}

## Customization using events

### Loading text filter for number or date column

The [SfTreeGrid.FilterItemsPopulating](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event is used to load text filters for the columns that have number or date value as underlying type by setting value of the `TreeGridFilterItemsPopulatingEventArgs.FilterControl.AdvancedFilterType` property to `AdvancedFilterType.TextFilter`.

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.FilterItemsPopulating += OnSfTreeGridFilterItemsPopulating;

private void OnSfTreeGridFilterItemsPopulating(object sender, TreeGridFilterItemsPopulatingEventArgs e)
 {
     if (e.Column.MappingName == "EmployeeID")
         e.FilterControl.AdvancedFilterType = AdvancedFilterType.TextFilter;
 }

{% endhighlight %}
{% endtabs %}

### Customizing filter predicates

The filter predicates can be customized using the [SfTreeGrid.FilterChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event. This event occurs when applying filter using the filter control. Here, [FilterValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Data.FilterPredicate.html#Syncfusion_Data_FilterPredicate_FilterValue) is changed based on some conditions.

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.FilterChanging += OnSfTreeGridFilterChanging;

private void OnSfTreeGridFilterChanging(object sender, TreeGridFilterChangingEventArgs e)
{
    if (e.FilterPredicates == null || e.Column.MappingName != "FirstName")
        return;

    if (e.FilterPredicates[0].FilterValue.Equals("Chester"))
        e.FilterPredicates[0].FilterValue = "Abraham";
}

{% endhighlight %}
{% endtabs %}

### Customizing Excel-like filter ItemsSource

The [TreeGridFilterControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html) `ItemsSource` can be customized to restrict some data from filtering using the [SfTreeGrid.FilterItemsPopulated](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event. Here, the [FilterElement](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.FilterElement.html) that has actual value as 0 is removed from `ItemsSource`.

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.FilterItemsPopulated += OnSfTreeGridFilterItemsPopulated;

private void OnSfTreeGridFilterItemsPopulated(object sender, TreeGridFilterItemsPopulatedEventArgs e)
{
    if (e.Column.MappingName == "EmployeeID")
    {
        var itemsSource = e.ItemsSource as List<FilterElement>;

        // Get the FilterElement to remove from itemsSource.
        var filterElement = itemsSource.FirstOrDefault(items => items.ActualValue.Equals(0));

        // Remove the FilterElement from itemsSource.
        itemsSource.Remove(filterElement);
    }
}

{% endhighlight %}
{% endtabs %}

### Changing filter UI

Filter UI can be changed either for all the columns or for a specific column in SfTreeGrid by changing the [FilterMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html#Syncfusion_UI_Xaml_TreeGrid_Filtering_TreeGridFilterControl_FilterMode) property value using the [SfTreeGrid.FilterItemsPopulating](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event.

Here, filter UI is changed to `AdvancedFilter` only for `EmployeeID` column.

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.FilterItemsPopulating += SfTreeGrid_FilterItemsPopulating;

private void SfTreeGrid_FilterItemsPopulating(object sender, TreeGridFilterItemsPopulatingEventArgs e)
{
    if (e.Column.MappingName == "EmployeeID")
        e.FilterControl.FilterMode = FilterMode.AdvancedFilter;
}

{% endhighlight %}
{% endtabs %}

### Customizing sort options text

Sort options text can be customized by changing the value of [AscendingSortString](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html#Syncfusion_UI_Xaml_TreeGrid_Filtering_TreeGridFilterControl_AscendingSortString) and [DescendingSortString](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html#Syncfusion_UI_Xaml_TreeGrid_Filtering_TreeGridFilterControl_DescendingSortString) properties in the [TreeGridFilterControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html) using the [SfTreeGrid.FilterItemsPopulating](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event.

{% tabs %}
{% highlight c# %}

this.sfTreeGrid.FilterItemsPopulating += OnSfTreeGridFilterItemsPopulating;

private void OnSfTreeGridFilterItemsPopulating(object sender, TreeGridFilterItemsPopulatingEventArgs e)
{
    if (e.Column.MappingName == "FirstName")
    {
        e.FilterControl.AscendingSortString = "Sort Ascending";
        e.FilterControl.DescendingSortString = "Sort Descending";
    }
}

{% endhighlight %}
{% endtabs %}

![Customizing Sort Option Text in WPF TreeGrid](Filtering_images/wpf-treegrid-sort-option-customization.png)

## Appearance

### Hiding sort options

Sort options can be collapsed by setting the [SortOptionVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html#Syncfusion_UI_Xaml_TreeGrid_Filtering_TreeGridFilterControl_SortOptionVisibility) property in [TreeGridFilterControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html).

{% tabs %}
{% highlight xaml %}

<Style TargetType="syncfusion:TreeGridFilterControl" x:Key="filterControlStyle">
    <Setter Property="SortOptionVisibility" Value="Collapsed"/>
</Style>

<syncfusion:SfTreeGrid Name="sfTreeGrid"
                           FilterPopupStyle="{StaticResource filterControlStyle}"
                           AllowFiltering="True”
                           ItemsSource="{Binding EmployeeDetails}" />

{% endhighlight %}
{% endtabs %}

![Hide Sort Options in WPF TreeGrid](Filtering_images/wpf-treegrid-hide-sort-option.png)

### Customizing the filter popup size 

The size of the filter popup can be changed using the [FilterPopupHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html#Syncfusion_UI_Xaml_TreeGrid_Filtering_TreeGridFilterControl_FilterPopupHeight) and [FilterPopupWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html#Syncfusion_UI_Xaml_TreeGrid_Filtering_TreeGridFilterControl_FilterPopupWidth) properties in [TreeGridFilterControl](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.Filtering.TreeGridFilterControl.html).

{% tabs %}
{% highlight xaml %}

<Window.Resources>
    <Style TargetType="syncfusion:TreeGridFilterControl">
        <Setter Property="FilterPopupHeight" Value="530"/>
        <Setter Property="FilterPopupWidth" Value="500"/>
    </Style>
</Window.Resources>

{% endhighlight %}
{% endtabs %}

![Customizing Filter Popup Size in WPF TreeGrid](Filtering_images/wpf-treegrid-filter-popup-customization.png)

### Changing filter icon style after applying filters

The filter icon style can be changed by writing style with TargetType as [FilterToggleButton](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.FilterToggleButton.html).

{% tabs %}
{% highlight c# %}

<Style TargetType="syncfusion:FilterToggleButton">
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="syncfusion:FilterToggleButton">
                <Grid SnapsToDevicePixels="True">
                    <VisualStateManager.VisualStateGroups>

                        <VisualStateGroup x:Name="CommonStates">
                            <VisualState x:Name="Normal" />
                            <VisualState x:Name="MouseOver" />
                            <VisualState x:Name="Pressed" />
                            <VisualState x:Name="Disabled" />
                        </VisualStateGroup>

                        <VisualStateGroup x:Name="FilterStates">

                            <VisualState x:Name="Filtered">
                                <Storyboard>
                                    <ObjectAnimationUsingKeyFrames Storyboard.TargetName="PART_FilterToggleButtonIndicator" 
                                                           Storyboard.TargetProperty="Data">
                                        <DiscreteObjectKeyFrame KeyTime="0">
                                            <DiscreteObjectKeyFrame.Value>
                                                <Geometry>M2.1299944,9.9798575L55.945994,9.9798575 35.197562,34.081179 35.197562,
                                                  62.672859 23.428433,55.942383 23.428433,33.52121z M1.3001332,0L56.635813,
                                                  0C57.355887,0,57.935946,0.5891428,57.935946,1.3080959L57.935946,
                                                  2.8258877C57.935946,3.5448422,57.355887,4.133985,56.635813,4.133985L1.3001332,
                                                  4.133985C0.58005941,4.133985,-2.3841858E-07,3.5448422,0,2.8258877L0,
                                                  1.3080959C-2.3841858E-07,0.5891428,0.58005941,0,1.3001332,0z
                                                </Geometry>
                                            </DiscreteObjectKeyFrame.Value>
                                        </DiscreteObjectKeyFrame>
                                    </ObjectAnimationUsingKeyFrames>
                                    <ColorAnimation Duration="0:0:0:1"                                                       
                                            Storyboard.TargetName="PathFillColor"
                                            Storyboard.TargetProperty="Color"
                                            To="Red" />
                                </Storyboard>
                            </VisualState>

                            <VisualState x:Name="UnFiltered">
                                <Storyboard>
                                    <ObjectAnimationUsingKeyFrames Storyboard.TargetName="PART_FilterToggleButtonIndicator" 
                                                           Storyboard.TargetProperty="Data">
                                        <DiscreteObjectKeyFrame KeyTime="0">
                                            <DiscreteObjectKeyFrame.Value>
                                                <Geometry>F1M-2124.61,-1263.65L-2131.54,-1263.72 -2145.51,-1263.84 -2152.41,
                                                  -1263.9C-2155.99,-1263.93,-2157.48,-1262.16,-2155.7,-1259.96L-2152.05,
                                                  -1255.43C-2150.28,-1253.23,-2147.38,-1249.62,-2145.61,-1247.42L-2143.25,
                                                  -1244.5 -2143.25,-1230.24C-2143.25,-1229.23,-2142.43,-1228.42,-2141.42,
                                                  -1228.42L-2135.64,-1228.42C-2134.63,-1228.42,-2133.81,-1229.23,-2133.81,
                                                  -1230.24L-2133.81,-1244.78 -2131.7,-1247.3C-2129.89,-1249.47,-2126.93,-1253.02,
                                                  -2125.12,-1255.18L-2121.39,-1259.65C-2119.57,-1261.82,-2121.02,-1263.62,-2124.61,-1263.65z
                                                </Geometry>
                                            </DiscreteObjectKeyFrame.Value>
                                        </DiscreteObjectKeyFrame>
                                    </ObjectAnimationUsingKeyFrames>
                                    <ColorAnimation Duration="0:0:0:1"                                                       
                                            Storyboard.TargetName="PathFillColor"
                                            Storyboard.TargetProperty="Color"
                                            To="Gray" />
                                </Storyboard>
                            </VisualState>

                        </VisualStateGroup>

                    </VisualStateManager.VisualStateGroups>

                    <Border Width="{TemplateBinding Width}"
                    Height="{TemplateBinding Height}"
                    Background="{TemplateBinding Background}"
                    SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}">

                        <Path Name="PART_FilterToggleButtonIndicator"
                      Margin="3"
                      Data="F1M-2124.61,-1263.65L-2131.54,-1263.72 -2145.51,-1263.84 -2152.41,
                            -1263.9C-2155.99,-1263.93,-2157.48,-1262.16,-2155.7,
                            -1259.96L-2152.05,-1255.43C-2150.28,-1253.23,-2147.38,
                            -1249.62,-2145.61,-1247.42L-2143.25,-1244.5 -2143.25,
                            -1230.24C-2143.25,-1229.23,-2142.43,-1228.42,-2141.42,
                            -1228.42L-2135.64,-1228.42C-2134.63,-1228.42,-2133.81,
                            -1229.23,-2133.81,-1230.24L-2133.81,-1244.78 -2131.7,
                            -1247.3C-2129.89,-1249.47,-2126.93,-1253.02,-2125.12,
                            -1255.18L-2121.39,-1259.65C-2119.57,-1261.82,-2121.02,
                            -1263.62,-2124.61,-1263.65z"
                      SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}"
                      Stretch="Fill">
                            <Path.Fill>
                                <SolidColorBrush x:Name="PathFillColor" 
                                         Color="Gray" />
                            </Path.Fill>
                        </Path>

                    </Border>
                </Grid>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>

{% endhighlight %}
{% endtabs %}

![Customizing Filter Icon in WPF TreeGrid](Filtering_images/wpf-treegrid-filter-icon.png)
