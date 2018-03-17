---
layout: post
title: PivotGrid-Getting-Started
description: pivotgrid getting started
platform: wpf
control: PivotGridControl
documentation: ug
---

# Creating a simple application with PivotGrid

## Adding PivotGrid through Designer

Open Visual Studio IDE and navigating to File > New > Project > WPF Application (inside Visual C# Templates) to create a new WPF application.

Once the WPF application is created, goto View menu and select Toolbox option. Now the Toolbox will appear inside Visual Studio IDE. Drag and drop the PivotGrid control from **Syncfusion BI WPF** category in the Toolbox to the designer page. The PivotGrid control will be added along with the dependency assemblies automatically into the application.

![](PivotGrid-Getting-Started-images/Adding PivotGrid through designer.png)

## Adding PivotGrid through XAML

Open Visual Studio IDE and navigating to File > New > Project > WPF Application (inside Visual C# Templates) to create a new WPF application.

Next you need to add the following dependency assemblies into your WPF Application. To add them to your WPF Application, right-click on **References** in Solution Explorer and select **Add Reference**. Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the below mentioned Syncfusion assemblies are found.

* Syncfusion.Grid.Wpf
* Syncfusion.GridCommon.Wpf
* Syncfusion.Linq.Base
* Syncfusion.PivotAnalysis.Base
* Syncfusion.PivotAnalysis.Wpf
* Syncfusion.Shared.Wpf

N> You can also get the assemblies by browsing to the Default Assembly Location.
{System Drive}:\Program Files (x86)\Syncfusion\Essential Studio\\{version number}\precompiledassemblies\\{version number}

Then define the PivotGrid control in MainWindow.xaml as shown in the below code sample.

{% highlight XAML %}

    <Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="WpfApplication1.MainWindow"
        Title="MainWindow" Height="350" Width="525">
        <Grid>
            <syncfusion:PivotGridControl Name="pivotGrid" HorizontalAlignment="Left" Margin="5,0,0,0" VerticalAlignment="Top" Height="50" Width="100"/>
        </Grid>
    </Window>

{% endhighlight %}

## Adding PivotGrid through Code-Behind

Open Visual Studio IDE and navigating to File > New > Project > WPF Application (inside Visual C# Templates) to create a new WPF application.

Next you need to add the following dependency assemblies into your WPF Application. To add them to your WPF Application, right-click on **References** in Solution Explorer and select **Add Reference**. Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the below mentioned Syncfusion assemblies are found.

* Syncfusion.Grid.Wpf
* Syncfusion.GridCommon.Wpf
* Syncfusion.Linq.Base
* Syncfusion.PivotAnalysis.Base
* Syncfusion.PivotAnalysis.Wpf
* Syncfusion.Shared.Wpf

N> You can also get the assemblies by browsing to the Default Assembly Location
{System Drive}:\Program Files (x86)\Syncfusion\Essential Studio\\{version number}\precompiledassemblies\\{version number}

Then, add a Grid container in MainWindow.xaml which will hold the PivotGrid control created and added from code-behind lately.

{% highlight XAML %}

    <Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="WpfApplication1.MainWindow"
        Title="MainWindow" Height="350" Width="525">
        <Grid Name="grid1">
        </Grid>
    </Window>

{% endhighlight %}

Include the *Syncfusion.Windows.Controls.PivotGrid* namespace in MainWindow.xaml.cs to create a PivotGrid control in code-behind.

{%highlight C# %}

    using System.Windows.Media.Imaging;
    using System.Windows.Navigation;
    using System.Windows.Shapes;
    using Syncfusion.Windows.Controls.PivotGrid;

{% endhighlight %}

Raise the **Loaded** event of the MainWindow and within that event, create a new instance of the PivotGridControl class. This instance should then be added as a child of the Grid present inside MainWindow.

{% highlight C# %}

public MainWindow() {
    InitializeComponent();
    this.Loaded += MainWindow_Loaded;
}
void MainWindow_Loaded(object sender, RoutedEventArgs e) {
    PivotGridControl pivotGrid = new PivotGridControl();
    this.grid1.Children.Add(pivotGrid);
}

{% endhighlight %}

## Adding PivotGrid through Expression Blend

Open Blend for Visual Studio and navigating to File > New Project > WPF > WPF Application to create a new WPF application.

Select the **Projects** tab available in the top-left corner of the Blend IDE, right-click on the **References** and select **Add Reference**. Now browse and add the following assemblies to the project.

* Syncfusion.Grid.Wpf
* Syncfusion.GridCommon.Wpf
* Syncfusion.Linq.Base
* Syncfusion.PivotAnalysis.Base
* Syncfusion.PivotAnalysis.Wpf
* Syncfusion.Shared.Wpf

N> You can also get the assemblies by browsing to the Default Assembly Location
{System Drive}:\Program Files (x86)\Syncfusion\Essential Studio\\{version number}\precompiledassemblies\\{version number}

Only after adding the above assemblies, PivotGrid control will be automatically added under **Assets** tab. Now choose the **Assets** tab, drag and drop the PivotGridControl from Toolbox to designer section.

![](PivotGrid-Getting-Started-images/Adding PivotGridControl through expression blend.png)

## Binding a datasource to PivotGridControl

Right-click on the project in the solution explorer and select **Add ->New item**.In the **Add New Item** window, choose option **Class** and provide the name of the class as *ProductSales.cs* and click **OK**.

The ItemSource for the PivotGrid control will be initialized in this file. Please refer the below code snippet.

{% highlight C# %}

public class ProductSales {
    public string Product {
        get;
        set;
    }
    public string Date {
        get;
        set;
    }
    public string Country {
        get;
        set;
    }
    public string State {
        get;
        set;
    }
    public int Quantity {
        get;
        set;
    }
    public double Amount {
        get;
        set;
    }
    public static ProductSalesCollection GetSalesData() {
        /// Geography
        string[] countries = new string[] {
            "Canada"
        };
        string[] canadaStates = new string[] {
            "Alberta",
            "British Columbia",
            "Ontario"
        };
        /// Time
        string[] dates = new string[] {
            "FY 2005",
            "FY 2006",
            "FY 2007"
        };
        /// Products
        string[] products = new string[] {
            "Bike",
            "Car"
        };
        Random r = new Random(123345345);
        int numberOfRecords = 2000;
        ProductSalesCollection listOfProductSales = new ProductSalesCollection();
        for (int i = 0; i < numberOfRecords; i++) {
            ProductSales sales = new ProductSales();
            sales.Country = countries[r.Next(0, countries.GetLength(0))];
            sales.Quantity = r.Next(1, 12);
            /// 1 percent discount for 1 quantity
            double discount = (30000*sales.Quantity)*(double.Parse(sales.Quantity.ToString()) / 100);
            sales.Amount = (30000 * sales.Quantity) - discount;
            sales.Date = dates[r.Next(r.Next(dates.GetLength(0) + 1))];
            sales.Product = products[r.Next(r.Next(products.GetLength(0) + 1))];
            sales.State = canadaStates[r.Next(canadaStates.GetLength(0))];
            listOfProductSales.Add(sales);
        }
        return listOfProductSales;
    }
    public override string ToString() {
        return string.Format("{0}-{1}-{2}", this.Country, this.State, this.Product);
    }
    public class ProductSalesCollection: List < ProductSales > {

    }
}

{% endhighlight %}

Above mentioned GetSalesData method is used to get the collection that needs to be populated in the PivotGrid control.Now we need to bind the collection to the PivotGrid control as its ItemSource. It can be done through *XAML* or *Code-behind*.

If you need to initialize the ItemSource through **XAML**, ObjectDataProvider is used. Please refer the following code.

{% highlight XAML %}

    <Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="WpfApplication1.MainWindow" Title="MainWindow" Height="350" Width="525" xmlns:local="clr-namespace:WpfApplication1">
        <Window.Resources>
            <ResourceDictionary>
                <ObjectDataProvider x:Key="data" ObjectType="{x:Type local:ProductSales}" MethodName="GetSalesData" />
            </ResourceDictionary>
        </Window.Resources>
        <Grid>
            <syncfusion:PivotGridControl Name="pivotGrid" HorizontalAlignment="Left" VerticalAlignment="Top" ItemSource="{Binding Source={StaticResource data}}" VisualStyle="Metro">
            </syncfusion:PivotGridControl>
        </Grid>
    </Window>

{% endhighlight %}

 Else, if you need to initialize the Item source through **Code-Behind**, please refer the below code snippet.

{% highlight C# %}

public MainWindow() {
    InitializeComponent();
    this.Loaded += MainWindow_Loaded;
}
void MainWindow_Loaded(object sender, RoutedEventArgs e) {
    PivotGridControl pivotGrid = new PivotGridControl();
    this.grid1.Children.Add(pivotGrid);
    pivotGrid.ItemSource = ProductSales.GetSalesData();
}

{% endhighlight %}

### Defining the PivotItems and PivotComputations

 **PivotItem** is a container for items in PivotGrid control. An item can be either a **PivotRow** or **PivotColumn**. Please refer the topic *1.3.1 Pivot Item* for more details.**PivotComputationInfo** holds the value fields for the PivotGrid control. It does have different types of custom calculations and we could summarize the values depends on our requirement. Please refer the topic *1.3.2 PivotComputationInfo* for more details. PivotItems and PivotComputations can be defined through *XAML* and *Code-Behind*.

If you need to define the PivotItems and PivotComputations through **XAML**, refer the code snippet below.

{% highlight XAML %}

    <Grid>
        <syncfusion:PivotGridControl Name="pivotGrid" HorizontalAlignment="Left" VerticalAlignment="Top" ItemSource="{Binding Source={StaticResource data}}" VisualStyle="Metro">
            <syncfusion:PivotGridControl.PivotRows>
                <syncfusion:PivotItem FieldHeader="Product" FieldMappingName="Product" TotalHeader="Total" />
                <syncfusion:PivotItem FieldHeader="Date" FieldMappingName="Date" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotGridControl.PivotColumns>
                <syncfusion:PivotItem FieldHeader="Country" FieldMappingName="Country" TotalHeader="Total" />
                <syncfusion:PivotItem FieldHeader="State" FieldMappingName="State" TotalHeader="Total" />
            </syncfusion:PivotGridControl.PivotColumns>
            <syncfusion:PivotGridControl.PivotCalculations>
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Amount" Format="C" />
                <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Quantity" SummaryType="Count" />
            </syncfusion:PivotGridControl.PivotCalculations>
        </syncfusion:PivotGridControl>
    </Grid>

{% endhighlight %}

Else, if you need to define in **Code-Behind**, include the *Syncfusion.PivotAnalysis.Base*  namespace in MainWindow.xaml.cs. Please refer the below code snippet.

{% highlight C# %}

    using System.Windows.Media.Imaging;
    using System.Windows.Navigation;
    using System.Windows.Shapes;
    using Syncfusion.Windows.Controls.PivotGrid;
    using Syncfusion.PivotAnalysis.Base;

{% endhighlight %}

{% highlight C# %}

public MainWindow() {
    InitializeComponent();
    this.Loaded += MainWindow_Loaded;
}
void MainWindow_Loaded(object sender, RoutedEventArgs e) {
    PivotGridControl pivotGrid = new PivotGridControl();
    grid1.Children.Add(pivotGrid);
    PivotItem m_PivotItem = new PivotItem() {
        FieldHeader = "Product", FieldMappingName = "Product", TotalHeader = "Total"
    };
    PivotItem m_PivotItem1 = new PivotItem() {
        FieldHeader = "Date", FieldMappingName = "Date", TotalHeader = "Total"
    };
    PivotItem n_PivotItem = new PivotItem() {
        FieldHeader = "Country", FieldMappingName = "Country", TotalHeader = "Total"
    };
    PivotItem n_PivotItem1 = new PivotItem() {
        FieldHeader = "State", FieldMappingName = "State", TotalHeader = "Total"
    };
    // Adding PivotItem to PivotRows
    pivotGrid.PivotRows.Add(m_PivotItem);
    pivotGrid.PivotRows.Add(m_PivotItem1);
    // Adding PivotItem to PivotColumns
    pivotGrid.PivotColumns.Add(n_PivotItem);
    pivotGrid.PivotColumns.Add(n_PivotItem1);
    PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() {
        CalculationName = "Amount", FieldName = "Amount", SummaryType = SummaryType.Count
    };
    PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
        CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.Count
    };
    pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
    pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);
    pivotGrid.ItemSource = ProductSales.GetSalesData();
}

{% endhighlight %}

**Run** the application, the following output will be generated.

![](PivotGrid-Getting-Started-images/PivotGrid with Populated values.png)