---
layout: post
title: Getting Started with WPF SfChart3D | Syncfusion
description: Learn here about getting started with simple application using WPF chart (SfChart3D) control and more details.
platform: wpf
control: SfChart3D
documentation: ug
---

# Getting Started with WPF Charts (SfChart3D)

This section explains you the steps required to populate the Chart with data, header, add data labels, legend and tooltips to the Chart. This section covers only the minimal features that you need to learn to get started with the Chart.

## Adding chart reference

Refer to this [article](https://help.syncfusion.com/wpf/add-syncfusion-controls) to learn how to add Syncfusion controls to Visual Studio projects in various ways. You can also refer to [this](https://help.syncfusion.com/wpf/control-dependencies) link to learn about the assemblies required for adding Chart to your project. 

## Initialize chart

Import the SfChart namespace in your XAML page.

{% tabs %}
  
{% highlight xaml %}

 xmlns:chart="clr-namespace:Syncfusion.UI.Xaml.Charts;assembly=Syncfusion.SfChart.WPF"

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Charts;

{% endhighlight %}

{% endtabs %}

Then initialize an empty chart with two axes as shown below,

{% tabs %}

{% highlight xaml %}

    <chart:SfChart3D >
            
        <!--PrimaryAxis-->
        <chart:SfChart3D.PrimaryAxis>
            <chart:DateTimeAxis3D/>
        </chart:SfChart3D.PrimaryAxis>
        <!--SecondaryAxis-->
        <chart:SfChart3D.SecondaryAxis>
            <chart:NumericalAxis3D/>
        </chart:SfChart3D.SecondaryAxis>

    </chart:SfChart3D>

{% endhighlight %}

{% highlight C# %}

     SfChart3D Chart3D = new SfChart3D()
        {
            PrimaryAxis = new DateTimeAxis3D(),

            SecondaryAxis = new NumericalAxis3D(),
        };

{% endhighlight %}

{% endtabs %}

![Chart 3D support in WPF](3D-Charts_images/Chart-3D-GettingStarted_init.png)


## Initialize view model

Since, the above step will produce only an empty column 3D chart, plotting data must be added to the chart. This step illustrates how to create a sample data source. The data source must implement the IEnumerable interface.

{% highlight C# %}

    public class UserProfile
    {
        public DateTime TimeStamp { get; set; }
        public double NoOfUsers { get; set; }
    }

{% endhighlight %}

Next, create a view model class and initialize a list of `UserProfile` objects as follows.

{% highlight C# %}

    public class UsersViewModel
    {
        public UsersViewModel()
        {
            this.UsersList = new ObservableCollection<UserProfile>();

            DateTime date = DateTime.Today;

            UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 1000 });
            UsersList.Add(new UserProfile { TimeStamp = date.AddHours(1), NoOfUsers = 5000 });
            UsersList.Add(new UserProfile { TimeStamp = date.AddHours(1.5), NoOfUsers = 3000 });
            UsersList.Add(new UserProfile { TimeStamp = date.AddHours(2), NoOfUsers = 4000 });
            UsersList.Add(new UserProfile { TimeStamp = date.AddHours(2.5), NoOfUsers = 2000 });
            UsersList.Add(new UserProfile { TimeStamp = date.AddHours(3), NoOfUsers = 1000 });
        }
        public ObservableCollection<UserProfile> UsersList { get; set; }

    }

{% endhighlight %}

Set the ViewModel instance as the DataContext of your window; this is done to bind properties of ViewModel.

N> Add namespace of `ViewModel` class to your XAML window if you prefer to set `DataContext` in XAML.


{% tabs %} 

{% highlight xaml %} 

<Window x:Class="GettingStarted_3DCharts.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:GettingStarted_3DCharts "
        xmlns:chart ="clr-namespace:Syncfusion.UI.Xaml.Charts;assembly=Syncfusion.SfChart.WPF"
        mc:Ignorable="d"
        Title="MainWindow" Height="350" Width="525">

    <Window.DataContext>
        <local:UsersViewModel/>
    </Window.DataContext>

</Window>


{% endhighlight %}

{% highlight C# %} 

this.DataContext = new UsersViewModel();

{% endhighlight %}

{% endtabs %}

## Populate chart with data

As we are going to visualize the comparison of heights in the data model, add ColumnSeries to SfChart3D.Series property, and then bind the Data property of the above ViewModel to the ColumnSeries.ItemsSource property as follows.

N> You need to set [`XBindingPath`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~XBindingPath.html) and [`YBindingPath`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XyDataSeries~YBindingPath.html) properties, so that [`SfChart`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart.html) would fetch values from the respective properties in the data model to plot the series.


{% tabs %}

{% highlight xaml %}

  <chart:SfChart3D x:Name="Chart3D" Width="500" Height="500">
            
        <!--PrimaryAxis-->
        <chart:SfChart3D.PrimaryAxis>
            <chart:DateTimeAxis3D/>
        </chart:SfChart3D.PrimaryAxis>
        <!--SecondaryAxis-->
        <chart:SfChart3D.SecondaryAxis>
            <chart:NumericalAxis3D/>
        </chart:SfChart3D.SecondaryAxis>

        <chart:ColumnSeries3D ItemsSource="{Binding UsersList}" XBindingPath="TimeStamp"
            YBindingPath="NoOfUsers"></chart:ColumnSeries3D>
            
    </chart:SfChart3D>

{% endhighlight %}

{% highlight c# %}

    SfChart3D chart3D = new SfChart3D();

    chart3D.PrimaryAxis = new CategoryAxis3D();

    chart3D.SecondaryAxis = new NumericalAxis3D();

    ColumnSeries3D series = new ColumnSeries3D()
        {
            ItemsSource = new UsersViewModel().UsersList,
            XBindingPath = "TimeStamp",
            YBindingPath = "NoOfUsers"
        };

    Chart3D.Series.Add(series);

{% endhighlight %}

{% endtabs %}

## Add Title

The header of the chart acts as the title to provide quick information to the user about the data being plotted in the chart. You can set title using the [`Header`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~Header.html) property of chart as follows.

{% tabs %} 

{% highlight xaml %}

<Grid>

   <chart:SfChart3D Header="Chart"> 
   </chart:SfChart3D> 

</Grid>

{% endhighlight %}

{% highlight C# %} 

    SfChart3D chart3D = new SfChart3D();
    chart3D.Header = "Chart";

{% endhighlight %}

{% endtabs %}  

## Enable data labels

You can add data labels to improve the readability of the chart and it can be enabled using [`AdornmentInfo`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfo.html) property of [`ChartSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeries.html). By default, there is no label displayed, you have to set [`ShowLabel`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ShowLabel.html) property of [`ChartAdornmentInfo`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfo.html) to True.

{% tabs %} 

{% highlight xaml %}

    <Grid>
        <chart:SfChart3D >

        ...
        
            <chart:ColumnSeries3D ItemsSource="{Binding UsersList}" XBindingPath="TimeStamp"
            YBindingPath="NoOfUsers">
                <chart:ColumnSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D></chart:ChartAdornmentInfo3D>
                </chart:ColumnSeries3D.AdornmentsInfo>
            </chart:ColumnSeries3D>
        ...

        </chart:SfChart3D>

    </Grid>

{% endhighlight %}

{% highlight C# %} 

series.AdornmentsInfo = new ChartAdornmentInfo (){ ShowLabel = true }; 

{% endhighlight %}

{% endtabs %}  

Refer to [`Adornments`](https://help.syncfusion.com/wpf/SfChart3D/Adornments) to learn more about the options to customize chart adornments.

## Enable legend

You can enable legend using the [`Legend`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartBase~Legend.html) property as follows.

{% tabs %} 

{% highlight xaml %}

 <Grid>
        <chart:SfChart3D >

        ...
        
        <!--Legend-->
        <chart:SfChart3D.Legend>
            <chart:ChartLegend></chart:ChartLegend>
        </chart:SfChart3D.Legend>
        ...

        </chart:SfChart3D>

    </Grid>

{% endhighlight %}

{% highlight C# %} 

chart.Legend = new ChartLegend (); 

{% endhighlight %}

{% endtabs %}  

Additionally, you need to set label for each series using the [`Label`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~Label.html) property of ChartSeries, which will be displayed in corresponding legend.

{% tabs %} 

{% highlight xaml %}

    <chart:SfChart3D >

	...

        <chart:ColumnSeries3D Label="UserProfile" ItemsSource="{Binding UsersList}" XBindingPath="TimeStamp"
            YBindingPath="NoOfUsers" >

        </chart:ColumnSeries3D>

	...

    </chart:SfChart3D>

{% endhighlight %}

{% highlight C# %} 

    ColumnSeries3D series = new ColumnSeries3D()
        {
            ItemsSource = new UsersViewModel().UsersList,
            XBindingPath = "TimeStamp",
            YBindingPath = "NoOfUsers",
            Label = "UserProfile"
        };


{% endhighlight %}

{% endtabs %}  

## Enable tooltip

Tooltips are used to show information about the segment, when you click the segment. You can enable tooltip by setting series [`ShowTooltip`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~ShowTooltip.html)  property to true.

{% tabs %} 

{% highlight xaml %}

    <chart:SfChart3D >

	...

        <chart:ColumnSeries3D Label="UserProfile" ItemsSource="{Binding UsersList}" XBindingPath="TimeStamp"
            YBindingPath="NoOfUsers" ShowTooltip="True" >

        </chart:ColumnSeries3D>

	...

    </chart:SfChart3D> 

{% endhighlight %}

{% highlight C# %} 

    ColumnSeries3D series = new ColumnSeries3D()
        {
            ItemsSource = new UsersViewModel().UsersList,
            XBindingPath = "TimeStamp",
            YBindingPath = "NoOfUsers",
            Label = "UserProfile",
            ShowTooltip = true,            
        };


{% endhighlight %}

{% endtabs %}

The following code example gives you the complete code of above configurations.

{% tabs %}

{% highlight xaml %}

<Window x:Class="GettingStarted_3DCharts.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:chart="clr-namespace:Syncfusion.UI.Xaml.Charts;assembly=Syncfusion.SfChart.WPF"
        xmlns:local="clr-namespace:GettingStarted_3DCharts"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    
    <Window.DataContext>
        <local:UsersViewModel/>
    </Window.DataContext>
    
    <Grid>
        <chart:SfChart3D x:Name="Chart3D" Width="500" Height="500" Header="Chart">

            <!--PrimaryAxis-->
            <chart:SfChart3D.PrimaryAxis>
                <chart:DateTimeAxis3D/>
            </chart:SfChart3D.PrimaryAxis>
            <!--SecondaryAxis-->
            <chart:SfChart3D.SecondaryAxis>
                <chart:NumericalAxis3D/>
            </chart:SfChart3D.SecondaryAxis>
            
            <!--Legend-->
            <chart:SfChart3D.Legend>
                <chart:ChartLegend></chart:ChartLegend>
            </chart:SfChart3D.Legend>

            <chart:ColumnSeries3D Label="UserProfile" ItemsSource="{Binding UsersList}" XBindingPath="TimeStamp"
            YBindingPath="NoOfUsers" ShowTooltip="True">

                <!--Adornments-->
                <chart:ColumnSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowLabel="True"></chart:ChartAdornmentInfo3D>
                </chart:ColumnSeries3D.AdornmentsInfo>
            </chart:ColumnSeries3D>           

        </chart:SfChart3D>

    </Grid>
</Window>

{% endhighlight %}

{% highlight C# %}

    SfChart3D chart = new SfChart3D() { Header = "Chart", Height = 500, Width = 500 };

            //Adding horizontal axis to the chart 
            CategoryAxis3D primaryAxis = new CategoryAxis3D();
            primaryAxis.Header = "Time";
            primaryAxis.FontSize = 14;
            chart.PrimaryAxis = primaryAxis;

            //Adding vertical axis to the chart 
            NumericalAxis3D secondaryAxis = new NumericalAxis3D();
            secondaryAxis.Header = "Users";
            secondaryAxis.FontSize = 14;
            chart.SecondaryAxis = secondaryAxis;

            //Adding Legends for the chart
            ChartLegend legend = new ChartLegend();
            chart.Legend = legend;

            //Initializing column series
            ColumnSeries3D series = new ColumnSeries3D();
            series.ItemsSource = new UsersViewModel().UsersList;
            series.XBindingPath = "TimeStamp";
            series.YBindingPath = "NoOfUsers";
            series.Label = "UserProfile";
            //Enable Tooltip
            series.ShowTooltip = true;
                       

            //Setting adornment to the chart series
            series.AdornmentsInfo = new ChartAdornmentInfo3D() { ShowLabel = true };

            //Adding Series to the Chart Series Collection
            chart.Series.Add(series);
            this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Chart 3D support in WPF](3D-Charts_images/Chart-3D-GettingStarted.png)

You can find the complete getting started sample : [`GettingStarted`](https://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted-3DCharts1840393114)


