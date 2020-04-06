---
layout: post
title: Series| SfChart | Wpf | Syncfusion
description: This section explains the different types of charts, including Cartesian, Financial, Accumulation, PolarRadar and its properties
platform: wpf
control: SfChart3D
documentation: ug
---

# Series in WPF Chart (SfChart3D)

### Series Types

* Column
* Bar
* Stacking column 
* Stacking column 100 
* Stacking bar
* Stacking bar
* Pie
* Doughnut



### Create a simple chart series

The following code can be used to create a simple doughnut series:

{% tabs %}
{% highlight xaml %}


<Page.DataContext>

      <local:UsersViewModel/>

</Page.DataContext>

<Syncfusion:SfChart3D x:Name="Chart" Height="500" Width="500">



<Syncfusion:SfChart3D.PrimaryAxis>



<Syncfusion:CategoryAxis3D/>



</Syncfusion:SfChart3D.PrimaryAxis>



<Syncfusion:SfChart3D.SecondaryAxis>



<Syncfusion:NumericalAxis3D/>



</Syncfusion:SfChart3D.SecondaryAxis>



<Syncfusion:DoughnutSeries3D



ItemsSource="{Binding UsersList}"



XBindingPath="TimeStamp"



YBindingPath="NoOfUsers">



</Syncfusion:DoughnutSeries3D>



</Syncfusion:SfChart3D >
{% endhighlight %}

{% highlight C# %}



public class UserProfile

 {

   public DateTime TimeStamp { get; set; }



   public double NoOfUsers { get; set; }

 }



public class UsersViewModel

 {

 public UsersViewModel()

  {

   this.UsersList = new ObservableCollection<UserProfile>();

   DateTime date = DateTime.Today;

   UsersList.Add(new UserProfile { TimeStamp=date.AddHours(0.5),NoOfUsers=1000});

   UsersList.Add(new UserProfile { TimeStamp=date.AddHours(0.5),NoOfUsers = 5000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 3000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 4000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 2000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 1000 });

  }

 public ObservableCollection<UserProfile> UsersList

  {

    get; set;

  }

 }
{% endhighlight %}
{% endtabs %}

The following image illustrates the result of the above code sample:

![Series types in WPF 3D Chart](3D-Charts_images/Charts-3D_img2.png)




