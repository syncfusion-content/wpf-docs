---
layout: post
title: Getting started | SfSparkline | wpf | Syncfusion
description: getting started
platform: wpf
control: SfSparkline
documentation: ug
---

# Getting started

## Creating sparkline

Following steps explain how to create sparkline,

### Adding the assembly reference:

* Open the [Add Reference](http://msdn.microsoft.com/en-us/library/wkze6zky(v=vs.80).aspx) window from your project.
* To Choose our assemblies follow the below step depending upon the developing environment. 
* If using VS 2012 choose Assemblies > Extensions > Syncfusion.SfChart.WPF.dll 
* If using VS 2010 choose .Net>Syncfusion.SfChart.WPF.dll
* Add the following namespace in your XAML page:

{% tabs %}

{% highlight xaml %}

xmlns:Syncfusion="clr-namespace:Syncfusion.UI.Xaml.Charts"

{% endhighlight  %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Charts;

{% endhighlight %}

{% endtabs %}

### Initialize the sparkline

You need to initialize the sparkline represented by the following class Syncfusion.UI.Xaml.Charts.SfChart,

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline>

</Syncfusion:SfLineSparkline>

{% endhighlight  %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()

{% endhighlight %}

{% endtabs %}

### Create a Sample Data Source

Since the above step will produce only an empty sparkline, we need to add some data to the sparkline for plotting. In this step, let’s create a sample data source.

{% highlight c# %}

public class UserProfile

 {

   public DateTime TimeStamp { get; set; }

   public double NoOfUsers { get; set; }

 } 

public class UsersViewModel

 {

 public UsersViewModel()

  {

   this.UsersList = new ObservableCollection<UserProfile>();

   DateTime date = DateTime.Today;

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 3000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 5000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = -3000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = -4000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 2000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 3000 });  }

 public ObservableCollection<UserProfile> UsersList

  {

    get; set;

  }

 }

{% endhighlight  %}

N> Syncfusion sparkline also supports items source as collection of double values and collection inherited from IEnumerable.


### Binding Data to sparkline

We need to add the above UsersViewModel to the DataContext of the sparkline, bind the data source to the ItemsSource property of the SfLineSparkline, and then map the data using YBindingPath and XBindingPath.

{% tabs %}

{% highlight xaml %}

<Grid.DataContext>

	<local:UsersViewModel/>

</Grid.DataContext>

<Syncfusion:SfLineSparkline 

		ItemsSource="{Binding UsersList}" 

		YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{% endhighlight  %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

  ItemsSource = new SparkViewModel().UsersList,

  YBindingPath = "NoOfUsers"

};

{% endhighlight %}

{% endtabs %}

N> if we do not map the XBindingPath means sparkline data positioned as indexed.

The following illustrates the result of the above code sample,

![Binding Data to WPF sparkline](Getting-started_images/Getting-started_img1.png)

## Theme

SfSparkline supports various built-in themes. Refer to the below links to apply themes for the SfSparkline,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to wpf document container](Getting-started_images/Theme.png)
   
