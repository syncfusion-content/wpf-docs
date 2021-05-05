---
layout: post
title: Data Virtualization in WPF DataGrid control | Syncfusion
description: Learn here all about Data Virtualization support in Syncfusion WPF DataGrid (SfDataGrid) control and more.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Data Virtualization in WPF DataGrid (SfDataGrid)

SfDataGrid provides support to handle the large amount of data through built-in virtualization features. With Data virtualization, [SfDataGrid.View](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_View) process the data in on-demand for better performance while loading large amount of data. Below are the different virtualization concepts available,

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
<code>Data Virtualization</code>
</td>
<td>
Use to load large amount of data in less time.
</td>
</tr>
<tr>
<td>
<code>Incremental Loading</code>
</td>
<td>
Use to load subset of data from the services or servers in less time while loading and scrolling. On-demand request also supported.
</td>
</tr>
<tr>
<td>
<code>Paging</code>
</td>
<td>
Use to load large amount of data in less time with the help of SfDataPager.
</td>
</tr>
<tr>
<td>
<code>On-demand paging</code>
</td>
<td>
Use to load data in on-demand. You can load data only for current page from server. 
</td>
</tr>
</table>

## Data Virtualization

You can load large amount of data in less time by setting [SfDataGrid.EnableDataVirtualization](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_EnableDataVirtualization) property to `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding EmployeeDetails}"
                       EnableDataVirtualization="True">
{% endhighlight %}
{% highlight c# %}
this.datagrid.EnableDataVirtualization = true;
{% endhighlight %}
{% endtabs %}

## Working with GridVirtualizingCollectionView

You can load the large amount of data in less time in another way using [GridVirtualizingCollectionView](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridVirtualizingCollectionView.html) which is derived from [VirtualizingCollectionView](http://help.syncfusion.com/cr/wpf/Syncfusion.Data.VirtualizingCollectionView.html) to [SfDataGrid.ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ItemsSource). 

In the below code, `ViewModel` defined with `GridVirtualizingCollectionView` by passing complete records collection and bound to SfDataGrid.

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

1. Data update using [LiveDataUpdateMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_LiveDataUpdateMode) is not supported.
2. Details view is not supported.
3. [AllowFrozenGroupHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AllowFrozenGroupHeaders) is not supported.
4. DataTable collection is not supported.

## Incremental Loading
 
DataGrid supports to load the data incrementally using [ISupportIncrementalLoading](http://help.syncfusion.com/cr/wpf/Syncfusion.Data.ISupportIncrementalLoading.html) interface.
`ISupportIncrementalLoading` interface has [LoadMoreItemsAsync](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.IncrementalList-1.html#Syncfusion_UI_Xaml_Grid_IncrementalList_1_LoadMoreItemsAsync_System_UInt32_) method which helps to load the data incrementally. `LoadMoreItemsAsync` called in on-demand while scrolling based on [HasMoreItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.IncrementalList-1.html#Syncfusion_UI_Xaml_Grid_IncrementalList_1_HasMoreItems) property.

If `HasMoreItems` is `false`, SfDataGrid stops calling `LoadMoreItemsAsync`.  SfDataGrid have [IncrementalList](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.IncrementalList-1.html) which is derived from `ISupportIncrementalLoading`. You can use `IncrementalList` or create collection derived from `ISupportIncrementalLoading` and bind it `SfDataGrid.ItemsSource`.

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

You can display animations when fetching data from service for [LoadMoreItemsAsync](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.IncrementalList-1.html#Syncfusion_UI_Xaml_Grid_IncrementalList_1_LoadMoreItemsAsync_System_UInt32_) method call, using [BackgroundWorker](https://msdn.microsoft.com/en-us/library/system.componentmodel.backgroundworker.aspx). 

In the below code snippet data fetched from service using `BackgroundWorker` and [SfBusyIndicator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBusyIndicator.html) displayed over SfDataGrid based on [IsBusy](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBusyIndicator.html#Syncfusion_Windows_Controls_Notification_SfBusyIndicator_IsBusy) property in `ViewModel`, until `BackgroundWorker` completes its action.

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

![wpf datagrid shows incremental loading of data](Data-Virtualization_images/Data-Virtualization_img1.png)

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/IncrementalLoading_Animation-1160118925.zip).

### LoadMore using ISupportIncrementalLoading

You can fetch the data in some user action instead of scrolling using [IncrementalList.LoadItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.IncrementalList-1.html#Syncfusion_UI_Xaml_Grid_IncrementalList_1_LoadItems_System_Collections_Generic_IEnumerable__0__) method.

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
2. Summary is not calculated based on [LiveDataUpdateMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_LiveDataUpdateMode).

## Paging

SfDataGrid supports to load paged data source using [SfDataPager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html). You can use the paging in SfDataGrid by go through the [Paging](https://help.syncfusion.com/wpf/datagrid/paging) section.
