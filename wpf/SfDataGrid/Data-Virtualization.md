---
layout: post
title: Data Virtualization support in SfDataGrid.
description: How to use Data Virtualization in SfDataGrid.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Data Virtualization

SfDataGrid provides support to handle the large amount of data through built-in virtualization features. With Data virtualization, [SfDataGrid.View](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~View.html) process the data in on-demand for better performance while loading large amount of data. Below are the different virtualization concepts available,

<table>
<tr>
<th>
Concept
</th>
<th>
Usage
</th>
</tr>
<tr>
<td>
VirtualizingCollectionView
</td>
<td>
Use to load large amount of data in less time.
</td>
</tr>
<tr>
<td>
Custom VirtualizingCollectionView
</td>
<td>
Use to load large amount of data in less time and also data can be loaded in on-demand.
</td>
</tr>
<tr>
<td>
Incremental Loading
</td>
<td>
Use to load subset of data from the services or servers in less time while loading and scrolling. On-demand request also supported.
</td>
</tr>
<tr>
<td>
Paging
</td>
<td>
Use to load large amount of data in less time with the help of SfDataPager.
</td>
</tr>
<tr>
<td>
On-demand paging
</td>
<td>
Use to load data in on-demand. You can load data only for current page from server. 
</td>
</tr>
</table>

## VirtualizingCollectionView
 
You can load the large amount of data in less time using [GridVirtualizingCollectionView](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridVirtualizingCollectionView.html) which is derived from [VirtualizingCollectionView](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.Data.WPF~Syncfusion.Data.VirtualizingCollectionView.html) to [SfDataGrid.ItemsSource](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~ItemsSource.html). 

In the below code, ViewModel defined with `GridVirtualizingCollectionView` by passing complete records collection and bound to SfDataGrid.

