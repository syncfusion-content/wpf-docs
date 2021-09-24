---
layout: post
title: Getting Started with WPF Surface Chart control | Syncfusion
description: Learn here about getting started with Syncfusion WPF Surface Chart (SfSurfaceChart) control, its elements and more.
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# Getting Started with WPF Surface Chart (SfSurfaceChart)

This section helps you get started with [`SfSurfaceChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html) control.

## Visual Structure

The following image helps you understand various elements in SfSurfaceChart when you use it for the first time.

![Visual Structure](surface_chart_images/surface_chart_img2.jpeg)


* Surface Header – Represents the title of surface chart
* Wall – Represents the wall that bounds the surface chart. 
* Major Gridlines- Represents the surface axis gridline for surface chart.
* Color Bar- Displays the value range in color for surface chart. 
* Axis Label- Displays the label for surface axis. 
* Axis Header- Displays the header of Surface axis.

## Create simple surface chart from XAML

This section demonstrates how to create a surface chart using the `SfSurfaceChart` control from XAML. You can add the [`SfChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) assembly as a reference to your application to create a surface chart using SfSurfaceChart control from XAML.

### Add Assembly reference

1. Open the Add Reference window from your project.
2. Choose Windows > Extensions > Syncfusion.SfChart.WPF.
3. Add the following namespace in your XAML page.

{% highlight xaml %}

xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Charts;assembly=Syncfusion.SfChart.WPF"

{% endhighlight %}

N> Adding the extension Syncfusion.SfChart.WPF, adds all the Syncfusion WPF controls. You can also add the SfChart reference alone from the following location. C:\Program Files (x86)\Syncfusion\Essential Studio<version>\Assemblies (4.0/4.5.1/4.6)

### Initialize the surface chart

You need to initialize the surface chart from the following namespace Syncfusion.UI.Xaml.Charts.

{% tabs %}

{% highlight xaml %}

       <syncfusion:SfSurfaceChart>

       </syncfusion:SfSurfaceChart>
 
{% endhighlight %}

{% endtabs %}

## Add Surface chart from Toolbox

