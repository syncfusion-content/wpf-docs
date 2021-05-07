---
layout: post
title: Sorting in WPF TreeGrid control | Syncfusion
description: Learn here all about Sorting support in Syncfusion WPF TreeGrid (SfTreeGrid) control and more.
platform: wpf
control: SfTreeGrid
documentation: ug
---


# Sorting in WPF TreeGrid (SfTreeGrid)

SfTreeGrid allows you to sort the data against one or more columns either in ascending or descending order. When sorting is applied, the rows are rearranged based on sort criteria. You can allow users to sort the data by touching or clicking the column header using [SfTreeGrid.AllowSorting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowSorting) property to `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeGrid Name="treeGrid"
						AllowSorting="True"                             
						AutoExpandMode="RootNodesExpanded"                    
						ChildPropertyName="Children"                  
						ItemsSource="{Binding EmployeeDetails}">
{% endhighlight %}
{% highlight c# %}

this.treeGrid.AllowSorting = true;

{% endhighlight %}
{% endtabs %}

In another way, you can enable or disable the sorting for particular column by setting the [TreeGridColumn.AllowSorting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_AllowSorting) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeGrid Name="treeGrid"
							   AllowSorting="False"
							   AutoGenerateColumns="False"
							   AutoExpandMode="RootNodesExpanded"                    
							   ChildPropertyName="Children"                  
							   ItemsSource="{Binding EmployeeDetails}">
	<syncfusion:SfTreeGrid.Columns>
		<syncfusion:TreeGridTextColumn AllowSorting="True" MappingName="FirstName" />
		<syncfusion:TreeGridTextColumn AllowSorting="False" MappingName="LastName" />
		<syncfusion:TreeGridTextColumn  MappingName="Id" />
		<syncfusion:TreeGridNumericColumn MappingName="Salary" />
	</syncfusion:SfTreeGrid.Columns>
</syncfusion:SfTreeGrid>
	
{% endhighlight %}
{% highlight c# %}

this.treeGrid.Columns["FirstName"].AllowSorting = true;
this.treeGrid.Columns["LastName"].AllowSorting = false;

{% endhighlight %}
{% endtabs %}

N> The[TreeGridColumn.AllowSorting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_AllowSorting) takes higher priority than [SfTreeGrid.AllowSorting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowSorting) property.

End users can sort the column by clicking column header cell. Once the columns get sorted, the sort indicator will be displayed on the right side of the column header.

![Sorting_img1](Sorting_images/Sorting_img1.png)

## Sort column in double click

By default, column gets sorted when column header clicked. You can change this behavior to sort the column in double click action by setting [SfTreeGrid.SortClickAction](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SortClickAction) property to `DoubleClick`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeGrid Name="treeGrid"
						AllowSorting="True"
						SortClickAction="DoubleClick"
						AutoExpandMode="RootNodesExpanded"                    
						ChildPropertyName="Children"                  
						ItemsSource="{Binding EmployeeDetails}">
							   
{% endhighlight %}
{% highlight c# %}

this.treeGrid.AllowSorting = true;
this.treeGrid.SortClickAction = SortClickAction.DoubleClick;
	
{% endhighlight %}
{% endtabs %}

## Sorting order

By default, the data is sorted in ascending or descending order when clicking column header. You can rearrange the data to its initial order from descending, when clicking column header by setting [SfTreeGrid.AllowTriStateSorting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowTriStateSorting) property.

Following are the sequence of sorting orders when clicking column header,

* Sorts the data in ascending order
* Sorts the data in descending order
* Clears the sorting and records displayed in its initial order

## Multi column sorting

SfTreeGrid control allows you sort more than one column, where sorting is applied one column against other columns. To apply sorting on multiple columns, user have to click the column header by pressing the &lt;kbd&gt;Ctrl&lt;/kbd&gt; key.
In the below screen shot, the `First Name` column sorted. Then the `Employee ID` column is sorted against the `First Name` data by clicking column header by pressing &lt;kbd&gt;Ctrl&lt;/kbd&gt; key. The sorting state of `First Name` column is preserved and `Employee ID` column sorted against `First Name` column.

![Sorting_img2](Sorting_images/Sorting_img2.png)

### Display sort order

It is also possible to display sorted order of columns in header by setting [SfTreeGrid.ShowSortNumbers](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_ShowSortNumbers) property to `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeGrid Name="treeGrid"
					AllowSorting="True"
					ShowSortNumbers="True"
					AutoExpandMode="RootNodesExpanded"                    
					ChildPropertyName="Children"                  
					ItemsSource="{Binding EmployeeDetails}">
						
