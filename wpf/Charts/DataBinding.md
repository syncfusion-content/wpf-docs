---
layout: post
title: Data Binding in WPF Charts control | Syncfusion
description: Learn here all about Data Binding support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Data Binding in WPF Charts (SfChart)

SfChart offers ItemsSource property to bind various datasource ranges from simple collection property to complex properties.

### Binding a simple collection to the chart

{% tabs %}


{% highlight xaml %}

<syncfusion:SfChart >

<syncfusion:LineSeries

ItemsSource="{Binding Demands}"

XBindingPath="Demand"

YBindingPath="Year2010">

</syncfusion:LineSeries>


</syncfusion:SfChart>

{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

LineSeries lineSeries = new LineSeries()
{

      ItemsSource = new ViewModel().Demands,

      XBindingPath = "Demand",

      YBindingPath = "Year2010",

};

chart.Series.Add(lineSeries);

public class GoldDemand

{

      public string Demand { get; set; }



      public double Year2010 { get; set; }



      public double Year2011 { get; set; }

}

public sealed partial class MainPage : Page

{

public MainPage()

{

      this.InitializeComponent();

      this.Demands = new ObservableCollection<GoldDemand>

      {

      new GoldDemand() {Demand = "Jewelry", Year2010 = 1998.0, Year2011 = 2361.2},

      new GoldDemand() {Demand = "Electronics", Year2010 = 1284.0, Year2011 = 1328.0},

      new GoldDemand() {Demand = "Research", Year2010 = 1090.5, Year2011 = 1032.0},

      new GoldDemand() {Demand = "Investment", Year2010 = 1643.0, Year2011 = 1898.0},

      new GoldDemand() {Demand = "Bank Purchases", Year2010 = 987.0, Year2011 = 887.0},



      new GoldDemand() {Demand = "Others", Year2010 = 1090.5, Year2011 = 1032.0},

      new GoldDemand() {Demand = "Investment", Year2010 = 1643.0, Year2011 = 1898.0},

      new GoldDemand() {Demand = "Bank Purchases", Year2010 = 987.0, Year2011 = 887.0},



      new GoldDemand() {Demand = "Electronics", Year2010 = 1284.0, Year2011 = 1328.0},

      new GoldDemand() {Demand = "Research", Year2010 = 1090.5, Year2011 = 1032.0},

      new GoldDemand() {Demand = "Investment", Year2010 = 1643.0, Year2011 = 1898.0},

      new GoldDemand() {Demand = "Bank Purchases", Year2010 = 987.0, Year2011 = 887.0}

      };

      DataContext = this;

}

public ObservableCollection<GoldDemand> Demands { get; set; } 

}

{% endhighlight %}

{% endtabs %}


### Binding complex property to the chart

The complex property binding feature enables you to access nested object reference property values to render the chart segment. 

{% tabs %}

{% highlight xaml %}

<syncfusion:LineSeries ItemsSource="{Binding  DataWithMulData}" XBindingPath="StadiumObject.CupDetailsObj.CupName" YBindingPath="StadiumObject.NumSeats" /> 

{% endhighlight %}

{% highlight C# %}

StadiumDetails stadiumDetails = new StadiumDetails();

LineSeries series = new LineSeries()
{

      ItemsSource = new ViewModel().DataWithMulData,

      XBindingPath = "stadiumDetails.CupDetailsObj.CupName",

      YBindingPath = "stadiumDetails.NumSeats",

      Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))

};

chart.Series.Add(series);

public class StadiumDetails

{

      public string PlaceName { get; set; }

      public int NumSeats { get; set; }

      public int Price { get; set; }

      public CupDetails CupDetailsObj { get; set; }

}

public class CupDetails

{

      public string CupName { get; set; }

}

public class DataPointWithMulData

{

      public string Name { get; set; }

      public StadiumDetails StadiumObject { get; set; }

}

{% endhighlight %}

{% endtabs %}

### Binding array property to the chart

The SfChart supports array values for the XBindingPath and YBindingPath. XBindingPath and YBindingPath are bound with the property name in the corresponding index value. You can bind the same property with different index values.

The following code example demonstrates how to bind the array values for the XBindingPath and YBindingPath.

{% tabs %}

{% highlight xaml %}

<chart:SfChart>

      <chart:ColumnSeries x:Name="series" ItemsSource="{Binding Brands}"

                          XBindingPath="Brand[1]" YBindingPath="Count[0]" >

      </chart:ColumnSeries>

</chart:SfChart>


{% endhighlight %}