Drag the [`SfSurfaceChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html) control from the Toolbox to the required location, where the surface chart should be displayed. You can select Toolbox from the View menu, when the toolbox window is not available in the project. The Toolbox window appears on the left side of the screen.

![Add Surface chart from Toolbox](surface_chart_images/surface_chart_img3.jpeg)

The Syncfusion WPF reference is added to the application reference and the xmlns namespace is added to MainPage.xaml.

![Solution explorer](surface_chart_images/surface_chart_img4.jpeg)


![Data set](surface_chart_images/surface_chart_img5.jpeg)


The following dataset is used to plot the surface chart. 

<table>
<tr>
<th>
X</th><td>
0</td><td>
0</td><td>
0</td><td>
1</td><td>
1</td><td>
1</td><td>
2</td><td>
2</td><td>
2</td></tr>
<tr>
<th>
Y</th><td>
3</td><td>
2</td><td>
1</td><td>
2</td><td>
1</td><td>
2</td><td>
1</td><td>
2</td><td>
3</td></tr>
<tr>
<th>
Z</th><td>
0</td><td>
1</td><td>
2</td><td>
0</td><td>
1</td><td>
2</td><td>
0</td><td>
1</td><td>
2</td></tr>
</table>

Before proceeding with the chart, create data model with the above details as follows.

{% highlight c# %}

public class Data
{
	public double X { get; set; }
	public double Y { get; set; }
	public double Z { get; set; }
}

{% endhighlight %}

Now, you have a data model property which hold values of each item in the collection.

{% highlight c# %}

public ObservableCollection<Data> DataValues { get; set; }
	
{% endhighlight %}

Also you have a property for row and column size in the given data. 

{% highlight c# %}

public int RowSize { get; set; }

public int ColumnSize { get; set; }

{% endhighlight %}

Add the values to the above defined collection property called DataValues, with the values illustrated in the above table.

{% highlight c# %}

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
Now you can add the elements required for the above scenario to the Surface instance created.

### Add data to surface chart

After you populate the data to the chart, you can bind the properties as shown in the following code example. 

{% tabs %}

{% highlight xaml %}

       <syncfusion:SfSurfaceChart ItemsSource="{Binding DataValues}"  XBindingPath="X"   
                           
                 YBindingPath="Y" ZBindingPath="Z" 
				 
                 RowSize="{Binding RowSize}" 
				 
                 ColumnSize="{Binding ColumnSize}" >

{% endhighlight %}

{% endtabs %}

### Add Header to the surface chart

The header acts as the title of the surface chart created, to identify its purpose. 

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSurfaceChart Header="Simple Surface" FontSize="20" />
	
{% endhighlight %}

{% endtabs %}

### Add Axes to surface chart

The following code example illustrates how to add XAxis, YAxis and ZAxis to the Surface chart.

{% tabs %}

{% highlight xaml %}

       <syncfusion:SfSurfaceChart ItemsSource="{Binding DataValues}"  XBindingPath="X"  
                              YBindingPath="Y" ZBindingPath="Z" RowSize="{Binding RowSize}"
                              ColumnSize="{Binding ColumnSize}">

            <syncfusion:SfSurfaceChart.XAxis>

                <syncfusion:SurfaceAxis Header="X-Axis" />

            </syncfusion:SfSurfaceChart.XAxis>

            <syncfusion:SfSurfaceChart.YAxis>

                <syncfusion:SurfaceAxis Header="Y-Axis" LabelFormat="0.0"/>

            </syncfusion:SfSurfaceChart.YAxis>

            <syncfusion:SfSurfaceChart.ZAxis>

                <syncfusion:SurfaceAxis Header="Z-Axis"/>

            </syncfusion:SfSurfaceChart.ZAxis>

        </syncfusion:SfSurfaceChart>

{% endhighlight %}

{% endtabs %}

N> SfSurfaceChart supports default axes, all the axes are generated automatically, even when it has not been defined explicitly.

### Add Surface Type

The following code example illustrates how to add surface type to the surface chart. 

{% tabs %}

{% highlight xaml %}

       <syncfusion:SfSurfaceChart Type="Surface" />
	
{% endhighlight %}

{% endtabs %}

### Add Color bar to the surface chart

The following code example illustrates how to add color bar to the surface chart

{% tabs %}

{% highlight xaml %}

         <syncfusion:SfSurfaceChart.ColorBar>
                <syncfusion:ChartColorBar ShowLabel="True" DockPosition="Right"/>
         </syncfusion:SfSurfaceChart.ColorBar>

{% endhighlight %}

{% endtabs %}

Now you have created a simple surface chart. The following code example is for XAML. 

{% highlight xaml %}

       <syncfusion:SfSurfaceChart Type="Surface"  Tilt="15" Rotate="30"

                           ItemsSource="{Binding DataValues}"  XBindingPath="X"    
						   
                           YBindingPath="Y" ZBindingPath="Z" 
						   
                           RowSize="{Binding RowSize}" 
						   
                           ColumnSize="{Binding ColumnSize}">

            <syncfusion:SfSurfaceChart.XAxis>

                <syncfusion:SurfaceAxis Header="X-Axis" />

            </syncfusion:SfSurfaceChart.XAxis>

            <syncfusion:SfSurfaceChart.YAxis>

                <syncfusion:SurfaceAxis Header="Y-Axis" LabelFormat="0.0"/>

            </syncfusion:SfSurfaceChart.YAxis>

            <syncfusion:SfSurfaceChart.ZAxis>

                <syncfusion:SurfaceAxis Header="Z-Axis"/>

            </syncfusion:SfSurfaceChart.ZAxis>

            <syncfusion:SfSurfaceChart.ColorBar>

                <syncfusion:ChartColorBar  DockPosition="Right"/>

            </syncfusion:SfSurfaceChart.ColorBar>

        </syncfusion:SfSurfaceChart>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![Simple Surface](surface_chart_images/surface_chart_img6.jpeg)

## Create a simple surface chart from Code behind.

This section demonstrates how to create a surface chart using SfSurfaceChart control from code behind. For that, you can add the **SfChart** assembly reference to your application.

### Add Assembly reference

1. Open the Add Reference window from your project.
2. Choose Windows > Extensions >Syncfusion.SfChart.WPF.
3. Add the following namespace in code behind

{% highlight c# %}

using Syncfusion.UI.Xaml.Charts;

{% endhighlight %}

The following section demonstrates a simple surface chart with the data discussed in the above table.

### Initialize the surface chart

{% highlight c# %}

SfSurfaceChart surface = new SfSurfaceChart(); 

{% endhighlight %}

### Add Data to surface chart

You can set the surface chart data in code behind, by directly adding data points to the Data property of surface chart using **AddPoints****(****x****,****y****,****z****)** method as shown in the following code example.

{% highlight c# %}

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
grid.Children.Add(surface);

{% endhighlight %}

### Add Header to the Surface chart

The header acts as the title of the surface chart created, to identify its purpose. 

{% highlight c# %}

            SfSurfaceChart chart = new SfSurfaceChart();
            chart.Header = "Simple Surface";
            chart.FontSize = 20;
            grid.Children.Add(chart);

{% endhighlight %}

### Add Axes to surface chart

The following code example illustrates how to add XAxis, YAxis and ZAxis to the surface chart.

{% highlight c# %}

            SfSurfaceChart chart = new SfSurfaceChart();
            chart.SetBinding(SfSurfaceChart.ItemsSourceProperty, "DataValues");
            chart.SetBinding(SfSurfaceChart.RowSizeProperty, "RowSize");
            chart.SetBinding(SfSurfaceChart.ColumnSizeProperty, "ColumnSize");
            chart.XBindingPath = "X";
            chart.YBindingPath = "Y";
            chart.ZBindingPath = "Z";
          
          //Add X axis to surface 
            SurfaceAxis xAxis = new SurfaceAxis();
            xAxis.Header = "X-Axis";
            chart.XAxis = xAxis;

          //Add Y axis to surface 
            SurfaceAxis yAxis = new SurfaceAxis();
            yAxis.Header = "Y-Axis";
            yAxis.LabelFormat = "0.0";
            chart.YAxis = yAxis;

          //Add Z axis to surface 
            SurfaceAxis zAxis = new SurfaceAxis();
            zAxis.Header = "Z-Axis";
            chart.ZAxis = zAxis;
            grid.Children.Add(chart);

{% endhighlight %}

N> SfSurfaceChart supports default axes, where all the axes are generated automatically, even when they are not defined explicitly.

### Add Surface Type

The following code example illustrates how to add surface type to the surface chart. 

{% highlight c# %}

             SfSurfaceChart chart = new SfSurfaceChart();
             chart.Type = SurfaceType.Surface;
             grid.Children.Add(chart);

{% endhighlight %}

### Add ColorBar to the surface chart

The following code example illustrates how to add color bar to the surface chart.

{% highlight c# %}

              ChartColorBar colorBar = new ChartColorBar();
              colorBar.DockPosition = ChartDock.Right;
              colorBar.ShowLabel = true;
              chart.ColorBar = colorBar;

{% endhighlight %}

Now, you have created a simple surface chart. The following code example is for code behind and data can be populated either by using the[`ItemsSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ItemsSource)  property or by using the [`AddPoints`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DataPointCollection.html#Syncfusion_UI_Xaml_Charts_DataPointCollection_AddPoints_System_Double_System_Double_System_Double_) method of [`Data`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_Data) property in surface chart.

{% highlight c# %}

            SfSurfaceChart chart = new SfSurfaceChart();
            chart.SetBinding(SfSurfaceChart.ItemsSourceProperty, "DataValues");
            chart.SetBinding(SfSurfaceChart.RowSizeProperty, "RowSize");
            chart.SetBinding(SfSurfaceChart.ColumnSizeProperty, "ColumnSize");
            chart.XBindingPath = "X";
            chart.YBindingPath = "Y";
            chart.ZBindingPath = "Z";          
            grid.Children.Add(chart);

             or

            SfSurfaceChart surface = new SfSurfaceChart();
            surface.Header = "Simple Surface";
            surface.Tilt = 15;
            surface.Rotate = 30;
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

            ChartColorBar colorBar = new ChartColorBar();
            colorBar.DockPosition = ChartDock.Right;
            colorBar.ShowLabel = true;
            surface.ColorBar = colorBar;
            this.Content = surface;

{% endhighlight %}

The following output is displayed as a result of the above code example.

You can get the complete getting started sample [`here`](https://www.syncfusion.com/downloads/support/directtrac/general/ze/SurfaceChartDemo-1998279060).

![simple surface from Code behind](surface_chart_images/surface_chart_img7.jpeg)
