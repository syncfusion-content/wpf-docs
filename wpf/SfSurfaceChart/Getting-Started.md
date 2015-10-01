# Getting Started

This section helps you to get started with SfSurfaceChart control.

## Visual Structure

The following image helps you understand various elements in SfSurfaceChart, when you use it for the first time.

![](surface_chart_images/surface_chart_img2.jpeg)


* Surface Header – Represent the title of surface chart
* Wall – Represent the wall which bounds to surface chart. 
* Major Gridlines- Represent the surface axis gridline for surface chart.
* Color Bar- Display the value range in color for surface chart. 
* Axis Label- Display the label for surface axis. 
* Axis Header- Display the header of Surface axis.

## Create simple surface chart from XAML

This session demonstrates how to create a surface chart using SfSurfaceChart control from XAML. For that, we should add the **SfChart** assembly as a reference to our application.

### Add Assembly reference

1. Open the Add Reference window from your project.
2. Choose Windows > Extensions > Syncfusion.SfChart.WPF.
3. Add the following namespace in your XAML page.

{% highlight xml %}

xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Charts;assembly=Syncfusion.SfChart.WPF"<br/><br/></td></tr>

{% endhighlight %}
N> Adding the extension Syncfusion.SfChart.WPF, adds all the Syncfusion WPF controls. We can also add the SfChart reference alone from the following location. C:\Program Files (x86)\Syncfusion\Essential Studio<version>\Assemblies (4.0/4.5.1/4.6)

### Initialize the surface chart

We need to initialize the surface chart from the following namespace Syncfusion.UI.Xaml.SfChart

{% highlight xml %}

<syncfusion:SfSurfaceChart>

 </syncfusion:SfSurfaceChart>
 
 {% endhighlight %}

#Add Surface chart from Toolbox

Drag and drop the **SfSurfaceChart** control from the Toolbox to the required location, where the surface chart has to be displayed. We can select Toolbox from the View menu, when the toolbox window is not available in the project. Now the Toolbox window appears at the left end of the screen.

![](surface_chart_images/surface_chart_img3.jpeg)


The Syncfusion WPF reference is added to the application reference and the xmlns namespace is added to MainPage.xaml.

![](surface_chart_images/surface_chart_img4.jpeg)


![](surface_chart_images/surface_chart_img5.jpeg)


The following dataset is used to plot the surface chart. 

<table>
<tr>
<td>
X<br/><br/></td><td>
0<br/><br/></td><td>
0<br/><br/></td><td>
0<br/><br/></td><td>
1<br/><br/></td><td>
1<br/><br/></td><td>
1<br/><br/></td><td>
2<br/><br/></td><td>
2<br/><br/></td><td>
2<br/><br/></td></tr>
<tr>
<td>
Y<br/><br/></td><td>
3<br/><br/></td><td>
2<br/><br/></td><td>
1<br/><br/></td><td>
2<br/><br/></td><td>
1<br/><br/></td><td>
2<br/><br/></td><td>
1<br/><br/></td><td>
2<br/><br/></td><td>
3<br/><br/></td></tr>
<tr>
<td>
Z<br/><br/></td><td>
0<br/><br/></td><td>
1<br/><br/></td><td>
2<br/><br/></td><td>
0<br/><br/></td><td>
1<br/><br/></td><td>
2<br/><br/></td><td>
0<br/><br/></td><td>
1<br/><br/></td><td>
2<br/><br/></td></tr>
</table>
Before proceeding with the chart, create data model with the above details as follows.

