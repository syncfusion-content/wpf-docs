---
layout: post
title: Getting Started | SfDataPagerControl | wpf | Syncfusion
description: This section explain about how to integrate WPF DataPager (SfDataPager) into an applicationl and enable its basic features with example.. 
platform: wpf
control: SfDataPager Control
documentation: ug
---

# Getting Started with WPF DataPager (SfDataPager)

This section describes about the assembly that is required for SfDataPagerControl in your WPF application.The following assemblies are required in your application.



<table>
<tr>
<th>
Demanded Assemblies</th><th>
Description</th></tr>
<tr>
<td>
Syncfusion.SfGrid.WPF</td><td>
Covers the SfDataPager and other elements.</td></tr>
</table>


When you use SfDataPager in the SfDataGrid, You need to add the following assembles with the default assembles.

<table>
<tr>
<th>
Demanded Assemblies</th><th>
Description</th></tr>
<tr>
<td>
Syncfusion.Data.WPF</td><td>
Covers basic processing on data like sorting, grouping, and filtering.</td></tr>
<tr>
<td>
Syncfusion.Shared.WPF</td><td>
Covers an editors like CurrencyTextBox, PercentEdit, DateTimeEdit.</td></tr>
</table>


## Control Structure

The following screenshot describes the elements of the DataPager control.

![Displaying DataPager control](Getting-Started_images/Getting-Started_img1.png)



* FirstPageButton: Moves the current page index to the first page and displays the first page data.
* PreviousPageButton: Moves the current page index to the previous page and displays the previous page data.
* LastPageButton: Moves the current page index to the last page and displays the last page data.
* NextPageButton: Moves the current page index to the next page and displays the next page data.
* NumericButtons: Denotes the available pages. You can directly navigate to the page by clicking the corresponding button.
* EllipsisButton: Displayed when AutoEllipsis mode is set. This button displays the next set of numeric page buttons are displayed.



## Create Simple Application with SfDataPager

The following steps help you to use the SfDataPager in an application:

1. Create a new WPF application
2. Open a VisualStudio toolbox. Navigate to SyncfusionControls and drag the SfDataPager to the design window.



   ![Displaying the WPF SfDataPager control in designer](Getting-Started_images/Getting-Started_img2.png)



3. When you drag the SfDataPager to the window, it automatically adds the required references to the current application.To add the SfDataPager using code, you can add the following assemblies to the project.
   
   I. Syncfusion.Data.WPF
   
   II. Syncfusion.SfGrid.WPF

4.You can either drag the control from Visual Studio or Expression Blend, or add the control to your project manually. You need to add the namespace to make use of SfDataPager in your application.

{% tabs %}
{% highlight xaml %}
<Window x:Class="SfDataPagerDemo.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:SfDataPagerDemo"        
        xmlns:datapager="clr-namespace:Syncfusion.UI.Xaml.Controls.DataPager;assembly=Syncfusion.SfGrid.WPF"
        mc:Ignorable="d"
        Title="MainWindow" Height="350" Width="525">
    <Grid>
        <datapager:SfDataPager x:Name="sfDataPager"/>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %}

5.Create Business object class named as OrderInfo

{% tabs %}
{% highlight c# %}
public class OrderInfo
{
    int orderID;
    string customerId;
    string country;
    string customerName;
    string shippingCity;

    public int OrderID
    {
        get { return orderID; }
        set { orderID = value; }
    }

    public string CustomerID
    {
        get { return customerId; }
        set { customerId = value; }
    }

    public string CustomerName
    {
        get { return customerName; }
        set { customerName = value; }
    }

    public string Country
    {
        get { return country; }
        set { country = value; }
    }

    public string ShipCity
    {
        get { return shippingCity; }
        set { shippingCity = value; }
    }

    public OrderInfo(int orderId, string customerName, string country, string customerId, string shipCity)
    {
        this.OrderID = orderId;
        this.CustomerName = customerName;
        this.Country = country;
        this.CustomerID = customerId;
        this.ShipCity = shipCity;
    }
}
{% endhighlight %}
{% endtabs %}

6.Add the following code in ViewModel class

{% tabs %}
{% highlight c# %}
public class ViewModel
{
    ObservableCollection<OrderInfo> orderCollection;

    public ObservableCollection<OrderInfo> OrderInfoCollection
    {
        get { return orderCollection; }
        set { orderCollection = value; }
    }

    public ViewModel()
    {
        orderCollection = new ObservableCollection<OrderInfo>();
        this.GenerateOrders();
    }

    private void GenerateOrders()
    {
        orderCollection.Add(new OrderInfo(1001, "Maria Anders", "Germany", "ALFKI", "Berlin"));
        orderCollection.Add(new OrderInfo(1002, "Ana Trujilo", "Mexico", "ANATR", "Mexico D.F."));
        orderCollection.Add(new OrderInfo(1003, "Antonio Moreno", "Mexico", "ANTON", "Mexico D.F."));
        orderCollection.Add(new OrderInfo(1004, "Thomas Hardy", "UK", "AROUT", "London"));
        orderCollection.Add(new OrderInfo(1005, "Christina Berglund", "Sweden", "BERGS", "Lula"));
        orderCollection.Add(new OrderInfo(1006, "Hanna Moos", "Germany", "BLAUS", "Mannheim"));
        orderCollection.Add(new OrderInfo(1007, "Frederique Citeaux", "France", "BLONP", "Strasbourg"));
        orderCollection.Add(new OrderInfo(1008, "Martin Sommer", "Spain", "BOLID", "Madrid"));
        orderCollection.Add(new OrderInfo(1009, "Laurence Lebihan", "France", "BONAP", "Marseille"));
        orderCollection.Add(new OrderInfo(1010, "Elizabeth Lincoln", "Canada", "BOTTM", "Tsawassen"));
    }
}
{% endhighlight %}
{% endtabs %}

7.Set the ViewModel instance as DataContext to window. Now, you can bind the data collection to the SfDataPagerSource property.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>
<Grid>
    <datapager:SfDataPager x:Name="sfDataPager" 
						   Grid.Row="1"
						   AccentBackground="DodgerBlue"
						   NumericButtonCount="5"
						   PageSize="5" 
						   Source="{Binding OrderInfoCollection}" />
</Grid>
{% endhighlight %}
{% endtabs %}

8.Then bind the PagedSource property of the SfDataPager control into the SfDataGridItemsSource property.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
    <local:Viewmodel/>
</Window.DataContext>
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="*" />
        <RowDefinition Height="Auto" />
    </Grid.RowDefinitions>
    <sfGrid:SfDataGrid AutoGenerateColumns="True" 
					   ItemsSource="{Binding ElementName=sfDataPager,Path=PagedSource}"/>
    <datapager:SfDataPager x:Name="sfDataPager" 
						   Grid.Row="1"
						   NumericButtonCount="10"
						   PageSize="10" 
						   Source="{Binding OrdersDetails}" />
</Grid>
{% endhighlight %}
{% endtabs %}

The following screenshot displays the output for Implementation of the SfDataPager in the SfDataGrid Control.


![Displaying the SfDataPager in the SfDataGrid Control ](Getting-Started_images/Getting-Started_img3.png)

## Theme

SfDataPager supports various built-in themes. Refer to the below links to apply themes for the SfDataPager,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme in the SfDataGrid Control ](Getting-Started_images/Theme.png)


