# Data Binding 

In surface chart we should be apply data in grid table format, which contains the number of rows and columns as shown in the below table. 

<table>
<tr>
<td>
<br/><br/></td><td>
Z0<br/><br/></td><td>
Z1<br/><br/></td><td>
Z2<br/><br/></td><td>
Zn<br/><br/></td></tr>
<tr>
<td>
X0<br/><br/></td><td>
Y00<br/><br/></td><td>
Y01<br/><br/></td><td>
Y02<br/><br/></td><td>
Y0n<br/><br/></td></tr>
<tr>
<td>
X1<br/><br/></td><td>
Y10<br/><br/></td><td>
Y11<br/><br/></td><td>
Y12<br/><br/></td><td>
Y1n<br/><br/></td></tr>
<tr>
<td>
X2<br/><br/></td><td>
Y20<br/><br/></td><td>
Y21<br/><br/></td><td>
Y22<br/><br/></td><td>
Y2n<br/><br/></td></tr>
<tr>
<td>
Xn<br/><br/></td><td>
Yn0<br/><br/></td><td>
Yn1<br/><br/></td><td>
Yn2<br/><br/></td><td>
Ynn<br/><br/></td></tr>
</table>
We can apply the data in surface in two ways. 

* Using ItemsSource property 
* Directly passing value through Data.AddPoints method.

### Using ItemsSource

We have to bind the IEnumerable collection property to surface chart ItemsSource property. That property each items holds the model properties which are used to map surface XBindingPath, YBindingPath and ZBindingPath property. 

Also we need to set given data row and column size to surface chart RowSize and ColumnSize Property. 

{% highlight C# %}

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

{% highlight xml %}

<Grid.DataContext>
     <local:ViewModel />
</Grid.DataContext>
<chart:SfSurfaceChart  ItemsSource="{Binding DataValue}"   XBindingPath="X" YBindingPath="Y" ZBindingPath="Z" RowSize="{Binding RowSize}" ColumnSize="{Binding ColumnSize}" />

{% endhighlight %}

### Using Data.AddPoints method

In this we can directly pass the data points to Data property **AddPoints****(****x****,****y****,****z****)** method. Here we no need to create items source and its member path. But we need to specify provided data rows and column size. 

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

{% highlight xml %}

<chart:SfSurfaceChart  x:Name="surface" />
	
{% endhighlight %}