{% tabs %}
{% highlight c# %}
public class ViewModel
{
    private GridVirtualizingCollectionView _gridVirtualizingItemsSource;
    public GridVirtualizingCollectionView GridVirtualizingItemsSource
    {
        get { return _gridVirtualizingItemsSource; }
        set { _gridVirtualizingItemsSource = value; }
    }

    public ViewModel()
    {
        var _orders = this.GenerateOrders();                        
        GridVirtualizingItemsSource = new GridVirtualizingCollectionView(_orders);
    }
}
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ColumnSizer="Star"
                       ItemsSource="{Binding GridVirtualizingItemsSource}" />
{% endhighlight %}
{% endtabs %}

### Limitations 

1. Data update using [LiveDataUpdateMode](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~LiveDataUpdateMode.html) is not supported.
2. Details view is not supported.
3. [AllowFrozenGroupHeaders](http://help.syncfusion.com/cr/cref_files/wpf/sfgridconverter/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~AllowFrozenGroupHeaders.html) is not supported.

## Creating Custom VirtualizingCollectionView

SfDataGrid supports to override GridVirtualizingCollectionView and retrieve the data in on-demand by inheriting [GridVirtualizingCollectionView](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridVirtualizingCollectionView.html) class. The `GridVirtualizingCollectionView` class provides set of virtual methods to load data and handle the operations like sorting, filtering, and grouping.

You can load the data in on-demand by overriding below methods in `GridVirtualizingCollectionView`.

<table>
<tr>
<th>
Methods
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
{{'[GetInternalSource](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.Data.WPF~Syncfusion.Data.VirtualizingCollectionView~GetInternalSource.html#"")'| markdownify }}
</td>
<td>
Returns the source.
</td>
</tr>
<tr>
<td>
{{'[GetItemAt](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.Data.WPF~Syncfusion.Data.CollectionViewAdv~GetItemAt.html#"")'| markdownify }}
</td>
<td>
Returns the data object by specified `index` from the collection. If the collection is filtered then returns from filtered source.
</td>
</tr>
<tr>
<td>
{{'[GetIndexOf](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.Data.WPF~Syncfusion.Data.VirtualizingCollectionView~GetIndexOf.html#"")'| markdownify }}
</td>
<td>
Returns the index by specified data object from the collection. If the collection is filtered then returns from filtered source.
</td>
</tr>
<tr>
<td>
{{'[GetViewRecordCount](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.Data.WPF~Syncfusion.Data.VirtualizingCollectionView~GetViewRecordCount.html#"")'| markdownify }}
</td>
<td>
Returns the data object count from collection. If the collection is filtered then returns using filtered source count.
</td>
</tr>
</table>

Below code creates the `GridVirtualizingCollectionViewExt` to load the virtualized data collection.

{% tabs %}
{% highlight c# %}
public class GridVirtualizingCollectionViewExt : GridVirtualizingCollectionView
{
    IList<OrderInfo> sourceCollection;
    public GridVirtualizingCollectionViewExt()
        : base()
    {
        sourceCollection = new ViewModel().Orders;
    }
    
    /// <summary>
    /// Gets the index of specified item.
    /// </summary>
    /// <param name="item">Specifies the item to get the index</param>
    /// <returns>Returns the index  of specified item</returns>
    protected override int GetIndexOf(object item)
    {
       return sourceCollection.IndexOf(item as OrderInfo);
    }
    
    /// <summary>
    /// Returns the specified index item from sourceCollection.
    /// </summary>
    /// <param name="index"></param>
    /// <returns></returns>
    public override object GetItemAt(int index)
    {
        return sourceCollection[index];
    }
    
    /// <summary>
    /// Gets the records count that are inview.
    /// </summary>
    /// <returns>Returns the records count that are inview</returns>
    public override int GetViewRecordCount()
    {
        return sourceCollection.Count();
    }
    
    /// <summary>
    /// Gets the list of records in view.
    /// </summary>
    /// <returns>Returns the list of records in view</returns>
    public override System.Collections.IEnumerable GetInternalSource()
    {
        return sourceCollection;
    }
    
    /// <summary>
    /// Process the sort on collection based on specified sort description. 
    /// </summary>
    /// <param name="sortDescription">Specifies the sort description to sort the collection</param>
    protected override void ProcessSort(System.ComponentModel.SortDescriptionCollection sortDescription)
    {
    }    
}
{% endhighlight %}
{% endtabs %}

Below code, sets the `GridVirtualizingCollectionViewExt` to SfDataGrid.ItemsSource.

{% tabs %}
{% highlight c# %}
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
        this.dataGrid.ItemsSource = new GridVirtualizingCollectionViewExt();            
    }
}
{% endhighlight %}
{% endtabs %}

### Handling Data Management with VirtualizingCollectionView

You can handle `Sorting`, `Filtering` and `Grouping` in custom virtualizing collection view by below methods.

<table>
<tr>
<th>
Methods
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
{{'[GetSourceList](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.Data.WPF~Syncfusion.Data.VirtualizingCollectionView~GetSourceList.html#"")'| markdownify }}
</td>
<td>
Returns the whole source to apply filter. Used to populate the items for ExcelLikeFilter pop-up.
</td>
</tr>
<tr>
<td>
{{'[ApplyFilter](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.Data.WPF~Syncfusion.Data.VirtualizingCollectionView~ApplyFilter.html#"")'| markdownify }}
</td>
<td>
Apply filter on source collection based on filter predicates.
</td>
</tr>
<tr>
<td>
{{'[ProcessSort](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.Data.WPF~Syncfusion.Data.VirtualizingCollectionView~ProcessSort.html#"")'| markdownify }}
</td>
<td>
Apply sorting on the source collection based on the sort descriptions. 
</td>
</tr>
<tr>
<td>
{{'[GetGroupedSource](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.Data.WPF~Syncfusion.Data.VirtualizingCollectionView~GetGroupedSource.html#"")'| markdownify }}
</td>
<td>
Apply grouping on source collection based on group descriptions and returns the grouped source.
</td>
</tr>
</table>

#### Sorting

You can apply sorting on collection based on custom logic by overriding `ProcessSort` method.

{% tabs %}
{% highlight c# %}
public class GridVirtualizingCollectionViewExt : GridVirtualizingCollectionView
{
    /// <summary>
    /// Process the sort on collection based on specified sort description. 
    /// </summary>
    /// <param name="sortDescription">Specifies the sort description to sort the collection</param>       
    protected override void ProcessSort(System.ComponentModel.SortDescriptionCollection sortDescription)
    {        
        this.sourceCollection = this.sourceCollection.OrderBy(item => item.Country).ToList();     
    }
}
{% endhighlight %}
{% endtabs %}

#### Filtering

You can filter the collection using `ApplyFilter` method. To load items source ExcelLikeFiltering pop-up, you can use `GetSourceListForFilteringItems`
You need to use the filtered source if the collection has filtered in `GetElementAt`, `GetIndexOf` and `GetViewRecordCount` methods.

{% tabs %}
{% highlight c# %}
public class GridVirtualizingCollectionViewExt : GridVirtualizingCollectionView
{
    IList<OrderInfo> filteredSource;
    public GridVirtualizingCollectionViewExt()
            : base(
    {
            sourceCollection = new ViewModel().Orders;
            filteredSource = new ObservableCollection<OrderInfo>();
    }
    
    /// <summary>
    /// Gets the SourceCollection to load items source in FilterPop-up control.
    /// </summary>
    /// <returns>Returns the SourceCollection</returns>
    public override System.Collections.IEnumerable GetSourceListForFilteringItems()
    {
        return sourceCollection;
    }
    
    /// <summary>
    /// Applies filter on collection.
    /// </summary>
    /// <param name="RowFilter">Specifies the RowFilter to apply filter on collection</param>
    protected override void ApplyFilter(Predicate<object> RowFilter)
    {
        foreach (var item in sourceCollection)
        {
            if (FilterRecord(item))
            {
                // The filtered data is stored in filteredSource. After filtering is applied- the GetItemAt method is called, you need to pass the Data from filteredSource to display the filtered data.
                this.filteredSource.Add(item);
            }
        }    
    }

    private void ClearFilter()
    {
        this.filteredSource.Clear();
    }
    
    /// <summary>
    /// Refresh the view while apply and clear the filter
    /// </summary>
    public override void RefreshFilter()
    {
        var filterPresent = this.FilterPredicates.Any(v => v.FilterPredicates != null && v.FilterPredicates.Count > 0);
    
        if (filterPresent)
        {
            var source = this.sourceCollection.OfQueryable().AsQueryable();
            ParameterExpression paramExpression;
    
            Expression predicate = this.GetPredicateExpression(source, out paramExpression);
            if (paramExpression != null && predicate != null)
            {
                var lamda = Expression.Lambda(predicate, paramExpression);
                var delg = lamda.Compile();
                this.RowFilter = (o) =>
                {
                    var result = (bool)delg.DynamicInvoke(o);
                    return result;
                };
            }         
        }
        else
            this.RowFilter = null;   
    
        if (this.RowFilter != null)
            ApplyFilter(null);
        else
            ClearFilter();
    
        Refresh();
    }
}
{% endhighlight %}
{% endtabs %}

#### Grouping

You can apply grouping on collection based custom logic and returns the grouped source by overriding `GetGroupedSource` method.

{% tabs %}
{% highlight c# %}
public class GridVirtualizingCollectionViewExt : GridVirtualizingCollectionView
{
    /// <summary>
    /// Gets the grouped result by specified group by array.
    /// </summary>
    /// <param name="groupBy">Specifies the group by array to get the group result on collection</param>
    /// <returns></returns>
    protected override IEnumerable<GroupResult> GetGroupedSource(string[] groupBy)
    {
        IQueryable queryable = this.sourceCollection.OfQueryable().AsQueryable();
        var result = queryable.GroupByMany(this.SourceType, (property) => this.GetExpressionFunc(property), groupBy).ToList();
        return result;
    }
}
{% endhighlight %}
{% endtabs %}

## Incremental Loading
 
SfDataGrid supports to load the data incrementally using [ISupportIncrementalLoading](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.Data.WPF~Syncfusion.Data.ISupportIncrementalLoading.html) interface.
`ISupportIncrementalLoading` interface has[LoadMoreItems](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.IncrementalList%601~LoadMoreItemsAsync.html)Async method which helps to load the data incrementally. `LoadMoreItemsAsync` called in on-demand while scrolling based on[HasMoreItems](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.IncrementalList%601~HasMoreItems.html) property.

If `HasMoreItems` is `false`, SfDataGrid stops calling `LoadMoreItemsAsync`.  SfDataGrid have [IncrementalList](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.IncrementalList%601.html) which is derived from `ISupportIncrementalLoading`. You can use IncrementalList or create collection derived from ISupportIncrementalLoading and bind it SfDataGrid.ItemsSource.

In the below code, `IncrementalList` is initialized by passing Action to its constructor for loading items incrementally.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
    <local:ViewModel />
</Window.DataContext>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       AllowFiltering="True"
                       AutoGenerateColumns="True"    
                       ItemsSource="{Binding IncrementalItemsSource}"/>  
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
Public class ViewModel
{
    public ViewModel()
    {
        IncrementalItemsSource = new IncrementalList<OrderInfo>(LoadMoreItems) { MaxItemCount = 1000 };
    }

    private IncrementalList<OrderInfo> _incrementalItemsSource;
    public IncrementalList<OrderInfo> IncrementalItemsSource
    {
        get { return _incrementalItemsSource; }
        set { _incrementalItemsSource = value; }
    }

    /// <summary>
    /// Method to load items which assigned to the action of IncrementalList
    /// </summary>
    /// <param name="count"></param>
    /// <param name="baseIndex"></param>
    void LoadMoreItems(uint count, int baseIndex)
    {
        var _orders = GenerateOrders();
        var list = _orders.Skip(baseIndex).Take(50).ToList();
        IncrementalItemsSource.LoadItems(list);
    }
}
{% endhighlight %}
{% endtabs %}

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/IncrementalLoading-519410720.zip).

### Displaying animation when fetching data from services

You can display animations when fetching data from service for [LoadMoreItems](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.IncrementalList%601~LoadMoreItemsAsync.html)Async method call, using [BackgroundWorker](https://msdn.microsoft.com/en-us/library/system.componentmodel.backgroundworker.aspx). 

In the below code snippet data fetched from service using `BackgroundWorker` and SfBusyIndicator` displayed over SfDataGrid based on `IsBusy` property in ViewModel, until `BackgroundWorker` completes its action.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
    <local:ViewModel />
</Window.DataContext>
<Window.Resources>
    <local:BoolToVisiblityConverter x:Key="converter" />
</Window.Resources>
<Grid>
    <syncfusion:SfDataGrid x:Name="dataGrid" 
                           AllowFiltering="True"
                           AutoGenerateColumns="True"    
                           ItemsSource="{Binding IncrementalItemsSource}"/>  
    <Border Height="60"
            VerticalAlignment="Bottom"
            Background="Black"
            BorderBrush="Black"
            BorderThickness="1"
            Opacity="50"
            Visibility="{Binding IsBusy,
                                 Mode=TwoWay,
                                 Converter={StaticResource converter}}">
        <StackPanel HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Orientation="Horizontal">
            <TextBlock Margin="5"
                       VerticalAlignment="Center"
                       FontSize="16"
                       Foreground="White"
                       Text="Fetching Data..." />
            <syncfusion:SfBusyIndicator Margin="5"
                                        VerticalAlignment="Center"
                                        Foreground="Gray"
                                        AnimationType="Gear" />
        </StackPanel>
    </Border>
</Grid>
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
public class ViewModel : INotifyPropertyChanged
{
    NorthwindEntities northwindEntity;

    public ViewModel()
    {
        string uri="http://services.odata.org/Northwind/Northwind.svc/";
        incrementalItemsSource = new IncrementalList<Order>(LoadMoreItems) { MaxItemCount = 1000}; 
        northwindEntity = new NorthwindEntities(new Uri(uri));
        IsBusy = false;
    }

    private bool isBusy;
    /// <summary>
    /// Gets or Sets whether to show the busy indicator.
    /// </summary>
    public bool IsBusy
    {
        get { return isBusy; }
        set { isBusy = value; RaisePropertyChanged("IsBusy"); }
    }

    /// <summary>
    /// Loads the item while SfDataGrid loading and scrolling.
    /// </summary>
    /// <param name="count">Specifies the fetch count to load data</param>
    /// <param name="baseIndex">Specifies the index to load data</param>
    void LoadMoreItems(uint count, int baseIndex)
    {
        BackgroundWorker worker = new BackgroundWorker();
        worker.DoWork += (o, ae) =>
        {
            DataServiceQuery<Order> query = northwindEntity.Orders.Expand("Customer");
            query = query.Skip<Order>(baseIndex).Take<Order>(50) as DataServiceQuery<Order>;
            IAsyncResult ar = query.BeginExecute(null, null);
            var items = query.EndExecute(ar);
            var list = items.ToList();
            Application.Current.Dispatcher.Invoke(new Action(() => { IncrementalItemsSource.LoadItems(list); }));
        };

        worker.RunWorkerCompleted += (o, ae) =>
        {
            IsBusy = false; 
        };
            
        IsBusy = true;
        worker.RunWorkerAsync();
    }
}
{% endhighlight %}
{% endtabs %}

![](Data-Virtualization_images/Data-Virtualization_img1.png)

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/IncrementalLoading_Animation-1160118925.zip).

### LoadMore using ISupportIncrementalLoading

You can fetch the data in some user action instead of scrolling using [IncrementalList.LoadItems](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.IncrementalList%601~LoadItems.html) method.

In the below code, data fetched when you click the `Load Items` button.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>

<Grid x:Name="Root_Grid">
    <Grid.RowDefinitions>
        <RowDefinition Height="*"/>
        <RowDefinition Height="Auto"/>
    </Grid.RowDefinitions>
    <syncfusion:SfDataGrid x:Name="dataGrid"                                                                                                                                                                                           
                           AutoGenerateColumns="True"    
                           ItemsSource="{Binding IncrementalItemsSource}"/>
        <StackPanel Grid.Row="1" Orientation="Vertical">
            <Button x:Name="loadByButton" Content="Load Items" 
                            Command="{Binding DataContext.LoadItems , ElementName=dataGrid}"/>
        </StackPanel>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
public class ViewModel 
{
    NorthwindEntities northwindEntity;

    private IncrementalList<Order> _incrementalItemsSource;
    public IncrementalList<Order> IncrementalItemsSource
    {
        get { return _incrementalItemsSource; }
        set { _incrementalItemsSource = value; }
    }

    private BaseCommand loadItems;
    public BaseCommand LoadItems
    {
        get
        {
            if (loadItems == null)

                loadItems = new BaseCommand(OnLoadItemsClicked, OnCanLoad);
            return loadItems;
        }
    }

    private static bool OnCanLoad(object obj)
    {
        return true;
    }

    private void OnLoadItemsClicked(object obj)
    {            
        LoadMoreItems(5, this.IncrementalItemsSource.Count);
    }


    public ViewModel()
    {
        string uri="http://services.odata.org/Northwind/Northwind.svc/";
        _incrementalItemsSource = new IncrementalList<Order>(LoadMoreItems) { MaxItemCount = 50 }; 
        northwindEntity = new NorthwindEntities(new Uri(uri));
    }

    /// <summary>
    /// Method to load items which assigned to the action of IncrementalList
    /// </summary>
    /// <param name="count"></param>
    /// <param name="baseIndex"></param>
    void LoadMoreItems(uint count, int baseIndex)
    {                        
        DataServiceQuery<Order> query = northwindEntity.Orders.Expand("Customer");
        query = query.Skip<Order>(baseIndex).Take<Order>(50) as DataServiceQuery<Order>;
        IAsyncResult ar = query.BeginExecute(null, null);
        var items = query.EndExecute(ar);
        var list = items.ToList();
        IncrementalItemsSource.LoadItems(list);            
    }
}
{% endhighlight %}
{% endtabs %}

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/IncrementalLoading_-_LoadMoreItems-1914949679.zip).

### Limitations

1. Deleting is not supported. You can code to delete row in application level.
2. Summary is calculated based on [LiveDataUpdateMode](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~LiveDataUpdateMode.html).

## Paging

SfDataGrid supports to load paged data source using [SfDataPager](http://help.syncfusion.com/cr/cref_files/wpf/sfdatagrid/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html). You can use the paging in SfDataGrid by go through the [Paging](http://115.249.201.211:9090/wpf/sfdatagrid/paging) section.
