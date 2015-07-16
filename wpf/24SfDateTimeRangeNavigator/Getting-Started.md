---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: DateTime Range Navigator
documentation: ug
---

# Getting Started

## Visual Structure

A SfDateTimeRangeNavigator is composed of various elements such as Higher level bar, Lower Level Bar, Content, Resizable Scrollbar.

* Higher Level Bar - Contains timespan format one level Higher than Lower Level Bar DateTime values. E.g.  Higher Level Bar contains year format (yyyy) then the Lower Level Bar contains the Month format (MMM).
* Lower Level bar – Contains timespan format one lever Lower than Higer Level DateTime Values. E.g.  Lower Level Bar contains Month format (MMM) then the Higher Level Bar contains the year format (yyyy).
* Content – Can hold any type of UI element inside the Navigator.
* Resizable Scrollbar – Used to zoom and scroll the content and Label Bars. 



{ ![C:/Users/ApoorvahR/Desktop/1.png](Getting-Started_images/Getting-Started_img1.png) | markdownify }
{:.image }


## Create a SfDateTimeRangeNavigator

The following steps explain how to create a SfDateTimeRangeNavigator.

Adding the assembly reference

1. Open the Add Reference window from your project.
2. To Choose our assemblies follow the below step depending upon the developing environment. 
* If using VS 2012 choose Assemblies > Extensions > Syncfusion.SfChart.WPF.dll 
* If using VS 2010 choose .Net>Syncfusion.SfChart.WPF.dll

   3.  Add the following namespace in your XAML page:



[XAML]

xmlns:Syncfusion="clr-namespace:Syncfusion.UI.Xaml.Charts"



Initialize the SfDateTimeRangeNavigator



[XAML]

&lt;Syncfusion:SfDateTimeRangeNavigator&gt;

&lt;/Syncfusion:SfDateTimeRangeNavigator &gt;





Setting ItemsSource for SfDateTimeRangeNavigator

Since the above step will produce an empty SfDateTimeRangeNavigator without any labels, we need to set the ItemsSource and XBindingPath for the SfDateTimeRangeNavigator. The ItemsSource must implement the IEnumerable interface. 



[XAML]

&lt;Syncfusion:SfDateTimeRangeNavigator ItemsSource="{Binding ItemsSource}" XBindingPath="Date"  &gt;

 &lt;/Syncfusion:SfDateTimeRangeNavigator &gt;



Adding Content

Next Add Content which needs to be displayed inside a SfDateTimeRangeNavigator.

_Property table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
ItemsSource</td><td>
Used to set the ItemsSource for SfDateTimeRangeNavigator</td></tr>
<tr>
<td>
XBindingPath</td><td>
Represents the DateTime Xvalues</td></tr>
<tr>
<td>
Content</td><td>
To add any UI content inside a SfDateTimeRangeNavigator</td></tr>
</table>


[XAML]

&lt;Syncfusion:SfDateTimeRangeNavigator ItemsSource="{Binding ItemsSource}" XBindingPath="Date"  &gt;

&lt;Syncfusion:SfDateTimeRangeNavigator.Content&gt;

&lt;Syncfusion:SfChart x:Name="Chart"&gt;

  &lt;Syncfusion:SfChart.PrimaryAxis&gt;

    &lt;Syncfusion:DateTimeAxis/&gt;

  &lt;/Syncfusion:SfChart.PrimaryAxis&gt;

  &lt;Syncfusion:SfChart.SecondaryAxis&gt;

   &lt;Syncfusion:NumericalAxis/&gt;

  &lt;/Syncfusion:SfChart.SecondaryAxis&gt;

  <Syncfusion:LineSeries 

                ItemsSource="{Binding ItemsSource }" 

                XBindingPath="Date”

                YBindingPath="NoOfUsers">

  &lt;/Syncfusion:LineSeries&gt;



&lt;/Syncfusion:SfChart&gt;



&lt;/Syncfusion:SfDateTimeRangeNavigator.Content &gt;

 &lt;/Syncfusion:SfDateTimeRangeNavigator &gt;



The following illustrates the result of the above code sample:



{ ![C:/Users/ApoorvahR/Desktop/2.png](Getting-Started_images/Getting-Started_img2.png) | markdownify }
{:.image }


## Create a SfDateTimeRangeNavigator from Code Behind

This section demonstrates how to create an application using SfDateTimeRangeNavigator from Code Behind.

Add assembly reference

1. Open the Add Reference window from your project.
2. Choose Windows > Extensions >Syncfusion.SfChart.WPF.
3. Add the following namespace in your C# file, say MainPage.xaml.cs.



[C#]

using Syncfusion.UI.Xaml.Charts;





Initialize the Range Navigator



[C#]

SfDateTimeRangNavigator rangenavigator = new SfDateTimeRangNavigator ();





Create a Sample Data Source



[C#]



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



Defining ItemsSource 

Define the ItemsSource for the Range Navigator as shown in the following code example.

> _Note: You can set any IEnumerable collection as an ItemsSource._

> 

[C#]

//Intialize the SfDateTimeRangNavigator

SfDateTimeRangNavigator rangenavigator = new SfDateTimeRangNavigator ();

rangenavigator.ItemsSource = ItemsSource;

rangenavigator.XBindingPath = "Date";





Adding Content

Add the content that needs to be displayed inside SfDateTimeRangeNavigator using the Content property.



[C#]

//Intialize the SfChart

SfChart chart = new SfChart();

LineSeries series = new LineSeries();



series.ItemsSource = ItemsSource;

series.XBindingPath = "Date";

series.YBindingPath = "NoOfUsers";



var content = chart.Series.add(series);



//Add content to navigator



rangenavigator.Content = content;





The following output is displayed as a result of the above code example.



{ ![C:/Users/sureshs/Desktop/navigatorwpf3.png](Getting-Started_images/Getting-Started_img3.png) | markdownify }
{:.image }


> _Note:The SelectedData property of SfDateTimeRangeNavigator returns the collection that represents the data between selected ranges in the Navigator._