{% highlight C# %}

public class Model

{

      public string[] Brand { get; set; }

      public double[] Count { get; set; }

}

public class ViewModel

{

   public ViewModel()

   {

      Brands = new ObservableCollection<Model>();

      Brands.Add(new Model() { Brand = new string[] { "Reebok", "Adidas" }, Count 

= new  double[] { 34, 23 } });

      Brands.Add(new Model() { Brand = new string[] { "Benz", "Audi" }, Count 

=  new double[] { 50, 20 } });

      Brands.Add(new Model() { Brand = new string[] { "iPhone", "Nokia" }, Count 

= new double[] { 24, 30 } });

      Brands.Add(new Model() { Brand = new string[] { "Lenovo", "Acer" }, Count 

= new double[] { 38, 23 } });

      Brands.Add(new Model() { Brand = new string[] { "Fastrack", "Titan" },Count 

= new double[] { 27, 29 } });

   }

   public ObservableCollection<Model> Brands { get; set; }

}

private void CreateChart()

{

   ViewModel view = new ViewModel();

   SfChart chart = new SfChart();

   ColumnSeries series = new ColumnSeries();

   series.ItemsSource = view.Brands;

   series.XBindingPath = "Brand[1]";

   series.YBindingPath = "Count[0]";

   chart.Series.Add(series);

   grid.Children.Add(chart);

}


{% endhighlight %}


{% endtabs %}

### Listening Property Changes

You can notify the [`XBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.XYDataSeries.html#Syncfusion_UI_Xaml_Charts_XyDataSeries_YBindingPath) properties changes by setting [`ListenPropertyChange`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ListenPropertyChange) as true as shown in the below code snippet.

{% tabs %}

{% highlight xaml %}

<chart:ScatterSeries ScatterWidth="20" ScatterHeight="20"  Label="Coal" ListenPropertyChange="True"

ItemsSource="{Binding EnergyProductions}" Interior="#BCBCBC"

XBindingPath="ID" YBindingPath="Coal">

</chart:ScatterSeries>

{% endhighlight %}

{% highlight c# %}

ScatterSeries series = new ScatterSeries()
{

    ItemsSource = new ViewModel().EnergyProductions,

    XBindingPath = "ID",

    YBindingPath = "Coal",

    ScatterWidth = 20,

    ScatterHeight = 20,

    Label ="Coal",

    ListenPropertyChange=true,

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

Also, When enabling this property to the series you need to implements INotifyPropertyChanged to the underlying data object to make the chart listen to the property changes of your data object.

N> By default, the property change was disabled. So the dynamic updates will not get reflect in chart. You need to enable this property.

N> You can refer to our [WPF Charts](https://www.syncfusion.com/wpf-controls/charts) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Charts example](https://github.com/syncfusion/wpf-demos) to knows various chart types and how to easily configured with built-in support for creating stunning visual effects.

## See also

[`How to bind a list of Tuple in WPF Charts`](https://www.syncfusion.com/kb/11645/how-to-bind-a-list-of-tuple-in-wpf-charts)

[`How to bind the underlying DataTable model to the DataMarker Template in WPF Charts`](https://www.syncfusion.com/kb/11603/how-to-bind-the-underlying-datatable-model-to-the-datamarker-template-in-wpf-charts)

[`How to bind the SQL Database to WPF Charts`](https://www.syncfusion.com/kb/11595/how-to-bind-the-sql-database-to-wpf-charts)

[`How to bind the JSON data in WPF Chart`](https://www.syncfusion.com/kb/10929/how-to-bind-the-json-data-in-wpf-chart)

[`How to bind KeyValuePair collection in WPF Chart`](https://www.syncfusion.com/kb/10449/how-to-bind-keyvaluepair-collection-in-wpf-sfchart)

[`How to bind the series collection property using MVVM pattern`](https://www.syncfusion.com/kb/9406/how-to-bind-the-series-collection-property-using-mvvm-pattern)

[`How to bind data table in the Chart`](https://www.syncfusion.com/kb/5515/how-to-bind-data-table-in-the-sfchart)

[`How to create a real time Chart using MVVM in WPF`](https://www.syncfusion.com/kb/11416/how-to-create-a-real-time-chart-sfchart-using-mvvm-in-wpf)

[`How to bind the array property in Chart`](https://www.syncfusion.com/kb/4923/how-to-bind-the-array-property-in-sfchart)

[`How to generate dynamic number of series based on common items source`](https://www.syncfusion.com/kb/7578/how-to-generate-dynamic-number-of-series-based-on-common-items-source)

[`How to manage the empty values (NaN) in Chart`](https://www.syncfusion.com/kb/2900/how-to-manage-the-empty-values-nan-in-sfchart)