{% endhighlight %}
{% highlight c# %}

this.treeGrid.ShowSortNumbers = true;
	
{% endhighlight %}
{% endtabs %}

![Sorting_img3](Sorting_images/Sorting_img3.png)

## Programmatic Sorting

You can sort the data programmatically by adding or removing the SortColumnDescription in [SfTreeGrid.SortColumnDescriptions](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SortColumnDescription.html) property.

N> [SfTreeGrid.SortColumnChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) and [SfTreeGrid.SortColumnChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) events are not raised when the data sorted programmatically through `SfTreeGrid.SortColumnDescriptions`.

### Adding sort columns

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeGrid Name="treeGrid"
						AllowSorting="True"
						AutoExpandMode="RootNodesExpanded"                    
						ChildPropertyName="Children"                  
						ItemsSource="{Binding EmployeeDetails}">
			<syncfusion:SfTreeGrid.SortColumnDescriptions>
				<sync:SortColumnDescription ColumnName="FirstName" SortDirection="Ascending" />
				<sync:SortColumnDescription ColumnName="Id" SortDirection="Descending"/>
			</syncfusion:SfTreeGrid.SortColumnDescriptions>
</syncfusion:SfTreeGrid>

{% endhighlight %}
{% highlight c# %}

this.treeGrid.SortColumnDescriptions.Add(new SortColumnDescription() { ColumnName = "FirstName",SortDirection=ListSortDirection.Ascending });
this.treeGrid.SortColumnDescriptions.Add(new SortColumnDescription() { ColumnName = "Id", SortDirection = ListSortDirection.Descending });
	
{% endhighlight %}
{% endtabs %}

### Removing sort columns

You can unsort the data by removing the corresponding `SortColumnDescription` from the [SfTreeGrid.SortColumnDescriptions](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SortColumnDescription.html) property.

{% tabs %}
{% highlight c# %}

var sortColumnDescription = this.treeGrid.SortColumnDescriptions.FirstOrDefault(col => col.ColumnName == "FirstName");

if (sortColumnDescription != null)
    this.treeGrid.SortColumnDescriptions.Remove(sortColumnDescription);
			  
{% endhighlight %}
{% endtabs %}

### Clear sorting

You can clear sorting, by clearing the [SfTreeGrid.SortColumnDescriptions](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SortColumnDescription.html).

{% tabs %}
{% highlight c# %}

this.treeGrid.SortColumnDescriptions.Clear();
	
{% endhighlight %}
{% endtabs %}

## Custom sorting

SfTreeGrid allows you to sort the columns based on the custom logic. 
The custom sorting can be applied by adding the [SortComparer](http://help.syncfusion.com/cr/wpf/Syncfusion.Data.SortComparer.html) instance to [SfTreeGrid.SortComparers](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_SortComparers). 

The [SortComparer](http://help.syncfusion.com/cr/wpf/Syncfusion.Data.SortComparer.html) have the following properties,

[PropertyName](https://help.syncfusion.com/cr/wpf/Syncfusion.Data.SortComparer.html#Syncfusion_Data_SortComparer_PropertyName) - Gets or sets the name of the column to apply custom sorting.

[Comparer](https://help.syncfusion.com/cr/wpf/Syncfusion.Data.SortComparer.html#Syncfusion_Data_SortComparer_Comparer) - Gets or sets the custom comparer in which you can code to compare the data using custom logic. 

You can implement [ISortDirection](http://help.syncfusion.com/cr/wpf/Syncfusion.Data.ISortDirection.html) interface in comparer to get the sort direction. So you can apply different custom logics for ascending and descending. 

Follow the below steps to add custom comparer to sort using custom logic,

#### Define custom comparer with custom sort logic

In the below code snippet, `FirstName` property is compared based on its string length, instead of default string comparison. 
 
{% tabs %}
{% highlight c# %}

public class CustomSortComparer : IComparer<object>, ISortDirection
{

	public int Compare(object x, object y)
	{
		var item1 = x as EmployeeInfo;
		var item2 = y as EmployeeInfo;
		var value1 = item1.FirstName;
		var value2 = item2.FirstName;
		int c = 0;

		if (value1 != null && value2 == null)
		{
			c = 1;
		}

		else if (value1 == null && value2 != null)
		{
			c = -1;
		}

		else if (value1 != null && value2 != null)
		{
			c = value1.Length.CompareTo(value2.Length);
		}

		if (SortDirection == ListSortDirection.Descending)
			c = -c;

		return c;
	}

	//Get or Set the SortDirection value
	private ListSortDirection _SortDirection;

	public ListSortDirection SortDirection
	{
		get { return _SortDirection; }
		set { _SortDirection = value; }
	}
}
	
{% endhighlight %}
{% endtabs %}

####Adding custom comparer to SfTreeGrid

Custom comparer can be added to [SfTreeGrid.SortComparers](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_SortComparers) property. `SortComparers` maintains custom comparers and the custom comparer gets called when corresponding column gets sorted by clicking column header or programmatically.

{% tabs %}
{% highlight xaml %}
	
xmlns:data="clr-namespace:Syncfusion.Data;assembly=Syncfusion.Data.WPF"

<syncfusion:SfTreeGrid.SortComparers>
	<data:SortComparer Comparer="{StaticResource sortComparer}"  PropertyName="FirstName" />
</syncfusion:SfTreeGrid.SortComparers>
	
{% endhighlight %}
{% highlight c# %}

this.treeGrid.SortComparers.Add(new SortComparer() { Comparer = new CustomSortComparer(), PropertyName = "FirstName" });	
	
{% endhighlight %}
{% endtabs %}

Sorting `FirstName` column sorts the data using custom sort comparer available in `SfTreeGrid.SortComparers`.

![Sorting_img4](Sorting_images/Sorting_img4.png)

## Handling events

### SortColumnChanging event

[SfTreeGrid.SortColumnChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event occurs while sorting the columns by clicking column header. [GridSortColumnsChangingEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridSortColumnsChangingEventArgs.html) has following members which provides information for `SortColumnChanging` event.

[Action](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridSortColumnsChangingEventArgs.html#Syncfusion_UI_Xaml_Grid_GridSortColumnsChangingEventArgs_Action) - Gets the action triggered this event. 

[Cancel](http://msdn2.microsoft.com/en-us/library/system.componentmodel.canceleventargs.cancel.aspx) - Setting value to `true`, cancels the triggered action. 

[AddedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridSortColumnsChangingEventArgs.html#Syncfusion_UI_Xaml_Grid_GridSortColumnsChangingEventArgs_AddedItems) - Gets the list of new `SortColumnDescriptions` that are added.

[RemovedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridSortColumnsChangingEventArgs.html#Syncfusion_UI_Xaml_Grid_GridSortColumnsChangingEventArgs_RemovedItems) - Gets the list of `SortColumnDescriptions` that are removed. 

[CancelScroll](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridSortColumnsChangingEventArgs.html#Syncfusion_UI_Xaml_Grid_GridSortColumnsChangingEventArgs_CancelScroll) - Gets or sets a value that indicates, whether scroll and bring SelectedItem in view after sorting takes place.

You can prevent sorting for the particular column through [GridSortColumnsChangingEventArgs.Cancel](http://msdn2.microsoft.com/en-us/library/system.componentmodel.canceleventargs.cancel.aspx) property of `SortColumnChanging` event.

{% tabs %}
{% highlight c# %}

this.treeGrid.SortColumnsChanging += TreeGrid_SortColumnsChanging;

private void TreeGrid_SortColumnsChanging(object sender, GridSortColumnsChangingEventArgs e)
{

	if (e.AddedItems[0].ColumnName == "FirstName")
	{
		e.Cancel = true;
	}
}
	
{% endhighlight %}
{% endtabs %}

### SortColumnChanged event

[SfTreeGrid.SortColumnChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event occurs when the sorting is applied to the column. [GridSortColumnsChangedEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridSortColumnsChangedEventArgs.html) provides information for `SortColumnChanged` event. 
