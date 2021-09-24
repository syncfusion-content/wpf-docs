---
layout: post
title: Grouping in WPF DataGrid control | Syncfusion
description: Learn here all about Grouping support in Syncfusion WPF DataGrid (SfDataGrid) control, its elements and more details.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Grouping in WPF DataGrid (SfDataGrid)

[WPF DataGrid](https://www.syncfusion.com/wpf-controls/datagrid) allows you to group the data against one or more columns. When grouping is applied, the data is organized into a hierarchical structure based on matching column values and it is sorted by ascending order.
 
SfDataGrid allows you to group the data in below ways,

* UI Grouping
* Programmatic Grouping

## UI grouping

You can allow end-user to group the data by setting  [SfDataGrid.AllowGrouping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AllowGrouping) property to `true` , where user can drag and drop the column into `GroupDropArea` to group based on that column.
 
When the column is grouped, records that have an identical value in the column are combined to form a group. The GroupDropArea can be enabled by setting the [SfDataGrid.ShowGroupDropArea](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ShowGroupDropArea) property to `true`.


{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowGrouping="False"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}"
                        ShowGroupDropArea="True" />    
{% endhighlight %}
{% highlight c# %}
this.dataGrid.AllowGrouping = true;
{% endhighlight %}
{% endtabs %}

You can enable or disable grouping on particular column by setting the [GridColumn.AllowGrouping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_AllowGroupingProperty) property.


{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="False"
                        ItemsSource="{Binding Orders}"
                        ShowGroupDropArea="True">
    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridTextColumn AllowGrouping="True" MappingName="OrderID" />
        <syncfusion:GridTextColumn AllowGrouping="False" MappingName="CustomerID" />        
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.Columns["OrderID"].AllowGrouping = true;
this.dataGrid.Columns["CustomerID"].AllowGrouping = true;
{% endhighlight %}
{% endtabs %}


N> [GridColumn.AllowGrouping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_AllowGroupingProperty) takes higher priority than [SfDataGrid.AllowGrouping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AllowGrouping).

![WPF DataGrid Grouping](Grouping_images/wpf-datagrid-grouping.png)

The data can be grouped by an unlimited number of columns. To group more than one columns, drag-and-drop the desired columns in to `GroupDropArea`.

![Multiple Grouping in WPF DataGrid](Grouping_images/wpf-datagrid-multiple-grouping.png)

Each group is identified by its `CaptionSummaryRows` and it is used to organize the data into a hierarchical tree structure based on identical values of that column. The underlying records in each caption summary row can be expanded or collapsed by clicking its group caption.


Each `CaptionSummaryRow` carries information about a particular group like group name, number of items (records) in the group, etc. You can refer [Caption Summaries](http://help.syncfusion.com/wpf/sfdatagrid/summaries#caption-summaries) section, for more information about `CaptionSummaryRow`.

## Programmatic grouping

The WPF DataGrid (SfDataGrid) allows you to group the data programmatically by adding or removing [GroupColumnDescription](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupColumnDescription.html) to [SfDataGrid.GroupColumnDescriptions](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupColumnDescriptions) collection.

For example, if you want to group the OrderID column programmatically, define its [MappingName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_MappingName) to [ColumnName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupColumnDescription.html#Syncfusion_UI_Xaml_Grid_GroupColumnDescription_ColumnName) property of `GroupColumnDescription`. Then add the `GroupColumnDescription` to the `SfDataGrid.GroupColumnDescriptions` collection.


{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}"
                        ShowGroupDropArea="True">
    <syncfusion:SfDataGrid.GroupColumnDescriptions>
        <syncfusion:GroupColumnDescription ColumnName="OrderID" />
    </syncfusion:SfDataGrid.GroupColumnDescriptions>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GroupColumnDescriptions.Add(new GroupColumnDescription() { ColumnName = "OrderID" });
{% endhighlight %}
{% endtabs %}


You can group more than one column programmatically.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                               
                        ItemsSource="{Binding Orders}"
                        ShowGroupDropArea="True">

    <syncfusion:SfDataGrid.GroupColumnDescriptions>
        <syncfusion:GroupColumnDescription ColumnName="OrderID" />
        <syncfusion:GroupColumnDescription ColumnName="CustomerID" />
    </syncfusion:SfDataGrid.GroupColumnDescriptions>

</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.View.BeginInit();
this.dataGrid.GroupColumnDescriptions.Add(new GroupColumnDescription() { ColumnName = "OrderID" });
this.dataGrid.GroupColumnDescriptions.Add(new GroupColumnDescription() { ColumnName = "CustomerID" });
this.dataGrid.View.EndInit();
{% endhighlight %}
{% endtabs %}

## Group based on display text

You can group the column in DataGrid based on the value being displayed in cell by setting [GridColumn.GroupMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_GroupMode) as `Display`.
In the below example, OrderID column displays value with one decimal digit in cell. But when you group, groups will be created based on actual value considering all decimal digits of value (Refer right side screen shot). You can group based value displayed in the cell by setting [GridColumn.GroupMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_GroupMode) as `Display` (Refer left side screen shot for the same data).

{% tabs %}
{% highlight xaml %}
<Syncfusion:GridNumericColumn NumberDecimalDigits="1" MappingName="OrderID" HeaderText="OrderID" GroupMode="Display"/>
{% endhighlight %}
{% highlight c# %}
this.datagrid.Columns["OrderID"].GroupMode = DataReflectionMode.Display;
{% endhighlight %}
{% endtabs %}

![Grouped Column in WPF DataGrid based on Display Text](Grouping_images/wpf-datagrid-grouped-column.png)

### Group caption based on DisplayMember when grouping GridComboBoxColumn and GridMultiColumnDropDownList

In WPF DataGrid (SfDataGrid), you can group the column based on display value and also the same can be displayed  in caption summary by setting [GridColumn.GroupMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_GroupMode) as `Display`.

{% tabs %}
{% highlight xaml %}
<Syncfusion:GridComboBoxColumn ItemsSource="{Binding ComboItemsSource}" MappingName="ShipId" DisplayMemberPath="ShipCity" SelectedValuePath="ShipId" GroupMode="Display"/>
{% endhighlight %}
{% highlight c# %}
this.datagrid.Columns.Add(new GridComboBoxColumn()
{
    ItemsSource = viewModel.ComboItemsSource,
    DisplayMemberPath = "ShipCity",
    MappingName = "ShipId",
    SelectedValuePath = "ShipId",
    GroupMode = DataReflectionMode.Display
});
{% endhighlight %}
{% endtabs %}

![Grouped Column in WPF DataGrid based on Display Member](Grouping_images/wpf-datagrid-member-group-column.png)

## Clearing or removing group

You can remove all the groups by clearing [SfDataGrid.GroupColumnDescriptions](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupColumnDescriptions) collection.


{% tabs %}
{% highlight c# %}
this.dataGrid.GroupColumnDescriptions.Clear();
{% endhighlight %}
{% endtabs %}


You can ungroup the column programmatically at runtime by removing [GroupColumnDescription](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupColumnDescription.html)  from [SfDataGrid.GroupColumnDescriptions](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupColumnDescriptions) collection.


{% tabs %}
{% highlight c# %}
this.dataGrid.View.BeginInit();            
this.dataGrid.GroupColumnDescriptions.Remove(this.dataGrid.GroupColumnDescriptions[0]);
this.dataGrid.View.EndInit();
{% endhighlight %}
{% endtabs %}


To ungroup the column in UI, click the close button on column header or drag the column header from the `GroupDropArea` and drop it on the header row.

![WPF DataGrid Column without Grouping](Grouping_images/wpf-datagrid-without-grouping.png)


## Hiding the column when grouped

You can hide the column header when the particular column gets grouped by setting [SfDataGrid.ShowColumnWhenGrouped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ShowColumnWhenGrouped) property to `false`.

 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}"
                        ShowColumnWhenGrouped="False"
                        ShowGroupDropArea="True" />
{% endhighlight %}
{% highlight c# %}
this.dataGrid.ShowColumnWhenGrouped = false;
{% endhighlight %}
{% endtabs %}


![Hide Grouping Column in WPF DataGrid](Grouping_images/wpf-datagrid-hide-grouping.png)

## Freezing caption rows when scrolling 

You can freeze the group caption of the group in view until its records scrolled out of the view by setting the [SfDataGrid.AllowFrozenGroupHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AllowFrozenGroupHeaders) property to `true`.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"                            
                        AutoGenerateColumns="True"
                        AllowFrozenGroupHeaders="True"
                        ItemsSource="{Binding Orders}"
                        ShowGroupDropArea="True" />

{% endhighlight %}
{% highlight c# %}
this.dataGrid.AllowFrozenGroupHeaders = true;
{% endhighlight %}
{% endtabs %}


![WPF DataGrid with Frozen Caption Summary Rows](Grouping_images/wpf-datagrid-freeze-caption-rows.png)

## Expanding or collapsing the groups

By default, you can view the records in each group by expanding or collapsing its group caption.

You can allow end-user to expand or collapse the groups programmatically at runtime.
 
### Expand groups while grouping
 
You can expand all the groups while grouping by setting [SfDataGrid.AutoExpandGroups](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AutoExpandGroups) to `true`. So, when user group any column, then all groups will be in expanded state.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoExpandGroups="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}"
                        ShowGroupDropArea="True" />
{% endhighlight %}
{% highlight c# %}
this.dataGrid.AutoExpandGroups = true;
{% endhighlight %}
{% endtabs %}

### Programmatically expand or collapse the groups

#### Expand or collapse all the Groups

You can expand or collapse all the groups at programmatically at runtime by using [SfDataGrid.ExpandAllGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ExpandAllGroup) and [SfDataGrid.CollapseAllGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CollapseAllGroup) methods.


{% tabs %}
{% highlight c# %}
this.dataGrid.ExpandAllGroup();
this.dataGrid.CollapseAllGroup();
{% endhighlight %}
{% endtabs %}


#### Expand or Collapse the Group based on its level

You can expand or collapse the group based on its level by using [SfDataGrid.ExpandGroupsAtLevel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ExpandGroupsAtLevel_System_Int32_) and [SfDataGrid.CollapseGroupsAtLevel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CollapseGroupsAtLevel_System_Int32_) methods.


{% tabs %}
{% highlight c# %}
this.dataGrid.ExpandGroupsAtLevel(2);
this.dataGrid.CollapseGroupsAtLevel(2);
{% endhighlight %}
{% endtabs %}


#### Expand or Collapse the specific Group

You can expand or collapse specific group by using [SfDataGrid.ExpandGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ExpandGroup_Syncfusion_Data_Group_) and [SfDataGrid.CollapseGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CollapseGroup_Syncfusion_Data_Group_) methods.


{% tabs %}
{% highlight c# %}
var group = (dataGrid.View.Groups[0] as Group);
this.dataGrid.ExpandGroup(group);
this.dataGrid.CollapseGroup(group);
{% endhighlight %}
{% endtabs %}

## Customize indent column width 

You can customize the width of IndentColumn in SfDataGrid by using [IndentColumnWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_IndentColumnWidth) property as like below.

{% tabs %}
{% highlight xaml %}
<Syncfusion:SfDataGrid x:Name="dataGrid"                                      
                       AllowGrouping="True"
                       IndentColumnWidth="50"
                       ShowGroupDropArea="True"
                       ItemsSource="{Binding OrderInfoCollection }">
{% endhighlight %}
{% highlight c# %}
this.dataGrid.IndentColumnWidth = 50;
{% endhighlight %}
{% endtabs %}

## GroupDropArea customization

### GroupDropArea text

You can change the `GroupDropArea’ s` text can by setting [SfDataGrid.GroupDropAreaText](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupDropAreaText) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       GroupDropAreaText="Drag and drop the columns here"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True" />
{% endhighlight %}
{% endtabs %}


![WPF DataGrid with Custom Group Drop Area Text](Grouping_images/wpf-datagrid-custom-group-text.png)

### GroupDropArea height and appearance


SfDataGrid allows you to customize the appearance and height of `GroupDropArea` by writing the style of TargetType `GroupDropArea`.


{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <Style TargetType="syncfusion:GroupDropArea">
        <Setter Property="Height" Value="80" />        
        <Setter Property="Foreground" Value="Red" />
        <Setter Property="Background" Value="Pink" />
    </Style>
</Window.Resources>

{% endhighlight %}
{% endtabs %}


![Customizing GroupDropDrea Height in WPF DataGrid](Grouping_images/wpf-datagrid-group-drop-area-height.png)

### Expanding GroupDropArea while loading


By default, the `GroupDropArea` will be expanded while dragging the column towards the `GroupDropArea`. You can set the `GroupDropArea` to be always expanded by setting the [SfDataGrid.IsGroupDropAreaExpanded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_IsGroupDropAreaExpanded) property to `true`. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        IsGroupDropAreaExpanded="True"
                        ItemsSource="{Binding Orders}"
                        ShowGroupDropArea="True" />
{% endhighlight %}
{% highlight c# %}
this.dataGrid.IsGroupDropAreaExpanded = true;
{% endhighlight %}
{% endtabs %}


## Custom grouping

DataGrid allows you to group the data based on custom logic when the built-in grouping functionality doesn’t meet your requirement. 

To perform custom grouping on a particular column , specify the custom logic through [GroupColumnDescription.Converter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupColumnDescriptions) property and the column name to [GroupColumnDescription.ColumnName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupColumnDescription.html#Syncfusion_UI_Xaml_Grid_GroupColumnDescription_ColumnNameProperty) property.

For an example, the Date column is grouped based on the week basis in the following example.

 
{% tabs %}
{% highlight c# %}
public class GroupDateTimeConverter : IValueConverter
{
    public object Convert(object value, System.Type targetType, object parameter, CultureInfo culture)
    {
        var saleinfo = value as SalesByDate;
        var dt = DateTime.Now;
        var days = (int)Math.Floor((dt - saleinfo.Date).TotalDays);
        var dayofweek = (int)dt.DayOfWeek;
        var difference = days - dayofweek;

        if (days <= dayofweek)
        {

            if (days == 0)
                return "TODAY";

            if (days == 1)
                return "YESTERDAY";
            return saleinfo.Date.DayOfWeek.ToString().ToUpper();
        }

        if (difference > 0 && difference <= 7)
            return "LAST WEEK";

        if (difference > 7 && difference <= 14)
            return "TWO WEEKS AGO";

        if (difference > 14 && difference <= 21)
            return "THREE WEEKS AGO";

        if (dt.Year == saleinfo.Date.Year && dt.Month == saleinfo.Date.Month)
            return "EARLIER THIS MONTH";

        if (DateTime.Now.AddMonths(-1).Month == saleinfo.Date.Month)
            return "LAST MONTH";
        return "OLDER";
    }

    public object ConvertBack(object value, System.Type targetType, object parameter, CultureInfo culture)
    {
        throw new System.NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}


Now , assign the `GroupDateTimeConverter` into [GroupColumnDescription.Converter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupColumnDescriptions) and set `Date` property to [GroupColumnDescription.ColumnName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupColumnDescription.html#Syncfusion_UI_Xaml_Grid_GroupColumnDescription_ColumnNameProperty) property.


{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <local:GroupDateTimeConverter x:Key="customGroupDateTimeConverter" />        
</Window.Resources>
  
<syncfusion:SfDataGrid  x:Name="dataGrid"                          
                        AutoGenerateColumns="True"                          
                        ItemsSource="{Binding DailySalesDetails}">

    <syncfusion:SfDataGrid.GroupColumnDescriptions>
        <syncfusion:GroupColumnDescription ColumnName="Date" Converter="{StaticResource customGroupDateTimeConverter}" />
    </syncfusion:SfDataGrid.GroupColumnDescriptions>
        
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}


![WPF DataGrid with Custom Grouping](Grouping_images/wpf-datagrid-custom-grouping.png)

You can download samples from below location,
Refer [sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/CustomGroupingDemo541349132.zip) for Custom grouping when ItemsSource is ObservableCollection.

Refer [sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/DataTableCustomGrouping1799878748.zip) for Custom grouping when ItemsSource is DataTable.

You can refer [here](http://help.syncfusion.com/wpf/sfdatagrid/sorting#custom-sorting) to apply custom sorting when grouping is applied.

### Sorting the grouped column records 

In custom grouping, you can sort all the inner records of each group by setting [GroupColumnDescription.SortGroupRecords](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupColumnDescription.html#Syncfusion_UI_Xaml_Grid_GroupColumnDescription_SortGroupRecords)
sorted based on the column name described in [GroupColumnDescription](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupColumnDescription.html).

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid.GroupColumnDescriptions>
    <syncfusion:GroupColumnDescription ColumnName="SickLeaveHours"
                                       Converter="{StaticResource customGrouping}"
                                       SortGroupRecords="True" />
</syncfusion:SfDataGrid.GroupColumnDescriptions>
{% endhighlight %}
{% highlight c# %}
GroupColumnDescription groupColumnDesc = new GroupColumnDescription()
{
    ColumnName = "SickLeaveHours",
    Converter = new CustomGroupingConverter(),
    SortGroupRecords = true
};
dataGrid.GroupColumnDescriptions.Add(groupColumnDesc);
{% endhighlight %}
{% endtabs %}

In the below screenshot custom grouping is applied based on `SickLeaveHours` column and the inner records in each group are sorted based on `SickLeaveHours` value.


![Sorting Inner Records Group in WPF DataGrid](Grouping_images/wpf-datagrid-sort-inner-records.png)

## Sorting groups based on summary values

DataGrid allows you to sort the groups based its summary values. You can sort the groups based on summary aggregate value  by using [SfDataGrid. SummaryGroupComparer](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SummaryGroupComparer) property.


Follow the below steps to sort the groups based on caption aggregate value.

### Define custom group comparer with custom sort logic

In the below code snippet, the `OrderID` column compared and sorted based on the number of order count in each `OrderID`.
 
{% tabs %}
{% highlight c# %}
public class SortGroupComparers : IComparer<Group>, ISortDirection
{
    public ListSortDirection SortDirection { get; set; }

    public int Compare(Group x, Group y)
    {

        int cmp = 0;
        var xgroupSummary = Convert.ToInt32((x as Group).GetSummaryValue(x.SummaryDetails.SummaryRow.SummaryColumns[0].MappingName, "Count"));
        var ygroupSummary = Convert.ToInt32((y as Group).GetSummaryValue(x.SummaryDetails.SummaryRow.SummaryColumns[0].MappingName, "Count"));
        cmp = ((IComparable)xgroupSummary).CompareTo(ygroupSummary);

        if (this.SortDirection == ListSortDirection.Descending)
            cmp = -cmp;
        return cmp;
    }
}
{% endhighlight %}
{% endtabs %}

### Defining custom group comparer to DataGrid

Custom group comparer can be defined in SfDataGrid using [SfDataGrid.SummaryGroupComparer](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SummaryGroupComparer) property. `SummaryGroupComparer` maintains the custom comparers and the custom comparer gets called when corresponding column is grouped.


{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowSorting="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}"
                        ShowGroupDropArea="True"
                        SummaryGroupComparer="{StaticResource groupComparer}">

    <syncfusion:SfDataGrid.GroupColumnDescriptions>
        <syncfusion:GroupColumnDescription ColumnName="OrderID" />
    </syncfusion:SfDataGrid.GroupColumnDescriptions>

    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow Title="Items Count: {IDCount}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="IDCount"
                                                Format="'{Count}'"
                                                MappingName="OrderID"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}


![Displaying Grouping in WPF DataGrid using Custom Group Comparer](Grouping_images/wpf-datagrid-custom-group-comparer.png)

You can download the sample demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SortBySummaryDemo-355692747.zip).


## Grouping events

### GroupExpanding event

The [SfDataGrid.GroupExpanding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event occurs when the group is being expanded.
 
The [GroupChangingEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupChangingEventArgs.html) of the `GroupExpanding` event provides the information about the expanding group and it has the following members.

[Group](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupChangingEventArgs.html#Syncfusion_UI_Xaml_Grid_GroupChangingEventArgs_Group) - Gets the group that’s being expanded.

[Cancel](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.canceleventargs.cancel?view=net-5.0) – Decides whether to cancel the group expansion.
 
You can cancel the group expansion by setting [GroupChangingEventArgs.Cancel](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.canceleventargs.cancel?view=net-5.0) to `true`.


{% tabs %}
{% highlight c# %}
this.dataGrid.GroupExpanding += dataGrid_GroupExpanding;

void dataGrid_GroupExpanding(object sender, Syncfusion.UI.Xaml.Grid.GroupChangingEventArgs e)
{

    if (e.Group.Key.Equals(1001))    
        e.Cancel = true;    
}       
{% endhighlight %}
{% endtabs %}

### GroupExpanded event

The [SfDataGrid.GroupExpanded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event occurs after the group is expanded.

 
The [GroupChangedEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupChangedEventArgs.html) of the `GroupExpanded` event provides the information about the expanded group and it has the following member.

[Group](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupChangedEventArgs.html#Syncfusion_UI_Xaml_Grid_GroupChangedEventArgs_Group) - Gets the expanded group.

### GroupCollapsing event 

The [SfDataGrid.GroupCollapsing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event occurs when the group is being collapsed.

The [GroupChangingEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupChangingEventArgs.html)  of the `GroupCollapsing` event provides the information about the collapsing group and it contains the following member.

[Group](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupChangingEventArgs.html#Syncfusion_UI_Xaml_Grid_GroupChangingEventArgs_Group) - Gets the group that’s being collapsed.

[Cancel](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.canceleventargs.cancel?view=net-5.0) – Decides whether to cancel the group collapsing.

 
You can cancel the group is being collapsed by using [GroupChangingEventArgs.Cancel](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.canceleventargs.cancel?view=net-5.0) of `GroupCollapsing` event.


{% tabs %}
{% highlight c# %}
this.dataGrid.GroupCollapsing += dataGrid_GroupCollapsing;

void dataGrid_GroupCollapsing(object sender, GroupChangingEventArgs e)
{

    if (e.Group.Key.Equals(1001))    
        e.Cancel = true;    
}
{% endhighlight %}
{% endtabs %}

### GroupCollapsed event
 
The [SfDataGrid.GroupCollapsed](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event occurs after the group is collapsed.
 
[GroupChangedEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupChangedEventArgs.html) of the `GroupCollapsed` event  provides the information about collapsed group and it contains the following member.

[Group](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GroupChangedEventArgs.html#Syncfusion_UI_Xaml_Grid_GroupChangedEventArgs_Group) - Gets the collapsed group.

## See Also
[How to remove the gridline of WPF DataGrid (SfDataGrid) with grouping?](https://www.syncfusion.com/kb/11009)

[How to maintain expanded state of groups in printing?](https://www.syncfusion.com/kb/10042)

[How to show vertical border to the column wise summary rows?](https://www.syncfusion.com/kb/10038)

[How to define summary rows using AttachedProperty in datagrid](https://www.syncfusion.com/kb/9838)

[How to displaying Group header name based on other column](https://www.syncfusion.com/kb/7837)

[How to clear selection while grouping/ungrouping?](https://www.syncfusion.com/kb/6650)

[How to add selection to data rows of each group on expanding its CaptionSummaryRow?](https://www.syncfusion.com/kb/4211)

[How to change the CaptionSummaryRow Style based on the grouping level?](https://www.syncfusion.com/kb/4147)

[How to Change the GroupCaptionText based on Display member of the GridComboboxColumn?](https://www.syncfusion.com/kb/3446)

[How to add controls like TextBox in GroupDropArea?](https://www.syncfusion.com/kb/3370)

[How to customize the CaptionSummaryCell text in the SfDataGrid?](https://www.syncfusion.com/kb/3249)

[How to apply the Custom Grouping while grouping the column using GroupDropArea?](https://www.syncfusion.com/kb/2732)

[How to avoid selection while grouping and ungrouping in SfDataGrid?](https://www.syncfusion.com/kb/2531)

[How to customize the GroupDropArea?](https://www.syncfusion.com/kb/2434)
