---
layout: post
title: Getting Started | SfDateTimeRangeNavigator | wpf | Syncfusion
description: getting started
platform: wpf
control: SfDateTimeRangeNavigator
documentation: ug
---

# Getting Started

## Visual Structure

A SfDateTimeRangeNavigator is composed of various elements such as Higher level bar, Lower Level Bar, Content, Resizable Scrollbar.

* Higher Level Bar - Contains timespan format one level Higher than Lower Level Bar DateTime values. E.g.  Higher Level Bar contains year format (yyyy) then the Lower Level Bar contains the Month format (MMM).
* Lower Level bar – Contains timespan format one lever Lower than Higher Level DateTime Values. E.g.  Lower Level Bar contains Month format (MMM) then the Higher Level Bar contains the year format (yyyy).
* Content – Can hold any type of UI element inside the Navigator.
* Resizable Scrollbar – Used to zoom and scroll the content and Label Bars. 

![](Getting-Started_images/Getting-Started_img1.png)


## Create a SfDateTimeRangeNavigator

The following steps explain how to create a SfDateTimeRangeNavigator.

### Adding the assembly reference

1. Open the Add Reference window from your project.
2. To Choose our assemblies follow the below step depending upon the developing environment. 
   
   * If using VS 2012 choose Assemblies > Extensions > Syncfusion.SfChart.WPF.dll 
   * If using VS 2010 choose .Net>Syncfusion.SfChart.WPF.dll

3.  Add the following namespace in your XAML page:

{% highlight xaml %}

xmlns:Syncfusion="clr-namespace:Syncfusion.UI.Xaml.Charts"

{% endhighlight  %}

### Initialize the SfDateTimeRangeNavigator

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfDateTimeRangeNavigator>

</Syncfusion:SfDateTimeRangeNavigator >

{% endhighlight  %}

{% highlight c# %}

 SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator();

{% endhighlight %}

{% endtabs %}

### Setting ItemsSource for SfDateTimeRangeNavigator

Since the above step will produce an empty SfDateTimeRangeNavigator without any labels, we need to set the ItemsSource and XBindingPath for the SfDateTimeRangeNavigator. The ItemsSource must implement the IEnumerable interface. 

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfDateTimeRangeNavigator ItemsSource="{Binding UsersList}" XBindingPath="Date"  >

</Syncfusion:SfDateTimeRangeNavigator >

{% endhighlight  %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

        ItemsSource = new ViewModel().UsersList,

        XBindingPath ="Date"

};

{% endhighlight %}

{% endtabs %}

### Adding Content

Next Add Content which needs to be displayed inside a SfDateTimeRangeNavigator.

### Property 

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
ItemsSource</td><td>
Used to set the ItemsSource for SfDateTimeRangeNavigator</td></tr>
<tr>
<td>
XBindingPath</td><td>
Represents the DateTime X values</td></tr>
<tr>
<td>
Content</td><td>
To add any UI content inside a SfDateTimeRangeNavigator</td></tr>
</table>

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfDateTimeRangeNavigator ItemsSource="{Binding UsersList}" XBindingPath="Date"  >

	<Syncfusion:SfDateTimeRangeNavigator.Content>

		<Syncfusion:SfChart x:Name="Chart">

			<Syncfusion:SfChart.PrimaryAxis>

				<Syncfusion:DateTimeAxis/>

			</Syncfusion:SfChart.PrimaryAxis>

		<Syncfusion:SfChart.SecondaryAxis>

    <Syncfusion:NumericalAxis/>

</Syncfusion:SfChart.SecondaryAxis>

<Syncfusion:LineSeries 

        ItemsSource="{Binding UsersList}" 

        XBindingPath="Date”

        YBindingPath="NoOfUsers">

</Syncfusion:LineSeries>

</Syncfusion:SfChart>

</Syncfusion:SfDateTimeRangeNavigator.Content >

</Syncfusion:SfDateTimeRangeNavigator >

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

chart.PrimaryAxis = new DateTimeAxis();

chart.SecondaryAxis = new NumericalAxis();

LineSeries series = new LineSeries()
{

        ItemsSource = new ViewModel().UsersList,

        XBindingPath = "Date",

        YBindingPath = "NoOfUsers"

};

chart.Series.Add(series);

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

        ItemsSource = new ViewModel().StockPriceDetails,

        XBindingPath ="Date"

};

rangeNavigator.Content = chart;

{% endhighlight %}

{% endtabs %}

The following illustrates the result of the above code sample:

![](Getting-Started_images/Getting-Started_img2.png)

## Create a SfDateTimeRangeNavigator from Code Behind

This section demonstrates how to create an application using SfDateTimeRangeNavigator from Code Behind.

### Add assembly reference

1. Open the Add Reference window from your project.
2. Choose Windows > Extensions >Syncfusion.SfChart.WPF.
3. Add the following namespace in your C# file, say MainPage.xaml.cs.


{% highlight c# %}

using Syncfusion.UI.Xaml.Charts;

{% endhighlight %}

Initialize the Range Navigator

{% highlight c# %}

SfDateTimeRangNavigator rangenavigator = new SfDateTimeRangNavigator ();

{% endhighlight  %}

Create a Sample Data Source

{% highlight c# %}

public class ItemsSource
 {

   public DateTime Date { get; set; }

   public double NoOfUsers { get; set; }

 }

public class UsersViewModel

 {

 public UsersViewModel()

  {

   this.UsersList = new ObservableCollection<ItemsSource>();

   DateTime date = DateTime.Today;

   UsersList.Add(new ItemsSource { TimeStamp = date.AddHours(0.5), NoOfUsers = 3000 });

   UsersList.Add(new ItemsSource { TimeStamp = date.AddHours(0.5), NoOfUsers = 5000 });

   UsersList.Add(new ItemsSource { TimeStamp = date.AddHours(0.5), NoOfUsers = 2000 });

   UsersList.Add(new ItemsSource { TimeStamp = date.AddHours(0.5), NoOfUsers = 7000 });

   UsersList.Add(new ItemsSource { TimeStamp = date.AddHours(0.5), NoOfUsers = 6000 });

   UsersList.Add(new ItemsSource { TimeStamp = date.AddHours(0.5), NoOfUsers = 3000 });  }

 public ObservableCollection<ItemsSource> UsersList

  {

    get; set;

  }

 }

{% endhighlight  %}

### Defining ItemsSource 

Define the ItemsSource for the Range Navigator as shown in the following code example.

N> You can set any IEnumerable collection as an ItemsSource.

{% highlight c# %}

//Intialize the SfDateTimeRangNavigator

SfDateTimeRangNavigator rangenavigator = new SfDateTimeRangNavigator ();

rangenavigator.ItemsSource = UsersList;

rangenavigator.XBindingPath = "Date";

{% endhighlight %}


### Adding Content

Add the content that needs to be displayed inside SfDateTimeRangeNavigator using the Content property.

{% highlight c# %}

//Intialize the SfChart

SfChart chart = new SfChart();

LineSeries series = new LineSeries();

series.ItemsSource = UsersList;

series.XBindingPath = "Date";

series.YBindingPath = "NoOfUsers";

var content = chart.Series.add(series);

//Add content to navigator

rangenavigator.Content = content;

{% endhighlight  %}


The following output is displayed as a result of the above code example.

![](Getting-Started_images/Getting-Started_img3.png)

N> The SelectedData property of SfDateTimeRangeNavigator returns the collection that represents the data between selected ranges in the Navigator.
