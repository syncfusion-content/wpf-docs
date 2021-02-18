---
layout: post
title: Getting Started with WPF SfChart | Syncfusion
description: Learn here about getting started with simple application using WPF chart (SfChart) control and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Getting Started with WPF Chart (SfChart)

This section explains you the steps required to populate the Chart with data, header, add data labels, legend and tooltips to the Chart. This section covers only the minimal features that you need to learn to get started with the Chart.

To get start quickly with WPF Chart, you can check this video:
<style>#WPFChartVideoTutorial{width : 90% !important; height:400px !important }</style>
<iframe id='WPFChartVideoTutorial' src='https://www.youtube.com/embed/5b8nEevQPC8'></iframe>

## Adding chart reference

Refer to this [article](https://help.syncfusion.com/wpf/add-syncfusion-controls) to learn how to add Syncfusion controls to Visual Studio projects in various ways. You can also refer to [this](https://help.syncfusion.com/wpf/control-dependencies) link to learn about the assemblies required for adding Chart to your project. 
 
## Initialize chart

Import the [`SfChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) namespace as follows in your respective Window.

{% tabs %} 

{% highlight xaml %} 

xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Charts;assembly=Syncfusion.SfChart.WPF"

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.UI.Xaml.Charts;

{% endhighlight %}

{% highlight VB %} 

Imports Syncfusion.UI.Xaml.Charts

{% endhighlight %}

{% endtabs %} 

Then initialize an empty chart with two axes as shown below,

{% tabs %} 

{% highlight xaml %} 

 <syncfusion:SfChart> 
      <syncfusion:SfChart.PrimaryAxis> 
           <syncfusion:CategoryAxis /> 
      </syncfusion:SfChart.PrimaryAxis> 
      <syncfusion:SfChart.SecondaryAxis> 
           <syncfusion:NumericalAxis/> 
      </syncfusion:SfChart.SecondaryAxis>
 </syncfusion:SfChart>

{% endhighlight %}

{% highlight C# %} 

SfChart chart = new SfChart();

CategoryAxis primaryAxis = new CategoryAxis();

chart.PrimaryAxis = primaryAxis; 
   
NumericalAxis secondaryAxis = new NumericalAxis();

chart.SecondaryAxis = secondaryAxis;

{% endhighlight %}

{% highlight VB %}

Dim chart As New SfChart()

Dim primaryAxis As New CategoryAxis () 

chart.PrimaryAxis = primaryAxis 

Dim secondaryAxis As New NumericalAxis ()  

chart.SecondaryAxis = secondaryAxis

{% endhighlight %}

{% endtabs %} 

Run the project and check if you get following output to make sure you have configured your project properly to add [`SfChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html).

![Initializing WPF Chart](Getting-Started_images/img1.png)

N> [`SfChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) supports default axes, so that these axes ([`PrimaryAxis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_PrimaryAxis) and [`SecondaryAxis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_SecondaryAxis)) will get generated automatically based upon the data bind to the chart, if you didn’t specify the axes explicitly.

## Initialize view model

Now, let us define a simple data model that represents a data point in [`SfChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html).

{% tabs %}  

{% highlight c# %}

public class Person   
{   
    public string Name { get; set; }

    public double Height { get; set; }
}

{% endhighlight %} 

{% highlight VB %}

Public Class Person

    Public Property Name As String

    Public Property Height As Double

End Class

{% endhighlight %} 

{% endtabs %} 


Next, create a view model class and initialize a list of `Person` objects as follows.

{% tabs %}  

{% highlight c# %}

public class ViewModel  
{
      public List<Person> Data { get; set; }      

      public ViewModel()       
      {
            Data = new List<Person>()
            {
                new Person { Name = "David", Height = 180 },
                new Person { Name = "Michael", Height = 170 },
                new Person { Name = "Steve", Height = 160 },
                new Person { Name = "Joel", Height = 182 }
            }; 
       }
 }

{% endhighlight %} 


{% highlight VB %}

Public Class ViewModel

    Public Property Data As List(Of Person)

    Public Sub New()
        Data = New List(Of Person)() From
        {
            New Person With {.Name = "David", .Height = 180},
            New Person With {.Name = "Michael", .Height = 170},
            New Person With {.Name = "Steve", .Height = 160},
            New Person With {.Name = "Joel", .Height = 182}
        }
    End Sub
End Class

{% endhighlight %}

{% endtabs %} 

Set the `ViewModel` instance as the `DataContext` of your window; this is done to bind properties of `ViewModel` to [`SfChart`.](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html)
 
N> Add namespace of `ViewModel` class to your XAML window if you prefer to set `DataContext` in XAML.

{% tabs %} 

{% highlight xaml %} 

<Window x:Class=" ChartDemo.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:ChartDemo "
        xmlns:syncfusion ="clr-namespace:Syncfusion.UI.Xaml.Charts;assembly=Syncfusion.SfChart.WPF"
        mc:Ignorable="d"
        Title="MainWindow" Height="350" Width="525">

    <Window.DataContext>
        <local:ViewModel/>
    </Window.DataContext>

</Window>


{% endhighlight %}

{% highlight C# %} 

this.DataContext = new ViewModel();

{% endhighlight %}

{% highlight VB %} 

Me.DataContext = New ViewModel()

{% endhighlight %}

{% endtabs %} 

## Populate chart with data

As we are going to visualize the comparison of heights in the data model, add [`ColumnSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ColumnSeries.html) to [`SfChart.Series`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Series) property, and then bind the `Data` property of the above `ViewModel` to the [`ColumnSeries.ItemsSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ItemsSource) property as follows.

N> You need to set [`XBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.XyDataSeries.html#Syncfusion_UI_Xaml_Charts_XyDataSeries_YBindingPath) properties, so that [`SfChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) would fetch values from the respective properties in the data model to plot the series.

{% tabs %}   

{% highlight xaml %}

<syncfusion:SfChart>
   
  <syncfusion:SfChart.PrimaryAxis>
    
      <syncfusion:CategoryAxis Header="Name" />             
   
  </syncfusion:SfChart.PrimaryAxis>

  <syncfusion:SfChart.SecondaryAxis>
  
      <syncfusion:NumericalAxis Header="Height(in cm)" />                        

  </syncfusion:SfChart.SecondaryAxis>
    
   <syncfusion:ColumnSeries  ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height" >
  </syncfusion:ColumnSeries>

 </syncfusion:SfChart> 

{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

//Adding horizontal axis to the chart 

CategoryAxis primaryAxis = new CategoryAxis();

primaryAxis.Header = "Name";      

chart.PrimaryAxis = primaryAxis;


//Adding vertical axis to the chart 

NumericalAxis secondaryAxis = new NumericalAxis();

secondaryAxis.Header = "Height(in cm)";          

chart.SecondaryAxis = secondaryAxis;


//Initialize the two series for SfChart
ColumnSeries series = new ColumnSeries();

series.ItemsSource = (new ViewModel()).Data;
series.XBindingPath = "Name";            
series.YBindingPath = "Height";         
            
//Adding Series to the Chart Series Collection
chart.Series.Add(series);

{% endhighlight %}

{% highlight VB %}

Dim chart As New SfChart()

'Adding horizontal axis to the chart 

Dim primaryAxis As New CategoryAxis()

primaryAxis.Header = "Name"
chart.PrimaryAxis = primaryAxis


'Adding vertical axis to the chart  

Dim secondaryAxis As New NumericalAxis()

secondaryAxis.Header = "Height(in cm)"

chart.SecondaryAxis = secondaryAxis        

'Initialize the two series for SfChart
Dim series As New ColumnSeries()

series.ItemsSource = New ViewModel().Demands
series.XBindingPath = "Name"
series.YBindingPath = "Height"
        
'Adding Series to the Chart Series Collection

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %} 

N> Syncfusion Chart also supports rendering combination of multiple series. Refer to [`this`](https://help.syncfusion.com/wpf/sfchart/area#multiple-area) for details.

## Add title

The header of the chart acts as the title to provide quick information to the user about the data being plotted in the chart. You can set title using the [`Header`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_Header) property of chart as follows.

{% tabs %} 

{% highlight xaml %}

<Grid>

   <syncfusion:SfChart Header="Chart"> 
   </syncfusion:SfChart> 

</Grid>

{% endhighlight %}

{% highlight C# %} 

chart.Header = "Chart";

{% endhighlight %}

{% highlight VB %}

chart.Header = "Chart"

{% endhighlight %}

{% endtabs %}  

Refer to [`this`](https://help.syncfusion.com/wpf/sfchart/area#chart-header) link to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) to customize chart header.


## Enable data labels

You can add data labels to improve the readability of the chart and it can be enabled using [`AdornmentInfo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfo.html) property of [`ChartSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeries.html). By default, there is no label displayed, you have to set [`ShowLabel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ShowLabel) property of [`ChartAdornmentInfo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfo.html) to True.

{% tabs %} 

{% highlight xaml %}

<syncfusion:SfChart>

	...

  <syncfusion:ColumnSeries > 
     <syncfusion:ColumnSeries.AdornmentsInfo>
          <syncfusion:ChartAdornmentInfo ShowLabel="True"/> 
     </syncfusion:ColumnSeries.AdornmentsInfo> 
  </syncfusion:ColumnSeries>     

	...

</syncfusion:SfChart>

{% endhighlight %}

{% highlight C# %} 

series.AdornmentsInfo = new ChartAdornmentInfo (){ ShowLabel = true }; 

{% endhighlight %}

{% highlight VB %} 

series.AdornmentsInfo = New ChartAdornmentInfo() With {.ShowLabel = True} 

{% endhighlight %}

{% endtabs %}  

Refer to [`this`](https://help.syncfusion.com/uwp/sfchart/adornments) link  to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) to customize chart adornments.

## Enable legend

You can enable legend using the [`SfChart.Legend`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_Legend) property as follows.

{% tabs %} 

{% highlight xaml %}

<syncfusion:SfChart>

	...

    <syncfusion:SfChart.Legend>

        <syncfusion:ChartLegend/>

    </syncfusion:SfChart.Legend>

    ...

</syncfusion:SfChart>

{% endhighlight %}

{% highlight C# %} 

chart.Legend = new ChartLegend (); 

{% endhighlight %}

{% highlight VB %} 

chart.Legend = New ChartLegend () 

{% endhighlight %}

{% endtabs %}  

Additionally, you need to set label for each series using the [`Label`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_Label) property of ChartSeries, which will be displayed in corresponding legend.

{% tabs %} 

{% highlight xaml %}

<syncfusion:SfChart>

	...

      <syncfusion:ColumnSeries Label="Heights" ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height" />

	...

</syncfusion:SfChart>

{% endhighlight %}

{% highlight C# %} 

ColumnSeries series = new ColumnSeries (); 
series.ItemsSource = (new ViewModel()).Data;
series.XBindingPath = "Name"; 
series.YBindingPath = "Height"; 
series.Label = "Heights";

{% endhighlight %}

{% highlight VB %} 

Dim series As New ColumnSeries () 
series.ItemsSource = New ViewModel().Data
series.XBindingPath = "Name" 
series.YBindingPath = "Height" 
series.Label = "Heights"

{% endhighlight %}

{% endtabs %}  

Refer to this [`link`](https://help.syncfusion.com/uwp/sfchart/legend) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) to customize legend.

## Enable tooltip

Tooltips are used to show information about the segment, when you click the segment. You can enable tooltip by setting series [`ShowTooltip`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ShowTooltip)  property to true.

{% tabs %} 

{% highlight xaml %}

<syncfusion:SfChart>

	...

   <syncfusion:ColumnSeries ShowTooltip="True" ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height"/>

	...

</syncfusion:SfChart> 

{% endhighlight %}

{% highlight C# %} 

ColumnSeries series = new ColumnSeries();
series.ItemsSource = (new ViewModel()).Data;
series.XBindingPath = "Name";          
series.YBindingPath = "Height";
series.ShowTooltip = true;

{% endhighlight %}

{% highlight VB %} 

Dim series As New ColumnSeries () 
series.ItemsSource = New ViewModel().Data
series.XBindingPath = "Name" 
series.YBindingPath = "Height" 
series.ShowTooltip = True

{% endhighlight %}

{% endtabs %}

Refer to [`this`](https://help.syncfusion.com/uwp/sfchart/interactive-features#tooltip) link to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) to customize tooltip.

The following code example gives you the complete code of above configurations.

{% tabs %} 

{% highlight xaml %}

<Window x:Class="Sample_WPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Sample_WPF"
        xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Charts;assembly=Syncfusion.SfChart.WPF"
        mc:Ignorable="d"
        Title="MainWindow" Height="350" Width="525">

    <!--Setting DataContext for SfChart-->
    <Window.DataContext>
        <local:ViewModel/>
    </Window.DataContext>
    
    <Grid>

        <syncfusion:SfChart Header="Chart" Height="300" Width="500">
            <!--Initialize the horizontal axis for SfChart-->
            <syncfusion:SfChart.PrimaryAxis>
                <syncfusion:CategoryAxis Header="Name" FontSize="14"/>
            </syncfusion:SfChart.PrimaryAxis>

            <!--Initialize the vertical axis for SfChart-->
            <syncfusion:SfChart.SecondaryAxis>
                <syncfusion:NumericalAxis Header="Height(in cm)" FontSize="14"/>
            </syncfusion:SfChart.SecondaryAxis>

            <!--Adding Legend to the SfChart-->
            <syncfusion:SfChart.Legend>
                <syncfusion:ChartLegend/>
            </syncfusion:SfChart.Legend>

            <!--Initialize the series for SfChart-->
            <syncfusion:ColumnSeries Label="Heights" ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height" ShowTooltip="True" >
                <syncfusion:ColumnSeries.AdornmentsInfo>
                    <syncfusion:ChartAdornmentInfo ShowLabel="True" >
                    </syncfusion:ChartAdornmentInfo>
                </syncfusion:ColumnSeries.AdornmentsInfo>
            </syncfusion:ColumnSeries>
                      
        </syncfusion:SfChart>

    </Grid>
</Window>
 
{% endhighlight %}

{% highlight C# %} 

using Syncfusion.UI.Xaml.Charts;

namespace ChartDemo
{
    
    public sealed partial class  MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            
            SfChart chart = new SfChart() { Header = "Chart", Height = 300, Width = 500 };

            //Adding horizontal axis to the chart 
            CategoryAxis primaryAxis = new CategoryAxis();
            primaryAxis.Header = "Name";
            primaryAxis.FontSize = 14;
            chart.PrimaryAxis = primaryAxis;

            //Adding vertical axis to the chart 
            NumericalAxis secondaryAxis = new NumericalAxis();
            secondaryAxis.Header = "Height(in cm)";
            secondaryAxis.FontSize = 14;
            chart.SecondaryAxis = secondaryAxis;

            //Adding Legends for the chart
            ChartLegend legend = new ChartLegend();
            chart.Legend = legend;

            //Initializing column series
            ColumnSeries series = new ColumnSeries();
            series.ItemsSource = (new ViewModel()).Data;
            series.XBindingPath = "Name";            
            series.YBindingPath = "Height";
            series.ShowTooltip = true;
            series.Label = "Heights";      

            //Setting adornment to the chart series
            series.AdornmentsInfo = new ChartAdornmentInfo() { ShowLabel = true };

            //Adding Series to the Chart Series Collection
            chart.Series.Add(series);
            this.Content = chart;
                      
        }
    }   
}

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Charts
Partial Public Class MainWindow
    Inherits Window   
    Public Sub New()
        InitializeComponent()

        Dim chart As New SfChart()
        chart.Header = "Chart"
        chart.Height = 300
        chart.Width = 500

        'Adding horizontal axis to the chart 

        Dim primaryAxis As New CategoryAxis()
        primaryAxis.Header = "Name"
        primaryAxis.FontSize = 14
        chart.PrimaryAxis = primaryAxis

        'Adding vertical axis to the chart  

        Dim secondaryAxis As New NumericalAxis()
        secondaryAxis.Header = "Height(in cm)"
        secondaryAxis.FontSize = 14
        chart.SecondaryAxis = secondaryAxis

        'Adding Legends for the chart
        Dim legend As New ChartLegend()
        chart.Legend = legend

        'Initializing column series
        Dim series As New ColumnSeries()
        series.ItemsSource = New ViewModel().Data
        series.XBindingPath = "Name"
        series.YBindingPath = "Height"
        series.Label = "Heights"
        series.ShowTooltip = True

        'Setting adornment to the chart series
        series.AdornmentsInfo = New ChartAdornmentInfo() With {.ShowLabel = True}       

        'Adding Series to the Chart Series Collection

        chart.Series.Add(series)

        Me.Content = chart

    End Sub
End Class

{% endhighlight %}

{% endtabs %}

The following chart is created as a result of the previous codes.

![Tooltip support in WPF Chart](Getting-Started_images/img3.png)

You can find the complete getting started sample from this [link](https://www.syncfusion.com/downloads/support/directtrac/general/ze/SfChart-GettingStarted-357667515).

## See also

[`How to create chart in VB .NET WPF`]( https://www.syncfusion.com/kb/10796/how-to-create-chart-in-vb-net-wpf)

[`How to create a chart control in WPF application using XAML`](https://www.syncfusion.com/kb/10786/how-to-create-a-chart-control-in-wpf-application-using-xaml)

[`How to create chart in C# WPF`](https://www.syncfusion.com/kb/10783/how-to-create-chart-in-c-wpf)

[`How to create Chart in F# WPF`](https://www.syncfusion.com/kb/11663/how-to-create-chart-in-f-wpf)

[`How to add Context Menu for WPF Chart`](https://www.syncfusion.com/kb/10726/how-to-add-contextmenu-for-wpf-chart)

[`How to add WPF SfChart inside the SfDataGrid`](https://www.syncfusion.com/kb/10386/how-to-add-wpf-sfchart-inside-the-sfdatagrid)

[`How to add footer content to WPF Chart`](https://www.syncfusion.com/kb/10201/how-to-add-footer-content-to-wpf-sfchart)

[`How to access data from Meta Trader to chart using TradePlatform.Net in WPF`](https://www.syncfusion.com/kb/7932/how-to-access-data-from-metatrader-to-sfchart-using-tradeplatform-net-in-wpf)

[`How to synchronize the selection between the chart and data grid`](https://www.syncfusion.com/kb/3579/how-to-synchronize-the-selection-between-the-chart-and-data-grid)

[`How to achieve series drilldown behavior in Chart`](https://www.syncfusion.com/kb/2692/how-to-achieve-series-drilldown-behaviour-in-sfchart)

[`How to generate dynamic number of series based on common items source`](https://www.syncfusion.com/kb/7578/how-to-generate-dynamic-number-of-series-based-on-common-items-source)

[`How to display the chart area alone in Chart`](https://www.syncfusion.com/kb/5477/how-to-display-the-chart-area-alone-in-sfchart)

[`How to redraw the chart while dragging the series out of the range`](https://www.syncfusion.com/kb/5366/how-to-redraw-the-chart-while-dragging-the-series-out-of-the-range)

[`How to create a real time Chart using MVVM in WPF`](https://www.syncfusion.com/kb/11416/how-to-create-a-real-time-chart-sfchart-using-mvvm-in-wpf)

[`How to add watermark to chart`](https://www.syncfusion.com/kb/5225/how-to-add-watermark-to-chart)

## Theme

SfChart supports various built-in themes. Refer to the below links to apply themes for the SfChart,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF SfChart](Getting-Started_images/theme.png)