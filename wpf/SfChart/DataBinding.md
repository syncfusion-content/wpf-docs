---
layout: post
title: DataBinding| SfChart | Wpf | Syncfusion
description: databinding
platform: wpf
control: SfChart
documentation: ug
---

# DataBinding

SfChart offers Itemsource property to bind various datasource ranges from simple collection property to complex properties.

###Binding a simple collection to the chart

{% highlight C# %}

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

public ObservableCollection<GoldDemand> Demands { get; set; }       }

{% endhighlight %}

{% highlight xml %}

<syncfusion:SfChart >

<syncfusion:LineSeries

ItemsSource="{Binding Demands}"

XBindingPath="Demand"

YBindingPath="Year2010">

</syncfusion:LineSeries>



</syncfusion:SfChart>

{% endhighlight %}

###Binding complex property to the chart

The complex property binding feature enables you to access nested object reference property values to render the chart segment. 

{% tabs %}
{% highlight xml %}

<syncfusion:LineSeries ItemsSource="{Binding  DataWithMulData}" XBindingPath="StadiumObject.CupDetailsObj.CupName" YBindingPath="StadiumObject.NumSeats" /> 

{% endhighlight %}

{% highlight C# %}

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

###Binding array property to the chart

The SfChart supports array values for the XBindingPath and YBindingPath. XBindingPath and YBindingPath are bound with the property name in the corresponding index value. You can bind the same property with different index values.

The following code example demonstrates how to bind the array values for the XBindingPath and YBindingPath.

{% tabs %}
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

{% endhighlight %}

{% highlight xml %}



<chart:SfChart>

      <chart:ColumnSeries x:Name="series" ItemsSource="{Binding Brands}"

XBindingPath="Brand[1]" YBindingPath="Count[0]" >

      </chart:ColumnSeries>

</chart:SfChart>


{% endhighlight %}


{% highlight C# %}



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


