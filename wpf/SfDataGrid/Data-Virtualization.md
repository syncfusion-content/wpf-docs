---
layout: post
title: Data Virtualization | SfDataGrid | WPF | Syncfusion
description: data virtualization
platform: wpf
control: SfDataGrid
documentation: ug
---

# Data Virtualization	

DataVirtualization is a term that achieves Virtualization for the actual data objects that are bound to the DataGrid. For small collection of basic data objects, the memory consumption is not significant; however for large collections, the memory consumption becomes very significant. For these reasons, it is desirable to use some sort of DataVirtualization mechanism to limit the amount of data object that is to be retrieved and instantiated in memory.

## Overview

DataVirtualization support enables you to work with huge data sources. DataGrid control creates records on demand by automatically enabling Data Virtualization when it is bounded to a data source of VirtualizingCollectionView.

## Enabling Virtualization in SfDataGrid

You can assign VirtualizingCollectionView object as ItemsSource for DataGrid to enable Virtualization.

## VirtualizingCollectionView

VirtualizingCollectionView is a type of ICollectionViewAdv that provides the functionality to create records that are needed. It creates the records for the rows that are in View.

The following code example illustrates how to create a VirtualizingCollectionView data source and assign it to DataGrid.


{% highlight C# %}



// Create the VirtualizingCollectionView object with enumerable data source.

VirtualizingCollectionView GridItemsSource = new VirtualizingCollectionView(enumerableDataSource);
{% endhighlight %}


{% highlight xml %}
}


<Window.DataContext>

<local:ViewModel/>

</Window.DataContext>



<syncfusion:SfDataGrid x:Name="dataGrid" 

                         AutoGenerateColumns="True"

                         ItemsSource="{Binding GridItemSource}"/>


{% endhighlight %}


To use extensive support of DataGrid like Excel-Like Filtering, Dynamic Object Binding, Unbound Columns, DisplayBinding and ValueBinding in DataVirtualization, you can define a GridVirtualizingCollectionView type of data source.

The following code example illustrates how to assign a GridVirtualizingCollectionView as ItemsSource for DataGrid.

