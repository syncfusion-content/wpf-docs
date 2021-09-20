---
layout: post
title: Data Binding in WPF Surface Chart control | Syncfusion
description: Learn here all about Data Binding support in Syncfusion WPF Surface Chart (SfSurfaceChart) control and more.
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# Data Binding in WPF Surface Chart (SfSurfaceChart)

In surface chart, you cane apply data in a grid table format, that contains the number of rows and columns as shown in the following table. 

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
X<sub>1</sub></th><td>
Y<sub>10</sub></td><td>
Y<sub>11</sub></td><td>
Y<sub>12</sub></td><td>
Y<sub>1n</sub></td></tr>
<tr>
<th>
X<sub>2</sub></th><td>
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

You can apply the data in surface in two ways. 

* Using ItemsSource property 
* Directly passing value through Data.AddPoints method.

### Using ItemsSource

You can bind the IEnumerable collection property to the [`ItemsSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ItemsSource) property of a surface chart. Each item holds the model properties that are used to map surface [`XBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_XBindingPath), [`YBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_YBindingPath) and [`ZBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ZBindingPath) property. 

Also, you must set the given data row and column size to surface chart [`RowSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_RowSize) and [`ColumnSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ColumnSize) Properties. 

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
        
        public ViewModel()
        {
            DataValue = new ObservableCollection<Data>();
            for (double x = -10; x < 10; x++)
            {
                for (double z = -10; z < 10; z++)
                {
                    double y = x*Math.Sin(z) + z*Math.Sin(x);
                    DataValue.Add(new Data() { X = x, Y = y, Z = z });
                }
            } 
         }       
         

        public ObservableCollection<Data> DataValue { get; set; }
        public int RowSize = 20;
        public int ColumnSize = 20;
    }
{% endhighlight %}
{% endtabs %}

### Using Data.AddPoints method

In this, you can directly pass the data points to the [`Data`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_Data) property [`AddPoints(x,y,z)`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DataPointCollection.html#Syncfusion_UI_Xaml_Charts_DataPointCollection_AddPoints_System_Double_System_Double_System_Double_) method. Here, you no need to create items source and its member path. But, you need to specify provided data rows and column size.

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
		double y = x*Math.Sin(z) + z*Math.Sin(x);
		
		surface.Data.AddPoints(x,y,z); //here we can directly pass data   
        
	 }
	 
 } 
 
 surface.RowSize = 20;
 
 surface.ColumnSize = 20;
 
}

{% endhighlight %}

{% endtabs %}
