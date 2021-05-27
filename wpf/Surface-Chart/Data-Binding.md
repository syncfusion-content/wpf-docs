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

You can bind the IEnumerable collection property to surface chart ItemsSource property. Each item holds the model properties used to map surface XBindingPath, YBindingPath and ZBindingPath property. 

Also you must set the given data row and column size to surface chart RowSize and ColumnSize Property. 

{% tabs %}

{% highlight c# %}

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

{% highlight xaml %}

<Grid.DataContext>

     <local:ViewModel />
	 
</Grid.DataContext>

<chart:SfSurfaceChart  ItemsSource="{Binding DataValue}"   XBindingPath="X" YBindingPath="Y" ZBindingPath="Z" RowSize="{Binding RowSize}" ColumnSize="{Binding ColumnSize}" />

{% endhighlight %}

{% endtabs %}

### Using Data.AddPoints method

In this we can directly pass the data points to Data property **AddPoints****(****x****,****y****,****z****)** method. Here we no need to create items source and its member path. But we need to specify provided data rows and column size. 

{% tabs %}

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

{% highlight xaml %}

<chart:SfSurfaceChart  x:Name="surface" />
	
{% endhighlight %}

{% endtabs %}