{% highlight C# %}

public class Data
    {
        public double X { get; set; }
        public double Y { get; set; }
        public double Z { get; set; }
    }

{% endhighlight %}

Now, we have a data model property which hold values of each item in the collection.

{% highlight C# %}

public ObservableCollection<Data> DataValues { get; set; }
	
{% endhighlight %}
Also we have a property for row and column size in the given data’s. 

{% highlight C# %}

public int RowSize { get; set; }
public int ColumnSize { get; set; }

{% endhighlight %}

Add the values to the above defined collection property called DataValues, with the values illustrated in the above table.

{% highlight C# %}

DataValues.Add(new Data() {X = 0, Y = 3, Z = 0});
DataValues.Add(new Data() {X = 0, Y = 2, Z = 1});
DataValues.Add(new Data() {X = 0, Y = 1, Z = 2});
                            
DataValues.Add(new Data() { X = 1, Y = 2, Z = 0 });
DataValues.Add(new Data() { X = 1, Y = 1, Z = 1 });
DataValues.Add(new Data() { X = 1, Y = 2, Z = 2 });
                            
DataValues.Add(new Data() { X = 2, Y = 1, Z = 0 });
DataValues.Add(new Data() { X = 2, Y = 2, Z = 1 });
DataValues.Add(new Data() { X = 2, Y = 3, Z = 2 });

RowSize = 3;
ColumnSize = 3;

{% endhighlight %}
Now we can add the elements required for the above scenario to the Surface instance created.

### Add Data to surface chart

After we have populate data to the chart, we can bind the properties as shown in the below code.   

{% highlight xml %}
<Syncfusion:SfSurfaceChart ItemsSource="{Binding DataValues}"  XBindingPath="X"                              
                 YBindingPath="Y" ZBindingPath="Z" 
                 RowSize="{Binding RowSize}" 
                 ColumnSize="{Binding ColumnSize}" 
>

{% endhighlight %}

### Add Header to the surface chart

The header is acts as the title of the surface chart created, to identify its purpose. 

{% highlight xml %}

<Syncfusion:SfSurfaceChart Header="Simple Surface" FontSize="20" />
	
{% endhighlight %}

### Add Axes to surface chart

The following code example illustrates how to add XAxis, YAxis and ZAxis to the Surface chart.

{% highlight xml %}

<Syncfusion:SfSurfaceChart>

      <Syncfusion:SfSurfaceChart.XAxis>
             <Syncfusion:SurfaceAxis Header="X-Axis" />
      </Syncfusion:SfSurfaceChart.XAxis>

      <Syncfusion:SfSurfaceChart.YAxis>
             <Syncfusion:SurfaceAxis Header="Y-Axis" LabelFormat="0.0"/>
      </Syncfusion:SfSurfaceChart.YAxis>
      
      <Syncfusion:SfSurfaceChart.ZAxis>
             <Syncfusion:SurfaceAxis Header="Z-Axis"/>
      </Syncfusion:SfSurfaceChart.ZAxis>
 </Syncfusion:SfSurfaceChart>

{% endhighlight %}

N> SfSurfaceChart supports default axes ( i.e., all the axes will be generated automatically, if we didn’t define it explicitly).

### Add Surface Type

The following code example illustrate how to add surface type to the surface chart. 

{% highlight xml %}

<Syncfusion:SfSurfaceChart Type="Surface" />
	
{% endhighlight %}

### Add Color bar to the surface chart

The following code example illustrate how to add color bar to the surface chart

{% highlight xml %}

<Syncfusion:SfSurfaceChart.ColorBar>          
         <Syncfusion:ChartColorBar  DockPosition="Right"/>
</Syncfusion:SfSurfaceChart.ColorBar>

{% endhighlight %}
Now we have created a simple surface chart and following code example are for XAML. 

{% highlight xml %}

<Syncfusion:SfSurfaceChart Type="Surface"  
                           ItemsSource="{Binding DataValues}"  XBindingPath="X"    
                           YBindingPath="Y" ZBindingPath="Z" 
                           RowSize="{Binding RowSize}" 
                           ColumnSize="{Binding ColumnSize}">

    <Syncfusion:SfSurfaceChart.XAxis>
            <Syncfusion:SurfaceAxis Header="X-Axis" />
    </Syncfusion:SfSurfaceChart.XAxis>

    <Syncfusion:SfSurfaceChart.YAxis>
             <Syncfusion:SurfaceAxis Header="Y-Axis" LabelFormat="0.0"/>
    </Syncfusion:SfSurfaceChart.YAxis>

    <Syncfusion:SfSurfaceChart.ZAxis>
             <Syncfusion:SurfaceAxis Header="Z-Axis"/>
    </Syncfusion:SfSurfaceChart.ZAxis>

    <Syncfusion:SfSurfaceChart.ColorBar>
             <Syncfusion:ChartColorBar  DockPosition="Right"/>
    </Syncfusion:SfSurfaceChart.ColorBar>
</Syncfusion:SfSurfaceChart>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![C:/Users/sheiksyedm/Documents/My Received Files/Doc_Images/Simple Surface.png](surface_chart_images/surface_chart_img6.jpeg)


## Create simple surface chart from Code behind

This session demonstrates how to create a surface chart using SfSurfaceChart control from code behind. For that, we must add the **SfChart** assembly reference to your application.

### Add Assembly reference

1. Open the Add Reference window from your project.
2. Choose Windows > Extensions >Syncfusion.SfChart.WPF.
3. Add the following namespace in code behind

{% highlight C# %}

using Syncfusion.UI.Xaml.Charts;

{% endhighlight %}
The following section demonstrates a simple surface chart with the data discussed above table.

### Initialize the surface chart

{% highlight C# %}

SfSurfaceChart surface = new SfSurfaceChart(); 

{% endhighlight %}

### Add Data to surface chart

We can set the surface chart data in code behind by directly adding data points to Data property of surface chart using **AddPoints****(****x****,****y****,****z****)** method as shown in the below code.

{% highlight C# %}

SfSurfaceChart surface = new SfSurfaceChart();

//First Row
surface.Data.AddPoints(0, 3, 0);
surface.Data.AddPoints(0, 2, 1);
surface.Data.AddPoints(0, 2, 2);

//Second Row
surface.Data.AddPoints(1, 2, 0);
surface.Data.AddPoints(1, 1, 1);
surface.Data.AddPoints(1, 2, 2);

//Third Row
surface.Data.AddPoints(2, 1, 0);
surface.Data.AddPoints(2, 2, 1);
surface.Data.AddPoints(2, 3, 2);

surface.RowSize = 3;
surface.ColumnSize = 3;

{% endhighlight %}

### Add Header to the Surface chart

The header is acts as the title of the surface chart created, to identify its purpose. 

{% highlight C# %}

surface.Header = "Simple Surface";

{% endhighlight %}

### Add Axes to surface chart

The following code example illustrates how to add XAxis, YAxis and ZAxis to the surface chart.

{% highlight C# %}

//Add X axis to surface 
SurfaceAxis xAxis = new SurfaceAxis();
xAxis.Header = "X-Axis";
surface.XAxis = xAxis;

//Add Y axis to surface 
SurfaceAxis yAxis = new SurfaceAxis();
yAxis.Header = "Y-Axis";
surface.YAxis = yAxis;

//Add Z axis to surface 
SurfaceAxis zAxis = new SurfaceAxis();
zAxis.Header = "Z-Axis";
surface.ZAxis = zAxis;

{% endhighlight %}

N> SfSurfaceChart supports default axes ( i.e., all the axes will be generated automatically, if we didn’t define it explicitly).

### Add Surface Type

The following code example illustrate how to add surface type to the surface chart. 

{% highlight C# %}

surface.Type = SurfaceType.Surface;

{% endhighlight %}

### Add Color bar to the surface chart

The following code example illustrate how to add color bar to the surface chart

{% highlight C# %}

surface.ColorBar = new ChartColorBar() {DockPosition = ChartDock.Right};

{% endhighlight %}

Now we have created a simple surface chart and following code example are for code behind

{% highlight C# %}

SfSurfaceChart surface = new SfSurfaceChart();

surface.Header = "Simple Surface";

surface.Type = SurfaceType.Surface;

//First Row
surface.Data.AddPoints(0, 3, 0);
surface.Data.AddPoints(0, 2, 1);
surface.Data.AddPoints(0, 2, 2);

//Second Row
surface.Data.AddPoints(1, 2, 0);
surface.Data.AddPoints(1, 1, 1);
surface.Data.AddPoints(1, 2, 2);

//Third Row
surface.Data.AddPoints(2, 1, 0);
surface.Data.AddPoints(2, 2, 1);
surface.Data.AddPoints(2, 3, 2);

surface.RowSize = 3;
surface.ColumnSize = 3;

//Add X axis to surface 
SurfaceAxis xAxis = new SurfaceAxis();
xAxis.Header = "X-Axis";
surface.XAxis = xAxis;

//Add Y axis to surface 
SurfaceAxis yAxis = new SurfaceAxis();
yAxis.Header = "Y-Axis";
surface.YAxis = yAxis;

//Add Z axis to surface 
SurfaceAxis zAxis = new SurfaceAxis();
zAxis.Header = "Z-Axis";
surface.ZAxis = zAxis;
surface.ColorBar = new ChartColorBar() {DockPosition = ChartDock.Right};

{% endhighlight %}

The following output is displayed as a result of the above code example.

![C:/Users/sheiksyedm/Documents/My Received Files/Doc_Images/Simple Surface.png](surface_chart_images/surface_chart_img7.jpeg)