{% highlight C# %}



//Create the GridVirtualizingCollectionView object with enumerable data source.

GridVirtualizingCollectionView GridItemsSource = new GridVirtualizingCollectionView(enumerableDataSource);
{% endhighlight %}

{% highlight xml %}





<syncfusion:SfDataGrid x:Name="dataGrid" 

                         AutoGenerateColumns="True"

                         ItemsSource="{Binding GridItemSource}"/>
{% endhighlight %}

## Custom Data Virtualization

Custom Data Virtualization is helpful for retrieving data from data sources on demand. DataGrid provides extensive support to achieve Custom Data Virtualization by inheriting the VirtualizingCollectionView class and overriding the virtual methods. To achieve Custom Data Virtualization, you can use a parameterless constructor of VirtualizingCollectionView.

### Virtual Methods of VirtualizingCollectionView

VirtualizingCollectionView contains the following virtual methods to override operations in CustomVirtualizingCollectionView class.

<table>
<tr>
<th>
Virtual Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
GetItemAt</td><td>
Object GetItemAt(int index)</td><td>
This method returns the data for the corresponding index.</td></tr>
<tr>
<td>
GetIndex</td><td>
Int GetIndex(object item)</td><td>
This method returns the index of the corresponding data.</td></tr>
<tr>
<td>
GetInternalSource</td><td>
IEnumerable GetInternalSource()</td><td>
This method returns the Collection of data in view.</td></tr>
<tr>
<td>
GetViewRecordCount</td><td>
Int GetViewRecordCount()</td><td>
This method returns the number of data in view.</td></tr>
<tr>
<td>
GetSourceListForFilteringItems</td><td>
IEnumerable GetSourceListForFilteringItems()</td><td>
This method returns the entire data source. > {{ '_Note: This is used while populating items for ExcelLikeFilter pop-up._' | markdownify }}> </td></tr>
<tr>
<td>
ProcessSort</td><td>
Void ProcessSort(SortDescriptionCollection sortDescriptions)</td><td>
This method is called when Sorting is applied.</td></tr>
<tr>
<td>
ApplyFilter</td><td>
Void ApplyFilter(Predicate&lt;object&gt; RowFilter)</td><td>
This method is called when filtering is applied.</td></tr>
<tr>
<td>
GetGroupedSource</td><td>
IEnumerable&lt;GroupResult&gt;  </td><td>
This method returns the Collection of group result after apply grouping.</td></tr>
</table>


N> GetInternalSource and GetViewRecorCount return the value based on filtering.

The following code example illustrates the Custom Data Virtualization class.


{% highlight C# %}





public class CustomVirtualizingClass : VirtualizingCollectionView

{



        IList<CountriesList> sourceCollection;



        public CustomVirtualizingClass()

            : base()

        {

            sourceCollection = new Countries();

        }



  /// <summary>

  /// Returns the index of data.

  /// </summary>   

        protected override int GetIndexOf(object item)

        {

            return sourceCollection.IndexOf(item as CountriesList);

        }



  /// <summary>

  /// Returns the data for corresponding index.

  /// </summary>   

        protected override object GetItemAt(int index)

        {

            return sourceCollection[index];

        }



  /// <summary>

        /// Returns the total view record count.

  /// </summary>   

        public override int GetViewRecordCount()

        {

            return sourceCollection.Count;

        }



  /// <summary>

        /// Returns the source collection.

  /// </summary>   

        public override IEnumerable GetInternalSource()

        {

            return sourceCollection;

        }

}

{% endhighlight %}

N> You can override the GetItemAt, GetIndexOf and GetViewRecordCount virtual methods when you create the custom virtualization class.

You can override the virtual methods in the VirtualizingCollectionView when you perform Sorting, Filtering and Grouping operations by using the Custom Data Virtualization class.

The following code example illustrates the methods that are used to achieve Sorting, Grouping and Filtering in the Custom Data Virtualization class.


{% highlight C# %}





   /// <summary>

   /// Total SortDescription Collection is the parameter for this method.       

   /// You can sort your source based on the SortDescription collection.

   /// </summary>   

   protected override void ProcessSort(SortDescriptionCollection sortDescription)

   {

       this.sourceCollection = this.sourceCollection.OrderBy(item => item.Country).ToList();

   }



   /// <summary>

   /// This method returns the collection of Syncfusion.Data.Extensions.GroupResult. 

   /// Hence you have to use Syncfusion.Data.Extensions.QueryableExtenstion.GroupByMany method to   

   /// get the collection of GroupResult.

   /// </summary>   

   protected override IEnumerable<GroupResult> GetGroupedSource(string[] groupBy)

   {

       IQueryable queryable = this.sourceCollection.OfQueryable().AsQueryable();

       var result = queryable.GroupByMany(this.SourceType, (property) => this.GetExpressionFunc(property), groupBy).ToList();

       return result;

   }

   /// <summary>

   /// The following method is called when filtering is applied to the column.

   /// The corresponding filter is passed as the parameter for this method.

   /// By applying the Filter predicate, you can filter your source.

   /// </summary>

   protected override void ApplyFilter(Predicate<object> Filter)

   {

       foreach (var item in sourceCollection)

       {

           if (Filter(item))

           {

             // The filtered data is stored in filteredSource. After filtering is applied, the GetItemAt method is called.

             // You need to pass the Data from filteredSource to display the filtered data.

               this.filteredSource.Add(item);

           }

       }

   }

{% endhighlight %}

### Limitations of Data Virtualization

DataVirtualization in DataGrid has certain limitations. They are as follows:

* Data reordering does not take place when a property is changed.
* Data Virtualization does not support Paging.

## Incremental Loading


Incremental Loading allows you to load a subset of data to DataGrid sequentially. It provides support for fast and fluid scrolling and loading a huge set of data. 

### Enabling Incremental Loading in SfDataGrid

You can enable IncrementalLoading in DataGrid by creating a data source with ISupportIncrementalLoading interface and assigning it to the ItemsSource property of DataGrid. ISupportIncrementalLoading interface has the following two members:

### LoadMoreItemsAsync Method

This method helps to load data incrementaly to the DataGrid. This method is called to fetch the initial set of data when the DataGrid loads. When you scroll the DataGrid and reach the last record of loaded data, DataGrid requests this method to load the next subset of data.

N> LoadMoreItemsAsync() method is called when HasMoreItems property is set to ‘true’.

### HasMoreItems

This is a boolean property that specifies whether the LoadMoreItemsAsync method is called or not. HasMoreItems is set to ‘false’ when the data source has no more data to load.

Also, you can use the DataFetchSize property of DataGrid to get or set the amount of data to fetch for virtualizing or prefetch operations. The default value of DataFetchSize property is five.

The IncrementalList<T> class implements the ISupportIncrementalLoading interface internally. You can use this class as your data source to perform Incremental Loading with DataGrid.

The following code example illustrates adding the IncrementaList<T> class as ItemsSource to DataGrid.


{% highlight C# %}





class IncrementalLoadingViewModel 

{

   public IncrementalLoadingViewModel()

   {

       // Create the IncrementalList<T> object with Func to load the items on-demand.

       itemSource = new IncrementalList<Employee>(LoadMoreItems) { MaxItemCount = 1000 };

       this.timer.Interval = new TimeSpan(1);

       this.timer.Tick += timer_Tick;

   }

   private IncrementalList <Employee> itemSource;

   public IncrementalList<Employee> GridItemSource

   {

       get { return itemSource; }

       set

       {

           itemSource = value;

           RaisePropertyChanged("GridItemSource");

       }

   }

   /// <summary>

   /// This method is called when the DataGrid is loaded and scrolled. 

   /// This method has the number of required data as parameter.

   /// </summary>   

   void LoadMoreItems(uint count, int baseIndex)

   {

       // Get the data from the repository.

       var data = this.respository.GetEmployeesDetails_ObservableCollection((int)count);



      // Load the data to Incremental List through “LoadItems” method.

      this.GridItemSource.LoadItems(data);

   }

}
{% endhighlight %}


{% highlight xml %}



<Window.DataContext>

<local:ViewModel/>

</Window.DataContext>





<syncfusion:SfDataGrid x:Name="dataGrid" 

                         AutoGenerateColumns="True"

                         ItemsSource="{Binding GridItemSource}"/>

{% endhighlight %}



### Limitations of Incremental Loading

* Sorting, Filtering and Grouping are applied only for loaded data.
* Summaries are calculated based on loaded data.
