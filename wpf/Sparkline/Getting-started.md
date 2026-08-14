---
layout: post
title: Getting Started with WPF Sparkline control | Syncfusion®
description: Learn how to get started with the Syncfusion® WPF Sparkline control. Explore setup, features, examples, and customization options.
platform: wpf
control: SfSparkline
documentation: ug
---

# Getting Started with WPF Sparkline

## Creating a Sparkline

The following steps explain how to create a sparkline.

### Adding the assembly reference

* Open the [Add Reference](https://www.microsoft.com/en-us/download/details.aspx?id=55984) window from your project.
* Choose Assemblies -> Extensions -> Syncfusion.SfChart.WPF
* Add the following namespace in your XAML page:

{% tabs %}

{% highlight xaml %}

xmlns:Syncfusion="clr-namespace:Syncfusion.UI.Xaml.Charts"

{% endhighlight  %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Charts;

{% endhighlight %}

{% endtabs %}

N> The Add Reference window differs for Visual Basic projects.

### Initialize the sparkline

You need to initialize the sparkline represented by the `SfLineSparkline` class (`Syncfusion.UI.Xaml.Charts.SfLineSparkline`).

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline>

</Syncfusion:SfLineSparkline>

{% endhighlight  %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline();

{% endhighlight %}

{% endtabs %}

### Create a sample data source

Since the above step will produce only an empty sparkline, we need to add some data to the sparkline for plotting. In this step, let’s create a sample data source.

{% highlight c# %}

public class UserProfile
{
    public DateTime TimeStamp { get; set; }
    public double NoOfUsers { get; set; }
}

public class UsersViewModel
{
    public ObservableCollection<UserProfile> UsersList { get; set; }
    public UsersViewModel()
    {
        this.UsersList = new ObservableCollection<UserProfile>();
        DateTime date = DateTime.Today;
        UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 3000 });
        UsersList.Add(new UserProfile { TimeStamp = date.AddHours(1), NoOfUsers = 5000 });
        UsersList.Add(new UserProfile { TimeStamp = date.AddHours(1.5), NoOfUsers = -3000 });
        UsersList.Add(new UserProfile { TimeStamp = date.AddHours(2), NoOfUsers = -4000 });
        UsersList.Add(new UserProfile { TimeStamp = date.AddHours(2.5), NoOfUsers = 2000 });
        UsersList.Add(new UserProfile { TimeStamp = date.AddHours(3), NoOfUsers = 3000 });
    }
}

{% endhighlight  %}

N> Syncfusion Sparkline also supports an ItemsSource as a collection of double values and any collection inherited from IEnumerable.


### Binding data to the sparkline

We need to add the above `UsersViewModel` to the `DataContext` of the sparkline, bind the data source to the `ItemsSource` property of the `SfLineSparkline`, and then map the data using `YBindingPath` and `XBindingPath`.

{% tabs %}

{% highlight xaml %}

<Grid.DataContext>
    <local:UsersViewModel/>
</Grid.DataContext>

<Syncfusion:SfLineSparkline
    ItemsSource="{Binding UsersList}"
    XBindingPath="TimeStamp"
    YBindingPath="NoOfUsers">
</Syncfusion:SfLineSparkline>

{% endhighlight  %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{
  ItemsSource = new UsersViewModel().UsersList,
  XBindingPath = "TimeStamp",
  YBindingPath = "NoOfUsers"
};

{% endhighlight %}

{% endtabs %}

N> If `XBindingPath` is not mapped, the sparkline data is positioned as indexed.

The following illustrates the result of the above code sample:

![Binding data to WPF Sparkline](Getting-started_images/Getting-started_img1.png)

You can find the complete getting started sample from this [link](https://github.com/SyncfusionExamples/GettingStarted-WPF-Sparkline).

## Theme

SfSparkline supports various built-in themes. Refer to the following links to apply themes to SfSparkline:

* [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
* [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Setting theme to WPF Sparkline](Getting-started_images/Theme.png)
   
