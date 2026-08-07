---
layout: post
title: Data Binding in WPF Surface Chart | Syncfusion®
description: Data binding in the WPF Surface Chart connects data sources to surface visualizations, enabling dynamic updates and data-driven rendering.
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# Data Binding in WPF Surface Chart

In a surface chart, you can apply data in a grid table format that contains a number of rows and columns, as shown in the following table. 

<table>
<tr>
<th>
</th><th>
Z<sub>0</sub></th><th>
Z<sub>1</sub></th><th>
Z<sub>2</sub></th><th>
Z<sub>n</sub></th></tr>
<tr>
<th>
X<sub>1</sub></th><td>
Y<sub>00</sub></td><td>
Y<sub>01</sub></td><td>
Y<sub>02</sub></td><td>
Y<sub>0n</sub></td></tr>
<tr>
<th>
X<sub>2</sub></th><td>
Y<sub>10</sub></td><td>
Y<sub>11</sub></td><td>
Y<sub>12</sub></td><td>
Y<sub>1n</sub></td></tr>
<tr>
<th>
X<sub>3</sub></th><td>
Y<sub>20</sub></td><td>
Y<sub>21</sub></td><td>
Y<sub>22</sub></td><td>
Y<sub>2n</sub></td></tr>
<tr>
<th>
X<sub>n</sub></th><td>
Y<sub>n0</sub></td><td>
Y<sub>n1</sub></td><td>
Y<sub>n2</sub></td><td>
Y<sub>nn</sub></td></tr>
</table>

You can apply the data to a surface in two ways. 

* Using the ItemsSource property.
* Directly passing values through the Data.AddPoints method.

### Using ItemsSource

You can bind the IEnumerable collection property to the [`ItemsSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ItemsSource) property of a surface chart. Each item holds the model properties that are used to map the surface [`XBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_XBindingPath), [`YBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_YBindingPath), and [`ZBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ZBindingPath) properties. 

Additionally, you must set the data row and column size to the surface chart [`RowSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_RowSize) and [`ColumnSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ColumnSize) properties. 

{% tabs %}

{% highlight xaml %}

    <Grid.DataContext>
     <local:ViewModel />	 
    </Grid.DataContext>

         <chart:SfSurfaceChart ItemsSource="{Binding DataValue}"  XBindingPath="X"  
                              YBindingPath="Y" ZBindingPath="Z" RowSize="{Binding RowSize}"
                              ColumnSize="{Binding ColumnSize}">
        </chart:SfSurfaceChart>    

{% endhighlight %}
`
{% highlight c# %}

SfSurfaceChart chart = new SfSurfaceChart();
chart.SetBinding(SfSurfaceChart.ItemsSourceProperty, "DataValue");
chart.SetBinding(SfSurfaceChart.RowSizeProperty, "RowSize");
chart.SetBinding(SfSurfaceChart.ColumnSizeProperty, "ColumnSize");
chart.XBindingPath = "X";
chart.YBindingPath = "Y";
chart.ZBindingPath = "Z";
ChartColorBar colorBar = new ChartColorBar();
colorBar.DockPosition = ChartDock.Right;
colorBar.ShowLabel = true;
chart.ColorBar = colorBar;
grid.Children.Add(chart);

public class Data
{
    public double X { get; set; }
    public double Y { get; set; }
    public double Z { get; set; }
}

public class ViewModel
{
    public ObservableCollection<Data> DataValue { get; set; }
    public int RowSize = 20;
    public int ColumnSize = 20;

    public ViewModel()
    {
        DataValue = new ObservableCollection<Data>();
        for (double x = -10; x < 10; x++)
        {
            for (double z = -10; z < 10; z++)
            {
                double y = x * Math.Sin(z) + z * Math.Sin(x);
                DataValue.Add(new Data() { X = x, Y = y, Z = z });
            }
        }
    }
}

{% endhighlight %}
{% endtabs %}

### Using Data.AddPoints method

In this approach, you can directly pass the data points to the [`AddPoints(x, y, z)`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DataPointCollection.html#Syncfusion_UI_Xaml_Charts_DataPointCollection_AddPoints_System_Double_System_Double_System_Double_) method of the [`Data`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_Data) property. Here, you do not need to create an items source and its member path. However, you need to specify the data row and column size.

{% tabs %}

{% highlight xaml %}

    <chart:SfSurfaceChart  x:Name="surface" />
	
{% endhighlight %}

{% highlight c# %}

public MainWindow()
{
    InitializeComponent();

    SetData();
}

private void SetData()
{
    for (double x = -10; x < 10; x++)
    {
        for (double z = -10; z < 10; z++)
        {
            double y = x * Math.Sin(z) + z * Math.Sin(x);
            // Here you can directly pass data.
            surface.Data.AddPoints(x, y, z);
        }
    }

    surface.RowSize = 20;
    surface.ColumnSize = 20;
}

{% endhighlight %}

{% endtabs %}
