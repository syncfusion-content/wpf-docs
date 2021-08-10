---
layout: post
title: Master Details View in WPF DataGrid control | Syncfusion
description: Learn here all about Master Details View support in Syncfusion WPF DataGrid (SfDataGrid) control and more.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Master Details View in WPF DataGrid (SfDataGrid)

DataGrid provides support to represent the hierarchical data in the form of nested tables using Master-Details View. You can expand or collapse the nested tables ([DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html)) by using an expander in a row or programmatically.  The number of tables nested with relations is unlimited.

![WPF DataGrid with Master Details View](Master-Details-View_images/wpf-datagrid-master-details-view.png)

## Generating Master-Details view from IEnumerable

Master-Details View’s relation can be generated for the properties of type [IEnumerable](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ienumerable) in the underlying data object contain.

Follow the below steps to generate the Master-Details View for `IEnumerable`.

* Create the data model with relations (Here, relations are `IEnumerable` type properties)
* Defining relations
  * Auto-generating relations
  * Manually defining relations 
  
  
### Create the data model with relations

Create an `Employee` class with `Sales` and `Orders` property of type [ObservableCollection](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.observablecollection-1) to form the relations. The `Sales` and `Orders` properties are defined as `ObservableCollection<SalesInfo>` and `ObservableCollection<OrderInfo>` respectively. 

