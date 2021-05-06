---
layout: post
title: Data Binding in WPF Pivot Grid control | Syncfusion
description: Learn about Data Binding support in Syncfusion WPF Pivot Grid control and more.
platform: wpf
control: Pivot grid
documentation: ug
---

# Data Binding in WPF Pivot Grid

## Binding pivot grid to list

The pivot grid allows binding a list based collection as its item source. Refer to this topic [Binding a data source to pivot grid control](https://help.syncfusion.com/wpf/pivotgrid/pivotgrid-getting-started#binding-a-datasource-to-pivotgridcontrol) to learn more.

## Binding pivot grid to data table

The pivot grid allows binding a DataSet from the data table as its item source.

To do so, initially you should create a connection to the database. Then, retrieve and store the required data to a DataSet through SQL queries. Refer to the following code sample.

{% highlight C# %}

public static DataView GetOrderDetails() {
    try {
        DataSet ds = new DataSet();
        using(SqlCeConnection con = new SqlCeConnection(@ "DataSource=Data\Northwind.sdf")) {
            con.Open();
            SqlCeCommand cmd = new SqlCeCommand(@ "SELECT Top(100) [Order ID], [Product ID], [Unit Price], Quantity FROM [Order Details] ", con);
            SqlCeDataAdapter da = new SqlCeDataAdapter(cmd);
            da.Fill(ds);
            //Creation of DataView
            DataView dataView = new DataView(ds.Tables[0], "[Unit Price] >= 20", "[Order ID]", DataViewRowState.CurrentRows);
            return dataView;
        }
    }
}

{% endhighlight %}

Then, bind the DataSet as ItemSource to the pivot grid by invoking the appropriate method. It can be done through XAML or code-behind.

For XAML, refer to the following code sample.

{% highlight xaml %}

    <Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="WpfApplication1.MainWindow" Title="MainWindow" Height="350" Width="525" xmlns:local="clr-namespace:WpfApplication1">
        <Window.Resources>
            <ResourceDictionary>
                <ObjectDataProvider x:Key="data" ObjectType="{x:Type local:OrderDetails}" MethodName="GetOrderDetails" />
            </ResourceDictionary>
        </Window.Resources>
        <Grid>
            <syncfusion:PivotGridControl Margin="5" Grid.Row="2" x:Name="pivotGrid1" ItemSource="{Binding Source={StaticResource data}}">
                <syncfusion:PivotGridControl.PivotRows>
                    <syncfusion:PivotItem FieldHeader="OID" FieldMappingName="Order ID" TotalHeader="Total" />
                </syncfusion:PivotGridControl.PivotRows>
                <syncfusion:PivotGridControl.PivotColumns>
                    <syncfusion:PivotItem FieldHeader="PID" FieldMappingName="Product ID" TotalHeader="Total" />
                </syncfusion:PivotGridControl.PivotColumns>
                <syncfusion:PivotGridControl.PivotCalculations>
                    <syncfusion:PivotComputationInfo FieldName="Unit Price" CalculationName="UnitTotal" SummaryType="DoubleTotalSum" Format="#.00" />
                    <syncfusion:PivotComputationInfo FieldName="Quantity" CalculationName="QuantityCalc" SummaryType="Count" Format="C" />
                </syncfusion:PivotGridControl.PivotCalculations>
            </syncfusion:PivotGridControl>
        </Grid>
    </Window>

{% endhighlight %}

For code-behind, refer to the following code sample.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        //Binding DataView to the ItemSource
        this.pivotGrid1.ItemSource = OrderDetails.GetOrderDetails();
        this.pivotGrid1.PivotColumns.Add(new PivotItem {
            FieldHeader = "OrderID", FieldMappingName = "Order ID", TotalHeader = "Total"
        });
        this.pivotGrid1.PivotRows.Add(new PivotItem {
            FieldHeader = "ProductID", FieldMappingName = "Product ID", TotalHeader = "Total"
        });
        this.pivotGrid1.PivotCalculations.Add(new PivotComputationInfo {
            CalculationName = "UnitPrice", FieldName = "Unit Price", Format = "C", SummaryType = SummaryType.DecimalTotalSum
        });
        this.pivotGrid1.PivotCalculations.Add(new PivotComputationInfo {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.Count
        });
    }
}

{% endhighlight %}
