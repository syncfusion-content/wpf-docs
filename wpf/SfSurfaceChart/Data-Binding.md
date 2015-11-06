---
layout: post
title: Data Binding | SfSurfaceChart | wpf | Syncfusion
description: data binding
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# Data Binding 

In surface chart, you cane apply data in a grid table format, that contains the number of rows and columns as shown in the following table. 

<table>
<tr>
<th>
</th><th>
Z0</th><th>
Z1</th><th>
Z2</th><th>
Zn</th></tr>
<tr>
<th>
X0</th><td>
Y00</td><td>
Y01</td><td>
Y02</td><td>
Y0n</td></tr>
<tr>
<th>
X1</th><td>
Y10</td><td>
Y11</td><td>
Y12</td><td>
Y1n</td></tr>
<tr>
<th>
X2</th><td>
Y20</td><td>
Y21</td><td>
Y22</td><td>
Y2n</td></tr>
<tr>
<th>
Xn</th><td>
Yn0</td><td>
Yn1</td><td>
Yn2</td><td>
Ynn</td></tr>
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