{% tabs %}
{% highlight c# %}
public class SalesInfo : INotifyPropertyChanged
{
    private int _orderID;
    private string _salesID;
    private string _productName;
    private ObservableCollection<ProductInfo> products;

    public int OrderID
    {
        get { return _orderID; }
        set
        {
            _orderID = value;
            OnPropertyChanged("OrderID");
        }
    }
        
    public string SalesID
    {
        get { return _salesID; }
        set
        {
            _salesID = value;
            OnPropertyChanged("SalesID");
        }
    }
        
    public string ProductName
    {
        get { return _productName; }
        set
        {
            _productName = value;
            OnPropertyChanged("ProductName");
        }
    }
        
    public event PropertyChangedEventHandler PropertyChanged;

    private void OnPropertyChanged(String name)
    {
 
        if (PropertyChanged != null)
        {
            PropertyChanged(this, new PropertyChangedEventArgs(name));
        }
    }
}

public class OrderInfo : INotifyPropertyChanged
{
    private int orderId;
    private int _quantity;

    public int OrderID
    {
        get { return orderId; }
        set
        {
            orderId = value;
            OnPropertyChanged("OrderID");
        }
    }
        
    public int Quantity
    {
        get { return _quantity; }
        set
        {
            _quantity = value;
            OnPropertyChanged("Quantity");
        }
    }
        
    public event PropertyChangedEventHandler PropertyChanged;

    private void OnPropertyChanged(String name)
        {

            if (PropertyChanged != null)
            {
                PropertyChanged(this, new PropertyChangedEventArgs(name));
            }
        }
}

public class Employee : INotifyPropertyChanged
{
    private int _EmployeeID;
    private int _orderId;
    private string _city;
    private ObservableCollection<SalesInfo> _sales;
    private ObservableCollection<OrderInfo> _orders;

    public int EmployeeID
    {
        get { return this._EmployeeID; }
        set
        {
            this._EmployeeID = value;
            OnPropertyChanged("EmployeeID");
        }
    }
        
    public int OrderID
    {
        get { return this._orderId; }
        set
        {
            this._orderId = value;
            OnPropertyChanged("OrderID");
        }
    }

    public string City
    {
        get { return _city; }
        set
        {
            _city = value;
            OnPropertyChanged("City");
        }
    }

    public ObservableCollection<SalesInfo> Sales
    {
        get { return _sales; }
        set
        {
            _sales = value;
            OnPropertyChanged("Sales");
        }
    }
        
    public ObservableCollection<OrderInfo> Orders
    {
        get { return _orders; }
        set
        {
            _orders = value;
            OnPropertyChanged("Orders");
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    private void OnPropertyChanged(String name)
    {

        if (PropertyChanged != null)
            {
                PropertyChanged(this, new PropertyChangedEventArgs(name));
            }
        }
}
{% endhighlight %}
{% endtabs %}

Create a `ViewModel` class with `Employees` property and it is initialized with several data objects in the constructor. Similarly, the `Sales` and `Orders` property are also initialized. 

{% tabs %}
{% highlight c# %}
public class ViewModel
{
    ObservableCollection<Employee> _employees;

    public ObservableCollection<Employee> Employees
    {
        get { return _employees; }
        set { _employees = value; }
    }

    public ViewModel()
    {        
        this.GenerateOrders();
        this.GenerateSales();
        _employees = GetEmployeesDetails();
    }
    
    public ObservableCollection<Employee> GetEmployeesDetails()
    {
        var employees = new ObservableCollection<Employee>();
        employees.Add(new Employee() { EmployeeID = 1, OrderID = 1001, City = "Berlin", Orders = GetOrders(1001), Sales = GetSales(1001) });
        employees.Add(new Employee() { EmployeeID = 2, OrderID = 1002, City = "Mexico D.F.", Orders = GetOrders(1002), Sales = GetSales(1002) });
        employees.Add(new Employee() { EmployeeID = 3, OrderID = 1003, City = "London", Orders = GetOrders(1002), Sales = GetSales(1003) });
        employees.Add(new Employee() { EmployeeID = 4, OrderID = 1004, City = "BERGS", Orders = GetOrders(1002), Sales = GetSales(1004) });
        employees.Add(new Employee() { EmployeeID = 5, OrderID = 1005, City = "Mannheim", Orders = GetOrders(1002), Sales = GetSales(1005) });
        return employees;
    }

    //Orders collection is initialized here.
    ObservableCollection<OrderInfo> Orders = new ObservableCollection<OrderInfo>();

    public void GenerateOrders()
    {
        Orders.Add(new OrderInfo() { OrderID = 1001, Quantity = 10 });
        Orders.Add(new OrderInfo() { OrderID = 1001, Quantity = 10 });
        Orders.Add(new OrderInfo() { OrderID = 1002, Quantity = 20 });
        Orders.Add(new OrderInfo() { OrderID = 1002, Quantity = 20 });
        Orders.Add(new OrderInfo() { OrderID = 1003, Quantity = 50 });
        Orders.Add(new OrderInfo() { OrderID = 1004, Quantity = 70 });
        Orders.Add(new OrderInfo() { OrderID = 1005, Quantity = 20 });
        Orders.Add(new OrderInfo() { OrderID = 1005, Quantity = 20 });
    }
    
    private ObservableCollection<OrderInfo> GetOrders(int orderID)
    {
        ObservableCollection<OrderInfo> orders = new ObservableCollection<OrderInfo>();
  
        foreach (var order in Orders)
  
            if (order.OrderID == orderID)
                orders.Add(order);
        return orders;
    }

    //Sales collection is initialized here.
    ObservableCollection<SalesInfo> Sales = new ObservableCollection<SalesInfo>();
 
    public void GenerateSales()
    {
        Sales.Add(new SalesInfo() { OrderID = 1001, SalesID = "A00001", ProductName = "Bike1" });
        Sales.Add(new SalesInfo() { OrderID = 1001, SalesID = "A00002", ProductName = "Bike1" });
        Sales.Add(new SalesInfo() { OrderID = 1002, SalesID = "A00003", ProductName = "Cycle" });
        Sales.Add(new SalesInfo() { OrderID = 1003, SalesID = "A00004", ProductName = "Car" });
    }
    
    private ObservableCollection<SalesInfo> GetSales(int orderID)
    {
        ObservableCollection<SalesInfo> sales = new ObservableCollection<SalesInfo>();
 
        foreach (var sale in Sales)
 
            if (sale.OrderID == orderID)
                sales.Add(sale);
        return sales;
    }   
}
{% endhighlight %}
{% endtabs %}

### Defining relations in DataGrid 

#### Auto-generating relations

SfDataGrid will automatically generate relations and inner relations for the `IEnumerable` property types in the data object. This can be enabled by setting [SfDataGrid.AutoGenerateRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AutoGenerateRelations) to `true`.

Bind the collection created in the previous step to [SfDataGrid.ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ItemsSource) and set the [SfDataGrid.AutoGenerateRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AutoGenerateRelations) to `true`. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="True"
                        ItemsSource="{Binding Employees}" />
{% endhighlight %}
{% highlight c# %}
dataGrid.AutoGenerateRelations = true;
{% endhighlight %}
{% endtabs %}

When relations are auto-generated, you can handle the [SfDataGrid.AutoGeneratingRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event to customize or cancel the [GridViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.AutoGeneratingRelationsArgs.html#Syncfusion_UI_Xaml_Grid_AutoGeneratingRelationsArgs__ctor_Syncfusion_UI_Xaml_Grid_GridViewDefinition_System_Object_) before they are added to the [SfDataGrid.DetailsViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_DetailsViewDefinition).

Here, two relations are created from `Sales` and `Orders` collection property.

![WPF DataGrid displays Master Details View based on Auto Generated Relations](Master-Details-View_images/wpf-datagrid-auto-generated-columns.png)

#### Manually defining Relations

You can define the Master-Details View’s relation manually using [SfDataGrid.DetailsViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_DetailsViewDefinition), when the [SfDataGrid.AutoGenerateRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AutoGenerateRelations) is `false`. 

To define Master-Details View relations, create [GridViewDefinition](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html) and set the name of `IEnumerable` type property (from data object) to [ViewDefinition.RelationalColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ViewDefinition.html#Syncfusion_UI_Xaml_Grid_ViewDefinition_RelationalColumn). Then, add the `GridViewDefinition` to the [SfDataGrid.DetailsViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_DetailsViewDefinition). 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="False"
                        ItemsSource="{Binding Employees}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <!--  FirstLevelNestedGrid1 is created here  -->
        <syncfusion:GridViewDefinition RelationalColumn="Sales">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid1"
                                       AutoGenerateColumns="True"/>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
        <!--  FirstLevelNestedGrid2 is created here  -->
        <syncfusion:GridViewDefinition RelationalColumn="Orders">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid2"
                                       AutoGenerateColumns="True"/>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
dataGrid.AutoGenerateRelations = false;

var gridViewDefinition1 = new GridViewDefinition();
gridViewDefinition1.RelationalColumn = "Sales";
gridViewDefinition1.DataGrid = new SfDataGrid() { Name = "FirstLevelNestedGrid1", AutoGenerateColumns = true };

var gridViewDefinition2 = new GridViewDefinition();
gridViewDefinition2.RelationalColumn = "Orders";
gridViewDefinition2.DataGrid = new SfDataGrid() { Name = "FirstLevelNestedGrid2", AutoGenerateColumns = true };

dataGrid.DetailsViewDefinition.Add(gridViewDefinition1);
dataGrid.DetailsViewDefinition.Add(gridViewDefinition2);
{% endhighlight %}
{% endtabs %}

![WPF DataGrid displays Master Details View based on Manual Relations](Master-Details-View_images/wpf-datagrid-manual-relations.png)

In the same way, you can define relations for first level nested grids by defining relations to the [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) of first level nested grid.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="False"                        
                        ItemsSource="{Binding Employees}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <!--  FirstLevelNestedGrid is created here  -->
        <syncfusion:GridViewDefinition RelationalColumn="Orders">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid  x:Name="FirstLevelNestedGrid"
                                        AutoGenerateColumns="True"
                                        AutoGenerateRelations="False">
                    <!--  SecondLevelNestedGrid is created here  -->
                    <syncfusion:SfDataGrid.DetailsViewDefinition>
                        <syncfusion:GridViewDefinition RelationalColumn="Products">
                            <syncfusion:GridViewDefinition.DataGrid>
                                <syncfusion:SfDataGrid  x:Name="SecondLevelNestedGrid" 
                                                        AutoGenerateColumns="True" />
                            </syncfusion:GridViewDefinition.DataGrid>
                        </syncfusion:GridViewDefinition>
                    </syncfusion:SfDataGrid.DetailsViewDefinition>                   
                </syncfusion:SfDataGrid>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
dataGrid.AutoGenerateRelations = false;

// GridViewDefinition for parent DataGrid
var gridViewDefinition1 = new GridViewDefinition();
gridViewDefinition1.RelationalColumn = "Sales";
var firstLevelNestedGrid = new SfDataGrid() { Name = "FirstLevelNestedGrid", AutoGenerateColumns = true };
firstLevelNestedGrid.AutoGenerateRelations = false;

// GridViewDefinition for FirstLevelNestedGrid
var gridViewDefinition = new GridViewDefinition();
gridViewDefinition.RelationalColumn = "Products";
gridViewDefinition.DataGrid = new SfDataGrid() { Name = "SecondLevelNestedGrid", AutoGenerateColumns = true };
firstLevelNestedGrid.DetailsViewDefinition.Add(gridViewDefinition);
gridViewDefinition1.DataGrid = firstLevelNestedGrid;

dataGrid.DetailsViewDefinition.Add(gridViewDefinition1);
{% endhighlight %}
{% endtabs %}

![WPF DataGrid displays Nested Relations](Master-Details-View_images/wpf-datagrid-nested-relations.png)

## Generating Master-Details view from DataTable

Master-Details View’s relation can be generated for [DataTable](https://docs.microsoft.com/en-us/dotnet/api/system.data.datatable), when [DataRelation](https://docs.microsoft.com/en-us/dotnet/api/system.data.datarelation) is defined between two tables in underlying [DataSet](https://docs.microsoft.com/en-us/dotnet/api/system.data.dataset). 

Follow the below steps to generate the Master-Details View’s relation for DataTable,

* Create the [DataTable](https://docs.microsoft.com/en-us/dotnet/api/system.data.datatable) with relations.
* Defining relations
  * Auto-generating relations
  * Manually defining relations 
  
### Create the DataTable with relations 

Create `ViewModel` class and define the `Suppliers` property of type `DataTable`. Then, add the data relations between `Suppliers` and `Products` tables in the `DataSet` based on `SupplierID` column.

{% tabs %}
{% highlight c# %}
public class ViewModel 
{        
    private DataTable _suppliers;
    
    public DataTable Suppliers
    {
        get { return _suppliers; }
        set { _suppliers = value; }
    }

    public ViewModel()
    {
        _suppliers = GetDataTable();
    }
       
    public DataTable GetDataTable()
    {
        DataSet ds = new DataSet();
        string connectionString = string.Format(@"Data Source = {0}", ("Northwind.sdf"));
        using (SqlCeConnection con = new SqlCeConnection(connectionString))
        {
            con.Open();
            SqlCeDataAdapter sda = new SqlCeDataAdapter("SELECT * FROM Suppliers", con);
            sda.Fill(ds, "Suppliers");
        }
        using (SqlCeConnection con1 = new SqlCeConnection(connectionString))
        {
            con1.Open();
            SqlCeDataAdapter sda1 = new SqlCeDataAdapter("SELECT * FROM Products", con1);
            sda1.Fill(ds, "Products");
        }
        
        //Both tables have Supplier ID as common to make relation
        ds.Relations.Add(new DataRelation("Supplier_Product", ds.Tables[0].Columns["Supplier ID"], ds.Tables[1].Columns["Supplier ID"]));
            
        if (ds.Tables.Count > 0)
            return ds.Tables[0];

        else
            return null;
    }
}
{% endhighlight %}
{% endtabs %}

### Defining relations in DataGrid 

#### Auto-generating relations

SfDataGrid will automatically generate relations and inner relations based on relations defined in [DataSet](https://docs.microsoft.com/en-us/dotnet/api/system.data.dataset). This can be enabled by setting [SfDataGrid.AutoGenerateRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AutoGenerateRelations) to `true`.

Bind the `Suppliers` table created in the previous step to [SfDataGrid.ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ItemsSource) and set the [SfDataGrid.AutoGenerateRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AutoGenerateRelations) to `true`. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="datagrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="True"
                        ItemsSource="{Binding Suppliers}" />
{% endhighlight %}
{% highlight c# %}
dataGrid.AutoGenerateRelations = true;
{% endhighlight %}
{% endtabs %}

When relations are auto-generated, you can handle the [SfDataGrid.AutoGeneratingRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event to customize or cancel the [GridViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.AutoGeneratingRelationsArgs.html#Syncfusion_UI_Xaml_Grid_AutoGeneratingRelationsArgs__ctor_Syncfusion_UI_Xaml_Grid_GridViewDefinition_System_Object_) before they are added to the [SfDataGrid.DetailsViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_DetailsViewDefinition).

Here, Master-Details View relation is auto generated based on the `Supplier_Product` relation.

![WPF DataGrid displays Nested DataGrid](Master-Details-View_images/wpf-datagrid-nested-collection.png)

#### Manually defining Relations

You can define the Master-Details View’s relation manually using [SfDataGrid.DetailsViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_DetailsViewDefinition), when the [SfDataGrid.AutoGenerateRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AutoGenerateRelations) is `false`. 

To define Master-Details View relations, create [GridViewDefinition](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html) and set the relation name `Supplier_Product` to [ViewDefinition.RelationalColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ViewDefinition.html#Syncfusion_UI_Xaml_Grid_ViewDefinition_RelationalColumn). Then, the `GridViewDefinition` is added to the [SfDataGrid.DetailsViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_DetailsViewDefinition) collection of parent DataGrid.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid Name="dataGrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="False"
                        ItemsSource="{Binding Suppliers}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="Supplier_Product">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid" AutoGenerateColumns="True" />
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
dataGrid.AutoGenerateRelations = false;

// GridViewDefinition for DataGrid
var gridViewDefinition = new GridViewDefinition();
gridViewDefinition.RelationalColumn = "Supplier_Product";
gridViewDefinition.DataGrid = new SfDataGrid() { Name = "FirstLevelNestedGrid", AutoGenerateColumns = true };
this.dataGrid.DetailsViewDefinition.Add(gridViewDefinition);
{% endhighlight %}
{% endtabs %}

![WPF DataGrid displays Master Details View based on Manual Relations](Master-Details-View_images/wpf-datagrid-hierarchical-view.png)

## Populating Master-Details view through events

You can load `ItemsSource` for [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) asynchronously by handling [SfDataGrid.DetailsViewExpanding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html). You can set ItemsSource in on-demand when expanding record through [GridDetailsViewExpandingEventArgs.DetailsViewItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridDetailsViewExpandingEventArgs.html#Syncfusion_UI_Xaml_Grid_GridDetailsViewExpandingEventArgs_DetailsViewItemsSource) property in the [SfDataGrid.DetailsViewExpanding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       AutoGenerateRelations="True"
                       ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% highlight c# %}
this.dataGrid.DetailsViewExpanding += dataGrid_DetailsViewExpanding;

void dataGrid_DetailsViewExpanding(object sender, Syncfusion.UI.Xaml.Grid.GridDetailsViewExpandingEventArgs e)
{
    e.DetailsViewItemsSource.Clear();      
    var itemsSource = GetItemSource();
    e.DetailsViewItemsSource.Add("ProductDetails", Products);   
}

private ObservableCollection<ProductInfo> GetItemSource()
{
    Products = new ObservableCollection<ProductInfo>();    
    Products.Add(new ProductInfo() { OrderID = 1001, ProductName = "Bike" });
    Products.Add(new ProductInfo() { OrderID = 1002, ProductName = "Car" });
    Products.Add(new ProductInfo() { OrderID = 1003, ProductName = "Bike1" });             
    return Products;
}
{% endhighlight %}
{% endtabs %}

N> This event will be trigged only when underlying data object contains relations. Otherwise, you have to define dummy relation to notify DataGrid to fire this event.

In the below code snippet, `AutoGenerateRelations` set to false and also relation is defined with some name to `RelationalColumn`. For example, `ProductDetails` is the dummy relational column and underlying data object does not contain the `IEnumerable` type property with name `ProductDetails`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       AutoGenerateRelations="False"
                       ItemsSource="{Binding Orders}">
            <syncfusion:SfDataGrid.DetailsViewDefinition>
                <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
                    <syncfusion:GridViewDefinition.DataGrid>
                        <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"  
                                               AutoGenerateColumns="True" />
                    </syncfusion:GridViewDefinition.DataGrid>
                </syncfusion:GridViewDefinition>
            </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

Now the `ItemsSource` for [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) can be supplied through [DetailsViewExpanding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event as mentioned above.

### Loading DetailsViewItemsSource asynchronously

While populating Master-Details view through events, if the data to be loaded is downloaded from an external source or being read from a file, you may get a time delay. In such case, the `DetailsViewExpanding` event will be executed before the I/O processes get completes.

In this case, you can use [async](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async) and [await](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async) to load the data with a time delay and hold the event from executing before the data gets loaded from an external source gets completed.

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewExpanding += dataGrid_DetailsViewExpanding;

private async Task<ObservableCollection<ProductInfo>> GetItemSource()
{
     var products = new ObservableCollection<ProductInfo>();
     await Schedule(() =>
     {
          products.Add(new ProductInfo() { OrderID = 1001, ProductName = "Bike" });
          products.Add(new ProductInfo() { OrderID = 1002, ProductName = "Car" });
          products.Add(new ProductInfo() { OrderID = 1003, ProductName = "Bike1" });
     }, 2000);
     return products;
}

public async Task<bool> Schedule(Action _onCompletion, int durationMS)
{ 
    DispatcherTimer timer = new DispatcherTimer();
    timer.Interval = TimeSpan.FromMilliseconds(durationMS);

    //Task that causes time delay
    timer.Tick += timer_Tick;            
    _onCompletion();
    timer.Stop();
    return true;
}


async void dataGrid_DetailsViewExpanding(object sender, Syncfusion.UI.Xaml.Grid.GridDetailsViewExpandingEventArgs e)
{
      e.DetailsViewItemsSource.Clear();
      var itemsSource = await GetItemSource();
      e.DetailsViewItemsSource.Add("ProductDetails", itemsSource);
}

{% endhighlight %}
{% endtabs %}


The declaration of `await` with `GetItemSource` method hold the further process of adding the `DetailsViewItemsSource` until the items are assigned to the `ItemsSource`. Here the timer is invoked with 2 seconds delay in asynchronous `Schedule` method call in `GetItemSource` method while adding the DetailsViewDataGrid items.

The `DetailsViewExpanding` method runs synchronously until it reaches its first await expression. After await is reached, it is suspended until the awaited task is complete.

## Defining properties for DetailsViewDataGrid

You can set properties like `AllowEditing`, `AllowFiltering` and `AllowSorting` for [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) by using the [GridViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) property.

### When AutoGenerateRelations is false

For manually defined relation, the properties can be directly set to the [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid).

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       AutoGenerateRelations="False"
                       ItemsSource="{Binding Orders}">
            <syncfusion:SfDataGrid.DetailsViewDefinition>
                <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
                    <syncfusion:GridViewDefinition.DataGrid>
                        <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"
                                               AllowEditing="True"
                                               AllowFiltering="True"
                                               AllowResizingColumns="True"
                                               AllowSorting="True"
                                               AutoGenerateColumns="False" />
                    </syncfusion:GridViewDefinition.DataGrid>
                </syncfusion:GridViewDefinition>
            </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
FirstLevelNestedGrid.AllowEditing = true;
FirstLevelNestedGrid.AllowFiltering = true;
FirstLevelNestedGrid.AllowResizingColumns = true;
FirstLevelNestedGrid.AllowSorting = true;
{% endhighlight %}
{% endtabs %}

For two levels of nesting,

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       AutoGenerateRelations="False"
                       ItemsSource="{Binding Employees}">
            <syncfusion:SfDataGrid.DetailsViewDefinition>
            <!--  FirstLevelNestedGrid is created here  -->
                <syncfusion:GridViewDefinition RelationalColumn="Sales">
                    <syncfusion:GridViewDefinition.DataGrid>
                        <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"
                                               AutoGenerateColumns="True"
                                               AutoGenerateRelations="False">
                            <syncfusion:SfDataGrid.DetailsViewDefinition>
                            <!--  SecondLevelNestedGrid is created here  -->
                                <syncfusion:GridViewDefinition 
                                                RelationalColumn="Products">
                                    <syncfusion:GridViewDefinition.DataGrid>
                                        <syncfusion:SfDataGrid 
                                                    x:Name="SecondLevelNestedGrid"       
                                                    AllowEditing="True"
                                                    AllowFiltering="True"
                                                    AutoGenerateColumns="True" />           
                                    </syncfusion:GridViewDefinition.DataGrid>
                                </syncfusion:GridViewDefinition>
                            </syncfusion:SfDataGrid.DetailsViewDefinition>
                        </syncfusion:SfDataGrid>
                    </syncfusion:GridViewDefinition.DataGrid>
                </syncfusion:GridViewDefinition>
            </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
SecondLevelNestedGrid.AllowEditing = true;
SecondLevelNestedGrid.AllowFiltering = true;
{% endhighlight %}
{% endtabs %}


### When AutoGenerateRelations is true

When the relation is auto-generated, you can get the [GridViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) in the [AutoGeneratingRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler to set the properties.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       AutoGenerateRelations="True"
                       ItemsSource="{Binding Employees}"/>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.AutoGeneratingRelations += dataGrid_AutoGeneratingRelations;

void dataGrid_AutoGeneratingRelations(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingRelationsArgs e)
{
     e.GridViewDefinition.DataGrid.AllowEditing = true;
     e.GridViewDefinition.DataGrid.AllowFiltering = true;
     e.GridViewDefinition.DataGrid.AllowSorting = true;
     e.GridViewDefinition.DataGrid.AllowResizingColumns = true;        
}
{% endhighlight %}
{% endtabs %}

For two levels of nesting,

{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingRelations += dataGrid_AutoGeneratingRelations;

void dataGrid_AutoGeneratingRelations(object sender, AutoGeneratingRelationsArgs e)
{
     e.GridViewDefinition.DataGrid.AutoGenerateRelations = true;
     e.GridViewDefinition.DataGrid.AutoGeneratingRelations +=  
                                       FirstLevelNestedGrid_AutoGeneratingRelations;
}

Void FirstLevelNestedGrid_AutoGeneratingRelations(object sender,
                               AutoGeneratingRelationsArgs e)   
{
     e.GridViewDefinition.DataGrid.AutoGenerateColumns = true;
     e.GridViewDefinition.DataGrid.AllowEditing = true;
     e.GridViewDefinition.DataGrid.AllowFiltering = true;
}
{% endhighlight %}
{% endtabs %}


N> When you make any change in one [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html), that change will be applied to all [DetailsViewDataGrid’s](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) in the same level. For example, when you resize the first column in one [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html), the same column width is applied to all [DetailsViewDataGrid’s](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) at that level. This is applicable for features like filtering, sorting, grouping and re-ordering columns also. 

![WPF DataGrid in Master Details View](Master-Details-View_images/wpf-datagrid-details-view.png)

Here, `SalesID` column is sorted in all DetailsViewDataGrid at the same level.

N> [AllowFrozenGroupHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AllowFrozenGroupHeaders) , [FrozenRowsCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_FrozenRowsCount), [FooterRowsCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_FooterRowsCount), [FooterColumnCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FooterColumnCount), [FrozenColumnCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FrozenColumnCount) properties are not supported while using Master Details view.

## Defining columns for DetailsViewDataGrid

The [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid)’s columns can be generated either automatically or manually like parent DataGrid. You can refer [here](http://help.syncfusion.com/wpf/sfdatagrid/columns) to know more about columns. 

### Auto-generating columns

You can auto-generate the [ViewDefinition.DataGrid’s](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) columns by setting the [GridViewDefinition.DataGrid.AutoGenerateColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AutoGenerateColumns) to `true`. You can `cancel` or `customize` the column being created for [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) by handling [GridViewDefinition.DataGrid.AutoGeneratingColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                        
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="False"
                        ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"
                                        AutoGenerateColumns="True"      
										AutoGeneratingColumn="FirstLevelNestedGrid_AutoGeneratingColumn" />
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}

FirstLevelNestedGrid.AutoGeneratingColumn += FirstLevelNestedGrid_AutoGeneratingColumn;

{% endhighlight %}
{% endtabs %}

When relation is auto generated, you can set properties and wire [GridViewDefinition.DataGrid.AutoGeneratingColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event in [SfDataGrid.AutoGeneratingRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler.

{% tabs %}
{% highlight c# %}
void dataGrid_AutoGeneratingRelations(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingRelationsArgs e)
{    
     e.GridViewDefinition.DataGrid.AutoGenerateColumns = true;       
     e.GridViewDefinition.DataGrid += FirstLevelNestedGrid_AutoGeneratingColumn;
}
{% endhighlight %}
{% endtabs %}

### Manually defining columns

You can directly define the columns to [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) when [AutoGenerateColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AutoGenerateColumns) is `false`. When relation is manually defined, you can define the columns directly to `ViewDefinition.DataGrid` in XAML or C#, by adding desired column to the [SfDataGrid.Columns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Columns) collection.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       AutoGenerateRelations="False"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"   AutoGenerateColumns="False">
                    <syncfusion:SfDataGrid.Columns>
                        <syncfusion:GridTextColumn MappingName="OrderID" />
                        <syncfusion:GridTextColumn MappingName="ProductName" />
                    </syncfusion:SfDataGrid.Columns>
                </syncfusion:SfDataGrid>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

When relation is auto generated, you can define the [ViewDefinition.DataGrid’s](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) columns manually through the [SfDataGrid.AutoGeneratingRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler.

{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingRelations += dataGrid_AutoGeneratingRelations;

void dataGrid_AutoGeneratingRelations(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingRelationsArgs e)
{
    e.GridViewDefinition.DataGrid.AutoGenerateColumns = false;
    e.GridViewDefinition.DataGrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID" });
    e.GridViewDefinition.DataGrid.Columns.Add(new GridTextColumn() { MappingName = "ProductName" });
}
{% endhighlight %}
{% endtabs %}

### Creating Custom Column

You can also define your own column type to [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) like parent DataGrid. For more information about creating custom column, refer the [Custom Column support](http://help.syncfusion.com/wpf/sfdatagrid/columns). 

After creating the custom column, add the customized renderer to [CellRenderers](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CellRenderers) collection of [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html).

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewLoading += dataGrid_DetailsViewLoading;
void dataGrid_DetailsViewLoading(object sender, DetailsViewLoadingAndUnloadingEventArgs e)
{

     if (!e.DetailsViewDataGrid.CellRenderers.ContainsKey("DatePickerRenderer"))
         e.DetailsViewDataGrid.CellRenderers.Add("DatePickerRenderer", new DatePickerRenderer());
}
{% endhighlight %}
{% endtabs %}

Now, you can add the custom column to `Columns` collection of [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid).

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="False"
                        ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"
                                        AllowEditing="True"
                                        AutoGenerateColumns="False">
                    <syncfusion:SfDataGrid.Columns>
                        <syncfusion:GridTextColumn MappingName="OrderID" />
                        <syncfusion:GridTextColumn MappingName="ProductName" />
                        <local:DatePickerColumn DateMapping="DateOfMonth"
                                                DisplayBinding="{Binding DateOfMonth,
                                                                            Converter={StaticResource converter}}"
                                                MappingName="DateOfMonth" />
                    </syncfusion:SfDataGrid.Columns>
                </syncfusion:SfDataGrid>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

![WPF DataGrid with Editing in Master Details View](Master-Details-View_images/wpf-datagrid-editing.png)

## Handling events for DetailsViewDataGrid

You can handle [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) events by wiring events to [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) where sender is `ViewDefinition.DataGrid`. In another way, you can handle `DetailsViewDataGrid` events also through `ParentDataGrid` events by setting [NotifyEventsToParentDataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_NotifyEventsToParentDataGrid) property of `ViewDefinition.DataGrid`. For more information refer [Listen DetailsViewDataGrid event from ParentDataGrid event handler](https://help.syncfusion.com/wpf/sfdatagrid/master-details-view#listen-detailsviewdatagrid-event-in-parentdatagrid-event-handler) section. 

### When AutoGenerateRelations is false

For manually defined relation, the events can be wired from [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) directly in XAML or C#.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       AutoGenerateRelations="True"
                       ItemsSource="{Binding Orders}">
            <syncfusion:SfDataGrid.DetailsViewDefinition>
                <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
                    <syncfusion:GridViewDefinition.DataGrid>
                        <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"
                                               AutoGenerateColumns="True"   
											   CurrentCellBeginEdit="FirstLevelNestedGrid_CurrentCellBeginEdit"                             
											   FilterChanging="FirstLevelNestedGrid_FilterChanging"     
											   SortColumnsChanging="FirstLevelNestedGrid_SortColumnsChanging" />
                    </syncfusion:GridViewDefinition.DataGrid>
                </syncfusion:GridViewDefinition>
            </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
FirstLevelNestedGrid.CurrentCellBeginEdit += FirstLevelNestedGrid_CurrentCellBeginEdit;
FirstLevelNestedGrid.SortColumnsChanging += FirstLevelNestedGrid_SortColumnsChanging;
FirstLevelNestedGrid.FilterChanging += FirstLevelNestedGrid_FilterChanging;
{% endhighlight %}
{% endtabs %}

For second level nested grid,

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       AutoGenerateRelations="False"
                       ItemsSource="{Binding Employees}">
            <syncfusion:SfDataGrid.DetailsViewDefinition>
                <syncfusion:GridViewDefinition RelationalColumn="Sales">
                    <syncfusion:GridViewDefinition.DataGrid>
                        <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"
                                               AutoGenerateColumns="True"
                                               AutoGenerateRelations="False">
                            <syncfusion:SfDataGrid.DetailsViewDefinition>
                                <syncfusion:GridViewDefinition 
                                                           RelationalColumn="Products">
                                    <syncfusion:GridViewDefinition.DataGrid>
                                        <syncfusion:SfDataGrid 
                                               x:Name="SecondLevelNestedGrid"
                                               AllowFiltering="True"
                                               AutoGenerateColumns="True"
											  CurrentCellBeginEdit="SecondLevelNestedGrid_CurrentCellBeginEdit"    
											  FilterChanging="SecondLevelNestedGrid_FilterChanging"/>
                                    </syncfusion:GridViewDefinition.DataGrid>
                                </syncfusion:GridViewDefinition>
                            </syncfusion:SfDataGrid.DetailsViewDefinition>
                        </syncfusion:SfDataGrid>
                    </syncfusion:GridViewDefinition.DataGrid>
                </syncfusion:GridViewDefinition>                
            </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
SecondLevelNestedGrid.CurrentCellBeginEdit+=
                                           SecondLevelNestedGrid_CurrentCellBeginEdit;
SecondLevelNestedGrid.FilterChanging += SecondLevelNestedGrid_FilterChanging;

private void SecondLevelNestedGrid_CurrentCellBeginEdit(object sender, CurrentCellBeginEditEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}

### When AutoGenerateRelations is true

When the relation is auto-generated, you can get the [GridViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) in the [AutoGeneratingRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler to wire the events.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       AutoGenerateRelations="True"
                       ItemsSource="{Binding Employees}"/>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.AutoGeneratingRelations += dataGrid_AutoGeneratingRelations;

void dataGrid_AutoGeneratingRelations(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingRelationsArgs e)
{
        e.GridViewDefinition.DataGrid.CurrentCellBeginEdit +=  
                                    FirstLevelNestedGrid_CurrentCellBeginEdit;
        e.GridViewDefinition.DataGrid.SortColumnsChanging +=
                                    FirstLevelNestedGrid_SortColumnsChanging;
        e.GridViewDefinition.DataGrid.FilterChanging += 
                                    FirstLevelNestedGrid_FilterChanging;
}

void FirstLevelNestedGrid_CurrentCellBeginEdit(object sender, 
                                    CurrentCellBeginEditEventArgs args)
{
}

{% endhighlight %}
{% endtabs %}

For second level nested grid, 

{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingRelations += dataGrid_AutoGeneratingRelations;

void dataGrid_AutoGeneratingRelations(object sender, AutoGeneratingRelationsArgs e)
{

     // FirstLevelNestedGrid
     e.GridViewDefinition.DataGrid.AutoGenerateRelations = true;
     e.GridViewDefinition.DataGrid.AutoGeneratingRelations +=                                              
                                         FirstLevelNestedGrid_AutoGeneratingRelations;
}
void FirstLevelNestedGrid_AutoGeneratingRelations(object sender,  
                                                        AutoGeneratingRelationsArgs e)
{

     // SecondLevelNestedGrid
     e.GridViewDefinition.DataGrid.CurrentCellBeginEdit +=
                                       SecondLevelNestedGrid_CurrentCellBeginEdit;  
     e.GridViewDefinition.DataGrid.FilterChanging += 
                                       SecondLevelNestedGrid_FilterChanging;
}
{% endhighlight %}
{% endtabs %}

### Listen DetailsViewDataGrid event in ParentDataGrid event handler

You can listen `DetailsViewDataGrid` events in `ParentDataGrid` event handlers itself by setting [NotifyEventsToParentDataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_NotifyEventsToParentDataGrid) property of `ViewDefinition.DataGrid`. So, you don’t have to listen events for each level as discussed above.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid.DetailsViewDefinition>
                <syncfusion:GridViewDefinition RelationalColumn="OrderDetails">
                    <syncfusion:GridViewDefinition.DataGrid>
                        <syncfusion:SfDataGrid x:Name="FirstDetailsViewGrid"
                                            AllowEditing="True"
                                            AutoGenerateColumns="True"
                                            NotifyEventsToParentDataGrid="True">
                        </syncfusion:SfDataGrid>
                    </syncfusion:GridViewDefinition.DataGrid>
                </syncfusion:GridViewDefinition>
</syncfusion:SfDataGrid.DetailsViewDefinition>
{% endhighlight %}
{% endtabs %}

You can wire the events in `ParentDataGrid` and get the corresponding `DetailsViewDataGrid` in `ParentDataGrid EventArgs`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid Name="datagrid"                             
                       ItemsSource="{Binding Source}"
                       AllowEditing="True"
                       RowValidating="Datagrid_RowValidating">
{% endhighlight %}
{% highlight c# %}
this.datagrid.RowValidating += Datagrid_RowValidating;

private void Datagrid_RowValidating(object sender, RowValidatingEventArgs e)
{
    var detailsViewDataGrid = e.OriginalSender as DetailsViewDataGrid;
}
{% endhighlight %}
{% endtabs %}

You can get the `SourceDataGrid` in `ParentDataGrid` events using [GetSourceDataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Helpers.GridHelper.html#Syncfusion_UI_Xaml_Grid_Helpers_GridHelper_GetSourceDataGrid_Syncfusion_UI_Xaml_Grid_DetailsViewDataGrid_) helper method.

{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid.Helpers;
var sourceDataGrid = (e.OriginalSender as DetailsViewDataGrid).GetSourceDataGrid();  
{% endhighlight %}
{% endtabs %}

Refer [here](https://help.syncfusion.com/wpf/sfdatagrid/selection#getting-the-parent-of-detailsviewdatagrid) for get the `ParentDataGrid` using [GetParentDataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Helpers.SelectionHelper.html#Syncfusion_UI_Xaml_Grid_Helpers_SelectionHelper_GetParentDataGrid_Syncfusion_UI_Xaml_Grid_SfDataGrid_) helper method.

### Binding DetailsViewDataGrid event to command in ViewModel

You can bind the `DetailsViewDataGrid`  events using commands by setting [NotifyEventsToParentDataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_NotifyEventsToParentDataGrid) property of  `ViewDefinition.DataGrid`. Using this property, listen the `DetailsViewDataGrid` events in `ParentDataGrid` event handler.
Bind the events using commands in `ViewModel` as like below.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid Name="datagrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Source}"
                       AllowEditing="True">
            <i:Interaction.Triggers>
                <i:EventTrigger EventName="RowValidating">
                    <i:InvokeCommandAction Command="{Binding Path=RowValidating}"/>
                </i:EventTrigger>
            </i:Interaction.Triggers>
            <syncfusion:SfDataGrid.DetailsViewDefinition>
                <syncfusion:GridViewDefinition RelationalColumn="OrderDetails">
                    <syncfusion:GridViewDefinition.DataGrid>
                        <syncfusion:SfDataGrid x:Name="FirstDetailsViewGrid"
                                            AllowEditing="True"
                                            AutoGenerateColumns="True"
                                            NotifyEventsToParentDataGrid="True">
                        </syncfusion:SfDataGrid>
                    </syncfusion:GridViewDefinition.DataGrid>
                </syncfusion:GridViewDefinition>
            </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ViewModel : INotifyPropertyChanged
{   
    private ICommand _rowValidatingCommand;

    public ICommand RowValidating
    {
        get
        {
            return _rowValidatingCommand ?? (_rowValidatingCommand = new CommandHandler(() => RowValidatingEvent(), true));
        }
    }     

    public void RowValidatingEvent()
    {

    }
}

public class CommandHandler : ICommand
{
    private Action _action;
    private bool _canExecute;

    public CommandHandler(Action action, bool canExecute)
    {
        _action = action;
        _canExecute = canExecute;
    }

    public bool CanExecute(object parameter)
    {
        return _canExecute;
    }

    public event EventHandler CanExecuteChanged;

    public void Execute(object parameter)
    {
        _action();
    }
}
{% endhighlight %}
{% endtabs %}

### Getting the parent DataGrid while editing DetailsViewDataGrid

You can get the corresponding parent DataGrid while editing [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) through its [CurrentCellBeginEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler. 

{% tabs %}
{% highlight c# %}
this.FirstLevelNestedGrid.CurrentCellBeginEdit += FirstLevelNestedGrid_CurrentCellBeginEdit;

void FirstLevelNestedGrid_CurrentCellBeginEdit(object sender, CurrentCellBeginEditEventArgs args)
{
    var detailsViewDataGrid = args.OriginalSender as DetailsViewDataGrid;
    var parentDataGrid = detailsViewDataGrid.GetParentDataGrid();
}
{% endhighlight %}
{% endtabs %}

Here, sender is [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid). You can get the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) which actually raises the event by using [OriginalSender](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCancelEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCancelEventArgs_OriginalSender). 

## Column sizing 

SfDataGrid allows you to apply column sizer to `DetailsViewDataGrid` by setting the [GridViewDefinition.DataGrid.ColumnSizer](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ColumnSizer) like parent DataGrid. For more information, refer the [Column Sizing](https://help.syncfusion.com/wpf/datagrid/autosize-columns) section.

### Disable resizing of last column in parent DataGrid 

By default, the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) is clipped while resizing the last column of parent DataGrid if the parent DataGrid width is less than the `DetailsViewDataGrid` width. 

You can disable the resizing of last column of parent DataGrid by setting [DetailsViewManager.DisableLastColumnResizing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewManager.html#Syncfusion_UI_Xaml_Grid_DetailsViewManager_DisableLastColumnResizingProperty) attached property to `true`. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowResizingColumns="True"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="True"
                        ItemsSource="{Binding Orders}"
                        syncfusion:DetailsViewManager.DisableLastColumnResizing="True" />
{% endhighlight %}
{% highlight c# %}
DetailsViewManager.SetDisableLastColumnResizing(this.dataGrid, true);
{% endhighlight %}
{% endtabs %}

### Resizing parent DataGrid and DetailsViewDataGrid simultaneously

By default, [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) column width will not be adjusted while resizing the parent DataGrid’s columns. You can adjust DetailsViewDataGrid’s column width simultaneously while resizing parent DataGrid. This can be achieved by handling [DetailsViewLoading](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) and [ResizingColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) events.

N> It is applicable only when the parent and [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) having same number of columns.

The column width of `DetailsViewDataGrid` is set based on the parent DataGrid’s column in [DetailsViewLoading](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

{% tabs %}
{% highlight c# %}
dataGrid.DetailsViewLoading += dataGrid_DetailsViewLoading;

void dataGrid_DetailsViewLoading(object sender, DetailsViewLoadingAndUnloadingEventArgs e)
{
    var parentGrid = e.OriginalSender is DetailsViewDataGrid ? (e.OriginalSender as SfDataGrid) : sender as SfDataGrid;

    if (!CanResize(parentGrid))
        return;

    if (parentGrid.Columns.Count != e.DetailsViewDataGrid.Columns.Count)
        return;
    double width = 0;
    var detailsViewStartColumnIndex = e.DetailsViewDataGrid.ResolveToStartColumnIndex();   

    for (int i = 0; i < parentGrid.Columns.Count; i++)
    {
        width = i == 0 ? parentGrid.Columns[i].ActualWidth - detailsViewStartColumnIndex * 24 : parentGrid.Columns[i].Width;

        if (e.DetailsViewDataGrid.Columns[i].Width != parentGrid.Columns[i].Width)
            e.DetailsViewDataGrid.Columns[i].Width = width;
    }            
}
{% endhighlight %}
{% endtabs %}

When the column is resized in parent DataGrid column, then the new [Width](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_Width) is set to corresponding column of [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) based on the [ColumnIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ResizingColumnsEventArgs.html#Syncfusion_UI_Xaml_Grid_ResizingColumnsEventArgs_ColumnIndex) argument in [ResizingColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

{% tabs %}
{% highlight c# %}

dataGrid.ResizingColumns += dataGrid_ResizingColumns;

void dataGrid_ResizingColumns(object sender, ResizingColumnsEventArgs e)
{
    var grid = sender as SfDataGrid;          

    if (e.OriginalSender is DetailsViewDataGrid)
        grid = e.OriginalSender as SfDataGrid;

    if (grid.View == null)
        return;
    SetWidth(grid, e.ColumnIndex, e.Width);
}

private void SetWidth(SfDataGrid grid, int scrollColumnIndex, double width)
{
    if (grid.DetailsViewDefinition == null || !grid.DetailsViewDefinition.Any())
        return;
    if (!CanResize(grid))
        return;
    var columnIndex = grid.HelperResolveToGridVisibleColumnIndex(scrollColumnIndex);

    if (columnIndex < 0)
        return;
    var parentStartColumnIndex = grid.HelperResolveToStartColumnIndex();
    var indentColumnsWidth = 0;

    foreach (var definition in grid.DetailsViewDefinition)
    {
        var detailsViewDataGrid = (definition as GridViewDefinition).DataGrid;
        var startColumnIndex = detailsViewDataGrid.HelperResolveToStartColumnIndex();
        indentColumnsWidth = startColumnIndex * 24;
        var tempWidth = width - indentColumnsWidth < 0 ? 0 : width - indentColumnsWidth;
        detailsViewDataGrid.Columns[columnIndex].Width = scrollColumnIndex == parentStartColumnIndex ? tempWidth : width;

        // If DetailsViewDataGrid has DetailsViewDefinition(nested levels), recursively set width upto all levels

        if (detailsViewDataGrid.DetailsViewDefinition != null && detailsViewDataGrid.DetailsViewDefinition.Any())
            SetWidth(detailsViewDataGrid, detailsViewDataGrid.HelperResolveToScrollColumnIndex(columnIndex), detailsViewDataGrid.Columns[columnIndex].Width);
    }
}

private bool CanResize(SfDataGrid dataGrid)
{

    if (dataGrid.DetailsViewDefinition == null && !dataGrid.DetailsViewDefinition.Any())
        return true;

    foreach (var definition in dataGrid.DetailsViewDefinition)
    {
        var detailsViewGrid = (definition as GridViewDefinition).DataGrid;

        if (detailsViewGrid.DetailsViewDefinition == null && !detailsViewGrid.DetailsViewDefinition.Any())
            return CanResize(detailsViewGrid);

        if (detailsViewGrid.Columns.Count != dataGrid.Columns.Count)
            return false;
    }
    return true;
}
{% endhighlight %}
{% endtabs %}

The above `HelperResolveToStartColumnIndex`, `HelperResolveToGridVisibleColumnIndex`, `HelperResolveToScrollColumnIndex` helper methods are used to resolve row and column index in [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid).

{% tabs %}
{% highlight c# %}
public static class GridHelperClass
{
    /// <summary>
    /// Resolves the start column index of the ViewDefinition.DataGrid.
    /// </summary>
    /// <param name="dataGrid">
    /// The ViewDefinition.DataGrid
    /// </param>
    /// <returns>
    /// Returns the start column index of the ViewDefinition.DataGrid.
    /// </returns>

    public static int HelperResolveToStartColumnIndex(this SfDataGrid dataGrid)
    {
        int startIndex = 0;

        if (dataGrid.ShowRowHeader)
            startIndex += 1;

        if (dataGrid.GroupColumnDescriptions != null && dataGrid.GroupColumnDescriptions.Any())
            startIndex += dataGrid.GroupColumnDescriptions.Count;

        if (dataGrid.DetailsViewDefinition != null && dataGrid.DetailsViewDefinition.Any())
            startIndex += 1;
        return startIndex;
    }

    /// <summary>
    /// Resolves the visible column index for the specified column index in ViewDefinition.DataGrid.
    /// </summary>
    /// <param name="dataGrid">
    /// The ViewDefinition.DataGrid.
    /// </param>
    /// <param name="visibleColumnIndex">
    /// The visibleColumnIndex.
    /// </param>
    /// <returns>
    /// Returns the corresponding visible column index for the specified column index.
    /// </returns>
 
    public static int HelperResolveToGridVisibleColumnIndex(this SfDataGrid dataGrid, int visibleColumnIndex)
    {
        var indentColumnCount = (dataGrid.GroupColumnDescriptions != null ? dataGrid.GroupColumnDescriptions.Count : 0) +
            ((dataGrid.DetailsViewDefinition != null && dataGrid.DetailsViewDefinition.Any()) ? 1 : 0);
        int resolvedIndex = visibleColumnIndex - (indentColumnCount + (dataGrid.ShowRowHeader ? 1 : 0));
        return resolvedIndex;
    }

    /// <summary>
    /// Resolves the scroll column index for the specified column index in ViewDefinition.DataGrid.
    /// </summary>
    /// <param name="dataGrid">
    /// The ViewDefinition.DataGrid.
    /// </param>
    /// <param name="gridColumnIndex">
    /// The corresponding column index to get the scroll column index.
    /// </param>
    /// <returns>
    /// Returns the scroll column index for the specified column index.
    /// </returns>
 
    public static int HelperResolveToScrollColumnIndex(this SfDataGrid dataGrid, int gridColumnIndex)
    {
        var indentColumnCount = ((dataGrid.DetailsViewDefinition != null && dataGrid.DetailsViewDefinition.Any()) ? 1 : 0) +
            (dataGrid.GroupColumnDescriptions != null ? dataGrid.GroupColumnDescriptions.Count : 0);
        return ((dataGrid.ShowRowHeader ? 1 : 0) + indentColumnCount) + gridColumnIndex;
    }
}
{% endhighlight %}
{% endtabs %}

You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/WPF96131267.zip).

N> To display parent and [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) in the same line, set [DetailsViewPadding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_DetailsViewPadding) as `Zero`.

## Selection

[DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) allows you to select rows or cells based on the [SelectionUnit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectionUnit) property in its parent DataGrid. 

### Getting the selected DetailsViewDataGrid

You can get the currently selected [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) by using the [SelectedDetailsViewGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectedDetailsViewGrid) property of parent DataGrid.

{% tabs %}
{% highlight c# %}
var detailsViewDataGrid = this.dataGrid.SelectedDetailsViewGrid;
{% endhighlight %}
{% endtabs %}

For accessing nested level [SelectedDetailsViewGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectedDetailsViewGrid),

{% tabs %}
{% highlight c# %}
var detailsViewDataGrid = this.dataGrid.SelectedDetailsViewGrid.SelectedDetailsViewGrid;
{% endhighlight %}
{% endtabs %}

You can also get the selected [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) using [GetDataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Helpers.SelectionHelper.html#Syncfusion_UI_Xaml_Grid_Helpers_SelectionHelper_GetDataGrid_Syncfusion_UI_Xaml_Grid_SfDataGrid_) helper method which returns the DataGrid that contains the current cell.

{% tabs %}
{% highlight c# %}
var detailsViewDataGrid = this.dataGrid.GetDataGrid();
{% endhighlight %}
{% endtabs %}

### Getting the SelectedItem, SelectedItems and SelectedIndex of DetailsViewDataGrid

You can access the selected record or records and selected record index of `DetailsViewDataGrid` by using [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItem), [SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems) and [SelectedIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedIndex) properties directly.

{% tabs %}
{% highlight c# %}
var detailsViewDataGrid = this.dataGrid.GetDetailsViewGrid(2);
int selectedIndex = detailsViewDataGrid.SelectedIndex;
var selectedItem = detailsViewDataGrid.SelectedItem;
var selectedItems = detailsViewDataGrid.SelectedItems;
{% endhighlight %}
{% endtabs %}

You can access DetailsViewDataGrid’s [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItem), [SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems) and [SelectedIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedIndex) properties by using parent dataGrid’s `SelectedDetailsViewGrid` property also.

{% tabs %}
{% highlight c# %}
int selectedIndex = this.dataGrid.SelectedDetailsViewGrid.SelectedIndex;
var selectedItem = this.dataGrid.SelectedDetailsViewGrid.SelectedItem;
var selectedItems = this.dataGrid.SelectedDetailsViewGrid.SelectedItems;
{% endhighlight %}
{% endtabs %}

### Getting the CurrentCell of DetailsViewDataGrid

You can get the [CurrentCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCurrentCellManager.html#Syncfusion_UI_Xaml_Grid_GridCurrentCellManager_CurrentCell) of [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) by using the [SelectedDetailsViewGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectedDetailsViewGrid) property of parent DataGrid or [CurrentCellBeginEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event of `DetailsViewDataGrid`.

{% tabs %}
{% highlight c# %}
var currentCell = this.dataGrid.SelectedDetailsViewGrid.SelectionController.CurrentCellManager.CurrentCell;
this.FirstLevelNestedGrid.CurrentCellBeginEdit += FirstLevelNestedGrid_CurrentCellBeginEdit;

void FirstLevelNestedGrid_CurrentCellBeginEdit(object sender, CurrentCellBeginEditEventArgs args)
{
    var detailsViewDataGrid = args.OriginalSender as DetailsViewDataGrid;
    var currentCell = detailsViewDataGrid.SelectionController.CurrentCellManager.CurrentCell;
}
{% endhighlight %}
{% endtabs %}

You can refer [here](#handling-events-for-detailsviewdatagrid) to know about handling events for `DetailsViewDataGrid`.

### Getting the parent DataGrid

You can get the immediate parent DataGrid of corresponding [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) through [GetParentDataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Helpers.SelectionHelper.html#Syncfusion_UI_Xaml_Grid_Helpers_SelectionHelper_GetParentDataGrid_Syncfusion_UI_Xaml_Grid_SfDataGrid_) helper method.

{% tabs %}
{% highlight c# %}
var parentDataGrid = this.dataGrid.SelectedDetailsViewGrid.GetParentDataGrid();
{% endhighlight %}
{% endtabs %}

### Getting the DetailsViewDataGrid 

You can get the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) based on row index through [GetDetailsViewGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Helpers.SelectionHelper.html#Syncfusion_UI_Xaml_Grid_Helpers_SelectionHelper_GetDetailsViewGrid_Syncfusion_UI_Xaml_Grid_SfDataGrid_System_Int32_) helper method.

{% tabs %}
{% highlight c# %}
var detailsViewDataGrid = this.dataGrid.GetDetailsViewGrid(2);
{% endhighlight %}
{% endtabs %}

You can also get the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) based on the record index and relational column name using [GetDetailsViewGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Helpers.GridHelper.html#Syncfusion_UI_Xaml_Grid_Helpers_GridHelper_GetDetailsViewGrid_Syncfusion_UI_Xaml_Grid_SfDataGrid_System_Int32_System_String_) method.

{% tabs %}
{% highlight c# %}
var detailsViewDataGrid = this.dataGrid.GetDetailsViewGrid(0, "ProductDetails");
{% endhighlight %}
{% endtabs %}

### Programmatic Selection in DetailsViewDataGrid

In [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html), you can add or remove the selection programmatically like parent DataGrid. You can get particular `DetailsViewDataGrid` by using [DetailsViewLoading](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event or [GetDetailsViewGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Helpers.SelectionHelper.html#Syncfusion_UI_Xaml_Grid_Helpers_SelectionHelper_GetDetailsViewGrid_Syncfusion_UI_Xaml_Grid_SfDataGrid_System_Int32_) method to process the selection operations.

#### Selecting records

You can select the particular record by using [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItem) property.

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewLoading += dataGrid_DetailsViewLoading;

void dataGrid_DetailsViewLoading (object sender, DetailsViewLoadingAndUnloadingEventArgs e)
{
    var record = e.DetailsViewDataGrid.GetRecordAtRowIndex(1);
    e.DetailsViewDataGrid.SelectedItem = record;
}
{% endhighlight %}
{% endtabs %}

Here, the record in first row is selected in `DetailsViewDataGrid`.

You can also select the particular record by using [SelectedIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedIndex) property.

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewLoading += dataGrid_DetailsViewLoading;

void dataGrid_DetailsViewLoading (object sender, DetailsViewLoadingAndUnloadingEventArgs e)
{
    e.DetailsViewDataGrid.SelectedIndex = 1;
}
{% endhighlight %}
{% endtabs %}

Here, the record in first position is selected in `DetailsViewDataGrid`.

You can select multiple records by using [SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems) property.

You can refer [here](#handling-events-for-detailsviewdatagrid) to know about handling events for `DetailsViewDataGrid`.

#### Row selection

You can select multiple rows by using [SelectRows](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridSelectionController.html#Syncfusion_UI_Xaml_Grid_GridSelectionController_SelectRows_System_Int32_System_Int32_) method.

{% tabs %}
{% highlight c# %}
var detailsViewDataGrid = this.dataGrid.GetDetailsViewGrid(2);
detailsViewDataGrid.SelectionController.SelectRows(1, 2);
{% endhighlight %}
{% endtabs %}

Here, first and second rows are selected in the `DetailsViewDataGrid` which is present in second row of the parent DataGrid.

#### Cell selection

You can select cells also by using [SelectCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCellSelectionController.html#Syncfusion_UI_Xaml_Grid_GridCellSelectionController_SelectCell_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Boolean_) and [SelectedCells](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCellSelectionController.html#Syncfusion_UI_Xaml_Grid_GridCellSelectionController_SelectCells_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Boolean_) method. You can refer the [Selection](http://help.syncfusion.com/wpf/sfdatagrid/selection) section.

### Programmatically expand and bring DetailsViewDataGrid into view

SfDataGrid allows you to bring the specified [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) in to view by using [DetailsViewManager.BringInToView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewManager.html#Syncfusion_UI_Xaml_Grid_DetailsViewManager_BringIntoView_System_Int32_) method.

Before bringing the `DetailsViewDataGrid` into view, you have to expand the corresponding parent record if it is not already expanded.

{% tabs %}
{% highlight c# %}
// parent DataGrid row index
int parentRowIndex = 25;
var record = this.dataGrid.View.Records[this.dataGrid.ResolveToRecordIndex(parentRowIndex)];          

//Get the DetailsViewManager using Reflection
var propertyInfo = dataGrid.GetType().GetField("DetailsViewManager", System.Reflection.BindingFlags.Instance | System.Reflection.BindingFlags.NonPublic);
            DetailsViewManager detailsViewManager = propertyInfo.GetValue(dataGrid) as DetailsViewManager;
// Expand DetailsView at specified record index

if (!record.IsExpanded)
this.dataGrid.ExpandDetailsViewAt(this.dataGrid.ResolveToRecordIndex(parentRowIndex));

{% endhighlight %}
{% endtabs %}

If the `DetailsViewDataGrid` is already expanded, you can use [ScrollInView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ScrollInView_Syncfusion_UI_Xaml_ScrollAxis_RowColumnIndex_) method to bring it into view. Else, you have to use `BringIntoView` method also.

{% tabs %}
{% highlight c# %}
//  find DetailsViewDataRow index based on relational column
int index = 0;

foreach (var def in this.dataGrid.DetailsViewDefinition)
{

    if (def.RelationalColumn == "ProductDetails")
    {
       index = this.dataGrid.DetailsViewDefinition.IndexOf(def);
       index = parentRowIndex + index + 1;
    }
}
var rowColumnIndex = new RowColumnIndex(index, 1);

// if the DetailsViewDataGrid is already expanded, bring that into view
dataGrid.ScrollInView(rowColumnIndex);

//Get the DetailsViewDataGrid by passing the corresponding row index and relation name
var detailsViewDataGrid = this.dataGrid.GetDetailsViewGrid(this.dataGrid.ResolveToRecordIndex(parentRowIndex), "ProductDetails");

//if the DetailsViewDataGrid is not already expanded, call BringIntoView method

if (detailsViewDataGrid == null)
{
   detailsViewManager.BringIntoView(index);      
}
{% endhighlight %}
{% endtabs %}

You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/MASTER~3548859394.ZIP).

### Customizing Selection for DetailsViewDataGrid

You can also customize the selection behavior of `DetailsViewDataGrid` like the parent DataGrid. For more information about customizing selection behavior, you can refer [here](http://help.syncfusion.com/wpf/sfdatagrid/selection).
Follow the steps mentioned in selection customization section to customize selection behavior of [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) and set the customized selection controller to [DetailsViewDataGrid.SelectionController](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectionController) in [DetailsViewLoading](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

{% tabs %}
{% highlight c# %}
public class CustomSelectionController:GridSelectionController
{

    public CustomSelectionController(SfDataGrid dataGrid)
        :base(dataGrid)
    {
    }
}
this.dataGrid.DetailsViewLoading += dataGrid_DetailsViewLoading;

void dataGrid_DetailsViewLoading(object sender, DetailsViewLoadingAndUnloadingEventArgs e)
{

     if (!(e.DetailsViewDataGrid.SelectionController is CustomSelectionController))
        e.DetailsViewDataGrid.SelectionController = new CustomSelectionController(e.DetailsViewDataGrid);
}

{% endhighlight %}
{% endtabs %}

N> For customizing selection in second level nested grid, you can refer [here](#defining-properties-for-detailsviewdatagrid).

## Appearance customization

The visual appearance of [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) can be customized like parent DataGrid through [Styling and Templates support](http://help.syncfusion.com/wpf/sfdatagrid/styles-and-templates) in SfDataGrid. 

### Changing Header appearance of DetailsViewDataGrid

You can customize the header appearance of [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) , through [HeaderStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_HeaderStyle) property of `DetailsViewDataGrid`.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <Style x:Key="headerStyle" TargetType="syncfusion:GridHeaderCellControl">
        <Setter Property="Background" Value="Red" />
    </Style>
</Window.Resources>
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="False"
                        ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid  x:Name="FirstLevelNestedGrid"
                                        AutoGenerateColumns="False"
                                        HeaderStyle="{StaticResource headerStyle}">
                    <syncfusion:SfDataGrid.Columns>
                        <syncfusion:GridTextColumn MappingName="OrderID" />
                        <syncfusion:GridTextColumn MappingName="ProductName" />
                    </syncfusion:SfDataGrid.Columns>
                </syncfusion:SfDataGrid>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

When the relation is auto-generated, you can assign the customized header style to [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) in [AutoGeneratingRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingRelations += dataGrid_AutoGeneratingRelations;

void dataGrid_AutoGeneratingRelations(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingRelationsArgs e)
{
    e.GridViewDefinition.DataGrid.HeaderStyle = this.FindResource("headerStyle") as Style;
}
{% endhighlight %}
{% endtabs %}

![Changing Header Appearance of WPF Master Details View DataGrid](Master-Details-View_images/wpf-datagrid-header-customization.png)

### Hiding header row of Master-Details View

You can hide the header row of [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) by setting [HeaderRowHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_HeaderRowHeight) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="False"
                        ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid  x:Name="FirstLevelNestedGrid"
                                        AutoGenerateColumns="True"
                                        HeaderRowHeight="0" />
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
FirstLevelNestedGrid.HeaderRowHeight = 0;
{% endhighlight %}
{% endtabs %}

![WPF Nested DataGrid without Header](Master-Details-View_images/wpf-nested-datagrid-without-header.png)

### Customizing padding of the DetailsViewDataGrid

The padding of [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) can be customized through the [DetailsViewPadding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_DetailsViewPadding) property and it will be set to its corresponding parent DataGrid.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="False"
                        DetailsViewPadding="15"
                        ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid  x:Name="FirstLevelNestedGrid" 
                                        AutoGenerateColumns="True" />
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.DetailsViewPadding = new Thickness(15);
{% endhighlight %}
{% endtabs %}

![Customized Padding of WPF Nested DataGrid](Master-Details-View_images/wpf-datagrid-padding-customization.png)

N> For customizing appearance for second level nested grid, you can refer [here](#defining-properties-for-detailsviewdatagrid).

### Customize ExpanderColumn width 

You can customize the width of ExpanderColumn in SfDataGrid by using [ExpanderColumnWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ExpanderColumnWidth) property as like below.

{% tabs %}
{% highlight xaml %}
<Syncfusion:SfDataGrid x:Name="dataGrid"                               
                       ExpanderColumnWidth="50"
                       AutoGenerateRelations="True"
                       ItemsSource="{Binding OrderInfoCollection }">
{% endhighlight %}
{% highlight c# %}
this.dataGrid.ExpanderColumnWidth = 50;
{% endhighlight %}
{% endtabs %}

## Expanding and collapsing the DetailsViewDataGrid programmatically

SfDataGrid allows you to expand or collapse the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) programmatically in different ways. 

### Expand or collapse all the DetailsViewDataGrid
 
You can expand or collapse all the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) programmatically by using [ExpandAllDetailsView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ExpandAllDetailsView) and [CollapseAllDetailsView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CollapseAllDetailsView) methods.

{% tabs %}
{% highlight c# %}
this.dataGrid.ExpandAllDetailsView();
this.dataGrid.CollapseAllDetailsView();
{% endhighlight %}
{% endtabs %}

### Expand DetailsViewDataGrid based on level

You can expand all the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) programmatically based on level using [ExpandAllDetailsView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ExpandAllDetailsView_System_Int32_) method.

{% tabs %}
{% highlight c# %}
this.dataGrid.ExpandAllDetailsView(2);
{% endhighlight %}
{% endtabs %}

Here, all the DetailsViewDataGrids up to second level will be expanded.

### Expand or collapse Details View based on record index	

You can expand or collapse [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) based on the record index by using [ExpandDetailsViewAt](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ExpandDetailsViewAt_System_Int32_) and [CollapseDetailsViewAt](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CollapseDetailsViewAt_System_Int32_) methods.

{% tabs %}
{% highlight c# %}
this.dataGrid.ExpandDetailsViewAt(0);
this.dataGrid.CollapseDetailsViewAt(0);
{% endhighlight %}
{% endtabs %}

## Hiding expander when parent record’s relation property has an empty collection or null

By default, the expander will be visible for all the data rows in parent DataGrid even if its [RelationalColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ViewDefinition.html#Syncfusion_UI_Xaml_Grid_ViewDefinition_RelationalColumn) property has an empty collection or null. 

You can hide the expander from the view when corresponding `RelationalColumn` property has an empty collection or null, by setting [HideEmptyGridViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_HideEmptyGridViewDefinition) property as `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="True"
                        HideEmptyGridViewDefinition="True"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% endtabs %}

![WPF Master Details View DataGrid displays Expander View](Master-Details-View_images/wpf-datagrid-expander-view.png)

## Hiding GridDetailsViewIndentCell in SfDataGrid

[GridDetailsViewIndentCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridDetailsViewIndentCell.html) is used to indicate the space between the expander and first column of the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html). You can hide the [GridDetailsViewIndentCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridDetailsViewIndentCell.html) by setting [SfDataGrid.ShowDetailsViewIndentCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ShowDetailsViewIndentCell) property to `False` for the respective parent grid.

![WPF DataGrid displays Master Details View with Indent Cells](Master-Details-View_images/wpf-datagrid-indent-cell.png)

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        AutoGenerateRelations="True"
                        ShowDetailsViewIndentCell="False"
                        ItemsSource="{Binding Orders}" >
	<syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="OrderDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"
									   AutoGenerateColumns="True"/>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
dataGrid.ShowDetailsViewIndentCell= False;
{% endhighlight %}
{% endtabs %}

![WPF DataGrid displays Master Details View without Indentation](Master-Details-View_images/wpf-datgrid-without-indent-cell.png)

## Hiding the details view expander icon based on child items count

By default, the state of expander icon is visible for all the data rows in parent DataGrid even if its `RelationalColumn` property has an empty collection or null.

You can customize hiding the details view expander icon by handling the `SfDataGrid.QueryDetailsViewExpanderState` event. This event occurs when expander icon is changed on expanding or collapsing the details view. You can hide the expander icon by setting the `ExpanderVisibility` property to `false` in the `SfDataGrid.QueryDetailsViewExpanderState` event based on condition.

{% tabs %}
{% highlight c# %}
this.dataGrid.QueryDetailsViewExpanderState += DataGrid_QueryDetailsViewExpanderState;

private void DataGrid_QueryDetailsViewExpanderState(object sender, Syncfusion.UI.Xaml.Grid.QueryDetailsViewExpanderStateEventArgs e)
        {
            var orderInfo = e.Record as OrderInfo;
            if (orderInfo != null)
            {
                if (orderInfo.OrderDetails.Count == 0)
                {
                    e.ExpanderVisibility = false;
                }
            }
        }
{% endhighlight %}
{% endtabs %} 

The following screenshot illustrates how to hide the state of expander icon based on child items count.
![Hidw Expander Icon in WPF Master Details View DataGird](Master-Details-View_images/wpf-datagrid-hide-expander-icon.png)
You can download the sample from the following link: [Sample](https://github.com/SyncfusionExamples/how-to-hide-the-detailsview-expander-icon-based-on-child-records-count-wpf-datagrid).

## Change DetailsViewDataGrid ItemsSource at runtime using LiveDataUpdateMode property

`ItemsSource` for DetailsViewDataGrid is populated from the `DataContext` of parent row based on [ViewDefinition.RelationalColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ViewDefinition.html#Syncfusion_UI_Xaml_Grid_ViewDefinition_RelationalColumn). DetailsViewDataGrid doesn’t update its `ItemsSource` at runtime based on the property change, which is mapped the DetailsViewDataGrid `ItemsSource`. You can update the `ItemsSource` on the property change by setting [SfDataGrid.LiveDataUpdateMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_LiveDataUpdateMode) as `AllowChildViewUpdate`. 

{% tabs %}
{% highlight xaml %}
<Syncfusion:SfDataGrid Name="dataGrid"  
                       AutoGenerateColumns="True"
                       AutoGenerateRelations="True"
                       ItemsSource="{Binding Source}"                              
                       LiveDataUpdateMode="AllowChildViewUpdate,AllowDataShaping">
{% endhighlight %}
{% highlight c# %}
this.dataGrid.LiveDataUpdateMode = LiveDataUpdateMode.AllowChildViewUpdate | LiveDataUpdateMode.AllowDataShaping;
{% endhighlight %}
{% endtabs %}

You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/WPF_-_Sample1341078924).

## Refreshing UI while adding records to relation property at run time

By default, the expander is hidden in row, when the [HideEmptyGridViewDefinition](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_HideEmptyGridViewDefinition) is set to `true` and [RelationalColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ViewDefinition.html#Syncfusion_UI_Xaml_Grid_ViewDefinition_RelationalColumn) property has an empty collection or null. You can refresh row to display expender when records are added to `RelationalColumn` property by calling `UpdateDataRow` method. 

For example, if you try to add the new record in `ProductDetails` collection in the parent record having `OrderID` as 1009 and 1010 at run time, the new record is added but the expander is not shown.  But it needs to be shown in UI since `RelationalColumn` property has record now. In this case, you need to refresh the particular data row to display expander by using [UpdateDataRow](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Helpers.GridHelper.html#Syncfusion_UI_Xaml_Grid_Helpers_GridHelper_UpdateDataRow_Syncfusion_UI_Xaml_Grid_SfDataGrid_System_Int32_) helper method. 

{% tabs %}
{% highlight c# %}
var dataContext = DataContext as OrderInfoRepository;
var data = dataContext.Orders.Where(item => item.OrderID == 1009).FirstOrDefault();
var newItem = new List<ProductInfo>();
newItem.Add(new ProductInfo() { OrderID = 1009, ProductName = "Bike" });
data.ProductDetails = newItem;

this.dataGrid.UpdateDataRow(dataGrid.ResolveToRowIndex(data));
{% endhighlight %}
{% endtabs %}

## Handling Events

### DetailsViewLoading 

The [DetailsViewLoading](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event is raised, when the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) is being loaded in to the view (such as scrolling, window size changed and expanding the record using an expander or programmatically).

This event receives two arguments where sender as SfDataGrid and [DetailsViewLoadingAndUnloadingEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewLoadingAndUnloadingEventArgs.html) which contains the following member.
* [DetailsViewDataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewLoadingAndUnloadingEventArgs.html#Syncfusion_UI_Xaml_Grid_DetailsViewLoadingAndUnloadingEventArgs__ctor_System_Object_Syncfusion_UI_Xaml_Grid_DetailsViewDataGrid_) **-** Gets the `DetailsViewDataGrid` which is loaded into view. You can set the customized `Renderers`, `SelectionController`, `ResizingController`, `GridColumnDragDropController`, and `GridColumnSizer` to this. But it is not preferable to change the value of the public properties like `AllowFiltering`, `AllowSorting`, `SelectionUnit`, `AllowDeleting`, etc., here.

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewLoading += dataGrid_DetailsViewLoading;

void dataGrid_DetailsViewLoading(object sender, DetailsViewLoadingAndUnloadingEventArgs e)
{

     if (!(e.DetailsViewDataGrid.SelectionController is CustomSelectionController))
                e.DetailsViewDataGrid.SelectionController = new CustomSelectionController(e.DetailsViewDataGrid);
}
{% endhighlight %}
{% endtabs %}

### DetailsViewUnLoading

The [DetailsViewUnLoading](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event is raised when the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) is being unloaded from the view. 

This event receives two arguments where sender as SfDataGrid and [DetailsViewLoadingAndUnloadingEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewLoadingAndUnloadingEventArgs.html) which contains the following member.
* [DetailsViewDataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewLoadingAndUnloadingEventArgs.html#Syncfusion_UI_Xaml_Grid_DetailsViewLoadingAndUnloadingEventArgs__ctor_System_Object_Syncfusion_UI_Xaml_Grid_DetailsViewDataGrid_) - Gets the `DetailsViewDataGrid` which was unloaded from the view (such as scrolling, window size changed, Sorting, Grouping, Filtering and collapsing the DetailsViewDataGrid using expander or programmatically).

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewUnloading += dataGrid_DetailsViewUnloading;

void dataGrid_DetailsViewUnloading(object sender, DetailsViewLoadingAndUnloadingEventArgs e)
{
         
}
{% endhighlight %}
{% endtabs %}

### DetailsViewExpanding

The [DetailsViewExpanding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event is raised when the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) is being expanded by using an expander.

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewExpanding += dataGrid_DetailsViewExpanding;

void dataGrid_DetailsViewExpanding(object sender, Syncfusion.UI.Xaml.Grid.GridDetailsViewExpandingEventArgs e)
{
}
{% endhighlight %}
{% endtabs %}

### DetailsViewExpanded

The [DetailsViewExpanded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event is raised after the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) is expanded by using an expander.

{% tabs %}
{% highlight c# %}

this.dataGrid.DetailsViewExpanded += dataGrid_DetailsViewExpanded;

void dataGrid_DetailsViewExpanded(object sender, GridDetailsViewExpandedEventArgs e)
{
}
{% endhighlight %}
{% endtabs %}

### DetailsViewCollapsing

The [DetailsViewCollapsing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event is raised when the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) is being collapsed from the view by using an expander.

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewCollapsing += dataGrid_DetailsViewCollapsing;

void dataGrid_DetailsViewCollapsing(object sender, Syncfusion.UI.Xaml.Grid.GridDetailsViewCollapsingEventArgs e)
{
}
{% endhighlight %}
{% endtabs %}

### DetailsViewCollapsed

The [DetailsViewCollapsed](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event is raised after the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) is collapsed by using an expander.

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewCollapsed += dataGrid_DetailsViewCollapsed;

void dataGrid_DetailsViewCollapsed(object sender, GridDetailsViewCollapsedEventArgs e)
{
}
{% endhighlight %}
{% endtabs %}

### Cancel expanding or collapsing operations through events

You can cancel expanding operation while expanding the [DetailsViewDataGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.DetailsViewDataGrid.html) by using [GridDetailsViewExpandingEventArgs.Cancel](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.canceleventargs.cancel) property in the [DetailsViewExpanding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler.

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewExpanding += dataGrid_DetailsViewExpanding;

void dataGrid_DetailsViewExpanding(object sender, Syncfusion.UI.Xaml.Grid.GridDetailsViewExpandingEventArgs e)
{
 
    if ((e.Record as OrderInfo).OrderID == 1002)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

Similarly, the collapsing operation can be canceled through the [GridDetailsViewCollapsingEventArgs.Cancel](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.canceleventargs.cancel) property in the [DetailsViewCollapsing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler.

{% tabs %}
{% highlight c# %}
this.dataGrid.DetailsViewCollapsing += dataGrid_DetailsViewCollapsing;

void dataGrid_DetailsViewCollapsing(object sender, Syncfusion.UI.Xaml.Grid.GridDetailsViewCollapsingEventArgs e)
{
 
    if ((e.Record as OrderInfo).OrderID == 1002)
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

N>  To cancel expanding or collapsing operation in second level nested grid, you can refer [here](#handling-events-for-detailsviewdatagrid).

## Master-Details View limitations 

Following are the limitations of Master-Details View in SfDataGrid.

1. `DetailsViewDataGrid` does not have `GroupDropArea`.
2. `DetailsViewDataGrid` does not support `AutoGenerateColumnsMode.ResetAll`. Instead it works based on `Reset`.
3. Master-Details View doesn’t support Data Virtualization.
4. Master-Details View doesn’t support [AllowFrozenGroupHeader](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AllowFrozenGroupHeaders).
5. Master-Details View doesn’t support Freeze Pane.
6. Master-Details View doesn’t support `AutoRowHeight`.
7. For `DetailsViewDataGrid`, `SelectionMode`, `SelectionUnit`, `NavigationMode`, `DetailsViewPadding` properties are assigned from its parent grid only. So both parent DataGrid and `DetailsViewDataGrid` cannot have different values for these properties.

## See Also

[How to maintain the DetailsView expanded state when Sorting and Grouping the DataGrid (SfDataGrid)?](https://www.syncfusion.com/kb/11032)

[How to set the background for selected DetailsViewGrid?](https://www.syncfusion.com/kb/9329/)

[How to load the button command inside the Detailsview datagrid column and setting AncestorLevel?](https://www.syncfusion.com/kb/7205)

[How to export the DetailsView records in expanded state to Excel?](https://www.syncfusion.com/kb/7199)

[How to print the SfDataGrid with DetailsView?](https://www.syncfusion.com/kb/6937)

[How to get the SelectedItem of the DetailsView?](https://www.syncfusion.com/kb/6922)

[How to bind SelectedItem and CurrentItem in DetailsViewDataGrid](https://www.syncfusion.com/kb/6704)

[How to get the CurrentCell for DetailsViewDatagrid at runtime?](https://www.syncfusion.com/kb/6308)

[How to add a new record in specific DetailsViewDataGrid ?](https://www.syncfusion.com/kb/6287)

[How to hide the key mapping column in DetailsViewDataGrid?](https://www.syncfusion.com/kb/6204)

[How to resize the parent grid and DetailsViewDataGrid simultaneously?](https://www.syncfusion.com/kb/5279)

[How to create Custom Column in the DetailsViewDataGrid?](https://www.syncfusion.com/kb/4237)

[How to change the background color of the Header alone in DetailsView or Nested Grid?](https://www.syncfusion.com/kb/3209)

[How to prevent resizing the last column, when parent Grid width is less than the child Grid width?](https://www.syncfusion.com/kb/3109)

[How to change the ColumnSizer for the Nested grid?](https://www.syncfusion.com/kb/2478)

[How to get the parent grid while editing the child grid?](https://www.syncfusion.com/kb/2472)

[How to enable NestedGrid when I don't have relations in my datasource](https://www.syncfusion.com/kb/2458)

[How to hide the HeaderRow in Nested Grid?](https://www.syncfusion.com/kb/2443)
